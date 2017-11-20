---
title: "非標準動作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- compatibility and compliance, nonstandard behavior
- Microsoft-specific, compiler behavior
- nonstandard behavior, compliance and compatibility
ms.assetid: a57dea27-dc79-4f64-8a83-017e84841773
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 73b60bbdbd38738f8cb5d127b464b14465de413b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="nonstandard-behavior"></a>非標準動作
ここからのセクションでは、C++ の Visual C++ 実装が C++ 規格に準拠しない部分をいくつか示します。 ここで示している節番号は C++ 11 規格 (ISO/IEC 14882:2011(E)) の節番号に対応しています。  
  
 C++ 標準で定義されているものとは異なるコンパイラの制限の一覧が指定された[コンパイラの制限](../cpp/compiler-limits.md)です。  
  
## <a name="covariant-return-types"></a>共変の戻り値の型  
 仮想関数が可変個の引数を持つ場合、仮想既定クラスは共変の戻り値の型としてサポートされません。 このことは C++ ISO 仕様の 10.3 節 7 項に準拠していません。 次の例はコンパイルされず、コンパイル エラー [C2688](../error-messages/compiler-errors-2/compiler-error-c2688.md)  
  
```cpp  
// CovariantReturn.cpp  
class A   
{  
   virtual A* f(int c, ...);   // remove ...  
};  
  
class B : virtual A  
{  
   B* f(int c, ...);   // C2688 remove ...  
};  
```  
  
## <a name="binding-nondependent-names-in-templates"></a>テンプレートの非依存名のバインド  
 Visual C++ コンパイラでは現在、テンプレート初期解析時の非依存名のバインドはサポートされていません。 このことは、C++ ISO 仕様の 14.6.3 節に準拠していません。 そのため、テンプレートの定義後 (ただしインスタンス化前) にオーバーロードが宣言される場合があります。  
  
```cpp  
#include <iostream>  
using namespace std;  
  
namespace N {  
   void f(int) { cout << "f(int)" << endl;}  
}  
  
template <class T> void g(T) {  
    N::f('a');   // calls f(char), should call f(int)  
}  
  
namespace N {  
    void f(char) { cout << "f(char)" << endl;}  
}  
  
int main() {  
    g('c');  
}  
// Output: f(char)  
  
```  
  
## <a name="function-exception-specifiers"></a>関数の例外指定子  
 `throw()` 以外の関数の例外の指定子は解析されますが、使用されません。 このことは、ISO C++ 仕様の 15.4 節に準拠していません。 例:  
  
```cpp  
void f() throw(int); // parsed but not used  
void g() throw();    // parsed and used  
```  
  
 例外の仕様の詳細については、次を参照してください。[例外指定](../cpp/exception-specifications-throw-cpp.md)です。  
  
## <a name="chartraitseof"></a>char_traits::eof()  
 C++ 規格[char_traits::eof](../standard-library/char-traits-struct.md#eof)有効なに対応する必要がありますしない`char_type`値。 Visual C++ コンパイラは `char` 型ではなく、`wchar_t` 型にこの制約を適用します。 このことは、C++ ISO 規格の 12.1.1 節の表 62 に示された要件に準拠していません。 次に示しているのはその例です。  
  
```cpp  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    char_traits<char>::int_type int2 = char_traits<char>::eof();  
    cout << "The eof marker for char_traits<char> is: " << int2 << endl;  
  
    char_traits<wchar_t>::int_type int3 = char_traits<wchar_t>::eof();  
    cout << "The eof marker for char_traits<wchar_t> is: " << int3 << endl;  
}  
```  
  
## <a name="storage-location-of-objects"></a>オブジェクトの格納場所  
 C++ 規格の 1.8 節 6 項によると、完全な C++ オブジェクトには一意の格納場所が必要です。 ただし、Visual C++ では、データ メンバーのない型がオブジェクトの有効期間に他の型とデータの格納場所を共有する場合があります。