---
title: "コンパイラ エラー C2872 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2872
dev_langs:
- C++
helpviewer_keywords:
- C2872
ms.assetid: c619ef97-6e0e-41d7-867c-f8d28a07d553
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: c81fc315c4bb893b96876b7b67b42806a3246583
ms.lasthandoff: 04/29/2017

---
# <a name="compiler-error-c2872"></a>{1&gt;コンパイラ エラー C2872&lt;1}
'*シンボル*': あいまいなシンボル  
  
コンパイラを参照する記号を特定できません。 指定した名前の 2 つ以上のシンボルは、スコープでです。 コンパイラのあいまいなシンボルが次のファイルの場所と宣言のエラー メッセージは、ノートを参照してください。 この問題を解決することが完全に修飾する、あいまいなシンボル、名前空間、たとえばを使用して、`std::byte`または`::byte`です。 使用することも、[名前空間の別名](../../cpp/namespaces-cpp.md#namespace_aliases)ソース コード内のシンボルを明確化際に、使用するための便利な短い名前を含まれる名前空間に提供しています。  
  
C2872 は、ヘッダー ファイルが含まれている場合に発生することができます、[ディレクティブを使用して](../../cpp/namespaces-cpp.md#using_directives)、後続のヘッダー ファイルが含まれるともに指定された名前空間内にある型を格納している、`using`ディレクティブです。 指定して、`using`後にのみ、ヘッダー ファイルがで指定されたディレクティブ`#include`です。  
  
 C2872 の詳細については、サポート技術情報の記事を参照してください。 [[prb]: コンパイラ エラー時に使用する #import Visual c .NET での XML で](http://support.microsoft.com/kb/316317)と["エラー C2872: 'Platform': あいまいなシンボル"Visual Studio 2013 で Windows::Foundation::Metadata 名前空間を使用すると、エラー メッセージ](https://support.microsoft.com/kb/2890859)です。  
  
## <a name="example"></a>例  
 次の例では、という名前の変数に、あいまいな参照が行われるので C2872 が生成されます`i`以外の場合は 2 つと同じ名前の変数のスコープは。  
  
```cpp  
// C2872.cpp  
// compile with: cl /EHsc C2872.cpp  
namespace A {  
   int i;  
}  
  
using namespace A;  
int i;  
int main() {  
   ::i++;   // ok, uses i from global namespace  
   A::i++;   // ok, uses i from namespace A  
   i++;   // C2872 ambiguous: ::i or A::i? 
   // To fix this issue, use the fully qualified name
   // for the intended variable. 
}  
```
