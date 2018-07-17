---
title: ヘッダー ファイル (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 04/20/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- header files [C++]
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b571cd2836e66ebef21898af27cf2a6d7082e0e5
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2018
ms.locfileid: "36261068"
---
# <a name="header-files-c"></a>ヘッダー ファイル (C++)

使用する前に、変数、関数、クラスなどのプログラム要素の名前を宣言する必要があります。 たとえば、だけを書き込めません`x = 42`宣言する前に 'x' です。 

```cpp
int x; // declaration
x = 42; // use x
```

 宣言コンパイラに指示するかどうかは、 **int**、**二重**、**関数**、**クラス**またはその他のいくつかのことです。  さらに、それぞれの名前で宣言されなければなりません (直接または間接的に) が使用されているすべての .cpp ファイルです。 プログラムをコンパイルするときに各 .cpp ファイルにコンパイルされましていない個別にコンパイル ユニット。 コンパイラには、その他のコンパイル単位でどのような名前が宣言されているに関する情報がありません。 つまり、クラスまたは関数やグローバル変数を定義する場合は、そのことをそれを使用する各追加の .cpp ファイルでの宣言を指定する必要があります。 そのリソースの各宣言は、すべてのファイルと正確に一致する必要があります。 多少の不整合が発生エラー、または意図しない動作は、リンカーが 1 つのプログラムにすべてのコンパイル単位をマージしようとするとします。

C++ での使用規則は採用してエラーの可能性を最小限に抑える、*ヘッダー ファイル*宣言を格納します。 ヘッダー ファイルで宣言を確認しを使用する、# すべての .cpp ファイルの include ディレクティブや他のヘッダー ファイルには、その宣言が必要です。 #Include ディレクティブを挿入、ヘッダー ファイルのコピーをコンパイルする前に、.cpp ファイルに直接 include です。 

## <a name="example"></a>例

次の例では、クラスを宣言し、別のソース ファイルで使用する一般的な方法を示します。 ヘッダー ファイルから始めます**my_class.h**です。 クラスの定義が含まれていますが、定義が完了したことに注意してください。このメンバー関数は`do_something`が定義されていません。

```cpp
// my_class.h
namespace N
{
    class my_class
    {
    public:
        void do_something();
    };

}
```

次に、(通常の .cpp または同様の拡張機能)、実装ファイルを作成します。 うまくファイル my_class.cpp を呼び出すし、メンバー宣言の定義を提供します。 追加、`#include`ディレクティブ my_class 宣言を挿入するために"my_class.h"ファイルをこの時点で、.cpp ファイル、およびおあります **\<iostream >** の宣言を取得する`std::cout`です。 引用符は、ソース ファイルと同じディレクトリ内のヘッダー ファイルの使用、山かっこが標準ライブラリのヘッダーに使用されることに注意してください。 また、多くの標準ライブラリのヘッダーでは、.h または他のファイル拡張子がありません。

実装ファイルに必要に応じて使用できます、**を使用して**ステートメントと"my_class"または"cout"のすべての言及を修飾することを避けるために"n::"または"std::"です。  入れないでください**を使用して**ヘッダー ファイル内のステートメント。

```cpp
// my_class.cpp
#include "my_class.h" // header in local directory
#include <iostream> // header in standard library

using namespace N;
using namespace std;

void my_class::do_something()
{
    cout << "Doing something!" << endl;
}
```

使用できるようになりました`my_class`別の .cpp ファイルにします。 お #include、ヘッダー宣言で、コンパイラが取得できるようにします。 すべてのコンパイラいる必要がありますはその my_class という名前のパブリック メンバー関数を持つクラスである`do_something()`です。

```cpp
// my_program.cpp
#include "my_class.h"

using namespace N;

int main()
{
    my_class mc;
    mc.do_something();
    return 0;
}
```

コンパイラでは、.obj ファイルに各 .cpp ファイルのコンパイルが完了すると、.obj ファイルがリンカーに渡します。 My_class; の 1 つだけの定義が見つかれば、リンカーは、オブジェクト ファイルをマージした場合my_class.cpp、に対して生成される .obj ファイル内にあるし、ビルドが成功します。

## <a name="include-guards"></a>#Include guard

通常、ヘッダー ファイルが、 *guard*または **#pragma once**ディレクティブをそれらが挿入されるようにいない複数回、1 つの .cpp ファイルにします。 

my_class.h
#<a name="ifndef-myclassh--include-guard"></a>ifndef MY_CLASS_H/guard/
#<a name="define-myclassh"></a>MY_CLASS_H を定義します。


名前空間 N {クラス my_class {パブリック: do_something(); を無効にする} です。

}

#<a name="endif--myclassh-"></a>endif/* MY_CLASS_H */

## <a name="what-to-put-in-a-header-file"></a>ヘッダー ファイルに記述する内容

ヘッダー ファイルを複数のファイルが含まれている可能性がある可能性があります、ため、同じ名前の複数の定義を引き起こす可能性がある定義は使用できません。 次は許可されませんまたは非常に悪いプラクティスと見なされます。

- 名前空間またはグローバル スコープでの組み込みの種類の定義
- 非インライン関数の定義 
- 非 const 変数の定義
- 集計の定義
- 名前のない名前空間
- using ディレクティブ

使用、**を使用して**ディレクティブは、エラーを必ずしもはされませんが、名前空間をもたらすことに直接または間接的には、そのヘッダーがインクルードされるすべての .cpp ファイルのスコープ内にあるために、問題になる可能性があります。 

## <a name="sample-header-file"></a>ヘッダー ファイルのサンプル

次の例は、さまざまな種類の宣言と定義済みヘッダー ファイルで許可されるを示しています。

```cpp
#pragma once 
#include <vector> // #include directive
#include <string>

namespace N  // namespace declaration
{

    inline namespace P
    {
        //...
    }

    enum class colors : short { red, blue, purple, azure };


    const double PI = 3.14;  // const and constexpr definitions
    constexpr int MeaningOfLife{ 42 };
    constexpr int get_meaning()
    {
        static_assert(MeaningOfLife == 42, "unexpected!"); // static_assert
        return MeaningOfLife;
    }
    using vstr = std::vector<int>;  // type alias
    extern double d; // extern variable

#define LOG   // macro definition

#ifdef LOG   // conditional compilation directive
    void print_to_log();
#endif


    class my_class   // regular class definition, 
    {                // but no non-inline function definitions

        friend class other_class;
    public:
        void do_something();   // definition in my_class.cpp
        inline void put_value(int i) { vals.push_back(i); } // inline OK

    private:
        vstr vals;
        int i;
    };

    struct RGB
    {
        short r{ 0 };  // member initialization
        short g{ 0 };
        short b{ 0 };
    };

    template <typename T>  // template definition
    class value_store
    {
    public:
        value_store<T>() = default;
        void write_value(T val)
        {
            //... function definition OK in template
        }
    private:
        std::vector<T> vals;
    };

    template <typename T>  // template declaration
    class value_widget;

}