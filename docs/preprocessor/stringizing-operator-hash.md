---
title: "文字列化演算子 (#) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: '#'
dev_langs: C++
helpviewer_keywords:
- preprocessor, operators
- arguments [C++], converting to strings
- stringizing operator
- preprocessor
- string literals, converting macro parameters to
- macros [C++], converting parameters to strings
- '# preprocessor operator'
ms.assetid: 1175dd19-4538-43b3-ad97-a008ab80e7b1
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 320d3d2e5071d03a562e6673a8c13d28f4d0d114
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="stringizing-operator-"></a>文字列化演算子 (#)
シャープ記号つまり「文字列化」演算子 (**#**)、パラメーターの定義を展開することがなくマクロのパラメーターを文字列リテラルに変換します。 これは、引数を受け取るマクロでのみ使用されます。 マクロ定義の仮パラメーターの前に指定すると、マクロの呼び出し時に渡される実際の引数は一重引用符で囲まれ、文字列リテラルとして扱われます。 文字列リテラルは、マクロ定義内の文字列化演算子と仮パラメーターの組み合わせをすべて置き換えます。  
  
> [!NOTE]
>  Microsoft C (Version 6.0 以前) では、ANSI C 規格を拡張して、文字列リテラルと文字定数の内部に現れるマクロ仮引数を展開していましたが、この拡張機能はサポートされなくなりました。 この拡張機能に依存したコードは、文字列化を使用して書き直す必要があります (**#**) 演算子。  
  
実引数の最初のトークンに先行する空白と、実引数の最後のトークンに後続する空白は無視されます。 実引数のトークンの間にある空白は、結果の文字列リテラルでは 1 個の空白にまとめられます。 したがって、実引数で 2 つのトークンの間にコメントがある場合、コメントは 1 個の空白に置き換えられます。 結果の文字列リテラルは、隣接する任意の文字列リテラルと、空白のみで区切られて自動的に連結されます。  
  
さらに、通常の引数に含まれる文字が文字列リテラルで使用する場合は、エスケープ シーケンスが必要な場合 (たとえば、二重引用符の (**"**) または円記号 (**\\**) 文字) では、必要なエスケープ バック スラッシュが文字の前に自動的に挿入します。  
  
エスケープ シーケンスを含む文字列を使用する場合、Visual C 文字列化演算子は正しく動作しません。 この場合、コンパイラが生成されます[コンパイラ エラー C2017](../error-messages/compiler-errors-1/compiler-error-c2017.md)です。  
  
## <a name="example"></a>例  
次の例は、文字列化演算子を含むマクロ定義と、そのマクロを呼び出すメイン関数を示しています。  
  
このような呼び出しはプリプロセッサによって展開され、次のコードが生成されます。  
  
```cpp  
int main() {  
   printf_s( "In quotes in the printf function call\n" "\n" );  
   printf_s( "\"In quotes when printed to the screen\"\n" "\n" );  
   printf_s( "\"This: \\\" prints an escaped double quote\"" "\n" );  
}  
```  
  
```cpp  
// stringizer.cpp  
#include <stdio.h>  
#define stringer( x ) printf_s( #x "\n" )  
int main() {  
   stringer( In quotes in the printf function call );   
   stringer( "In quotes when printed to the screen" );     
   stringer( "This: \"  prints an escaped double quote" );  
}  
```  
  
```Output  
In quotes in the printf function call  
"In quotes when printed to the screen"  
"This: \"  prints an escaped double quote"  
```  
  
## <a name="example"></a>例  
次の例は、マクロ パラメーターを展開する方法を示しています。  
  
```cpp  
// stringizer_2.cpp  
// compile with: /E  
#define F abc  
#define B def  
#define FB(arg) #arg  
#define FB1(arg) FB(arg)  
FB(F B)  
FB1(F B)  
```  
  
## <a name="see-also"></a>参照  
 [プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)