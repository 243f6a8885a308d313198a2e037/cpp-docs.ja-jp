---
title: "-Zc: rvalueCast (型の変換規則の実施) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- rvaluecast
- /Zc:rvalueCast
- VC.Project.VCCLCompilerTool.EnforceTypeConversionRules
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- rvaluecast
- Enforce type conversion rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 7825277d-e565-4c48-b0fb-76ac0b0c6e38
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8f4b888dde70708ee10b2d8000ff6380709dc870
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="zcrvaluecast-enforce-type-conversion-rules"></a>/Zc:rvalueCast (型変換規則の適用)
ときに、 **/Zc:rvalueCast**オプションを指定すると、コンパイラは、c++ 11 標準に従いキャスト操作の結果として右辺値参照型を正しく識別します。 このオプションを指定しない場合、コンパイラの動作は Visual Studio 2012 での動作と同じです。 既定では、 **/Zc:rvalueCast**は無効になっています。 使用することをお勧め標準に準拠しキャストの使用でエラーを回避するのには、 **/Zc:rvalueCast**です。  
  
## <a name="syntax"></a>構文  
  
```  
/Zc:rvalueCast[-]  
```  
  
## <a name="remarks"></a>コメント  
 場合**/Zc:rvalueCast**が指定されている、コンパイラは、c++ 11 標準のセクション 5.4 をに従って扱いますなるキャスト式のみ非参照型で発生して、関数ではない型への右辺値参照になる式をキャスト右辺値の型。 既定では、または**/Zc:rvalueCast-**指定すると、コンパイラは、非準拠と右辺値と右辺値参照になるすべてのキャスト式を処理します。  
  
 使用して**/Zc:rvalueCast**を右辺値参照型を受け取る関数に引数としてキャスト式を渡す場合です。 既定動作により、コンパイラ エラー [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md)場合、コンパイラと誤って判断キャスト式の型。 この例では、/Zc:rvalueCast を指定しない場合に、正しいコードでコンパイラ エラーが表示されます。  
  
```cpp  
// Test of /Zc:rvalueCast  
// compile by using:  
// cl /c /Zc:rvalueCast- make_thing.cpp  
// cl /c /Zc:rvalueCast make_thing.cpp  
  
#include <utility>  
  
template <typename T>   
struct Thing {  
   // Construct a Thing by using two rvalue reference parameters  
   Thing(T&& t1, T&& t2)  
      : thing1(t1), thing2(t2) {}  
  
   T& thing1;  
   T& thing2;  
};  
  
// Create a Thing, using move semantics if possible  
template <typename T>  
Thing<T> make_thing(T&& t1, T&& t2)  
{  
   return (Thing<T>(std::forward<T>(t1), std::forward<T>(t2)));  
}  
  
struct Test1 {  
   long a;  
   long b;  
  
   Thing<long> test() {   
      // Use identity casts to create rvalues as arguments  
      return make_thing(static_cast<long>(a), static_cast<long>(b));   
   }  
};  
  
```  
  
 コンパイラの既定動作では、場合によっては C2102 エラーが報告されないことがあります。 この例では、コンパイラはエラーを報告、id のキャストによって作成された右辺値のアドレスが作成された場合**/Zc:rvalueCast**が指定されていません。  
  
```cpp  
int main() {  
   int a = 1;  
   int *p = &a;   // Okay, take address of lvalue   
                  // Identity cast creates rvalue from lvalue;    
   p = &(int)a;   // problem: should cause C2102: '&' requires l-value  
}  
```  
  
 Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  選択、 **C/C++**フォルダーです。  
  
3.  選択、**コマンドライン**プロパティ ページ。  
  
4.  変更、**追加オプション**含めるプロパティを**/Zc:rvalueCast**を選択し**OK**です。  
  
## <a name="see-also"></a>参照  
 [/Zc (準拠)](../../build/reference/zc-conformance.md)