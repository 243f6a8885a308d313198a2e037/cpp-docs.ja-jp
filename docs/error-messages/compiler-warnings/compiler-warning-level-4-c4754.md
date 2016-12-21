---
title: "コンパイラの警告 (レベル 4) C4754 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4754"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4754"
ms.assetid: e0e4606a-754a-4f42-a274-21a34978d21d
caps.latest.revision: 6
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4754
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

比較での算術演算の変換規則により、いずれかの分岐を実行できません。  
  
 比較の結果が常に同じであるため、C4754 警告が出力されます。  これは、条件のいずれかの分岐が実行されることがないことを示します。ほとんどの場合、関連付けられた整数式が間違っているためです。  このコードの欠陥は、多くの場合、64 ビット アーキテクチャでの間違った整数オーバーフローのチェックで発生します。  
  
 整数変換の規則は複雑であり、気付きにくい落とし穴が数多くあります。  C4754 警告を解決する別の方法として、[SafeInt ライブラリ](../../windows/safeint-library.md)を使用するようにコードを更新できます。  
  
## 使用例  
 次の例では C4754 エラーが生成されます。  
  
```cpp  
// C4754a.cpp  
// Compile with: /W4 /c  
#include "errno.h"  
  
int sum_overflow(unsigned long a, unsigned long b)   
{  
   unsigned long long x = a + b; // C4754  
  
   if (x > 0xFFFFFFFF)   
   {  
      // never executes!  
      return EOVERFLOW;  
   }  
   return 0;  
}  
```  
  
 加算 `a + b` では、結果が 64 ビットの値にアップキャストされて 64 ビットの変数 `x` に代入される前に、算術オーバーフローが発生する可能性があります。  つまり、`x` のチェックが冗長であり、オーバーフローをキャッチすることはありません。  この場合、コンパイル時に次の警告が出力されます。  
  
  **C4754 警告: C4754a.cpp \(7\) における比較時の算術演算の変換ルールにより、インライン関数で 1 つの分岐が実行できないことが示されています。  '\(a \+ ...\)' を 'ULONG64' \(または %d バイトの類似する型\) にキャストしてください。**  この警告を解決するには、8 バイトの値にオペランドをキャストする代入ステートメントを次のように変更できます。  
  
```cpp  
// Casting one operand is sufficient to force all the operands in   
// the addition be upcast according to C/C++ conversion rules, but  
// casting both is clearer.  
unsigned long long x =   
   (unsigned long long)a + (unsigned long long)b;  
```  
  
## 使用例  
 次の例でも C4754 警告が出力されます。  
  
```cpp  
// C4754b.cpp  
// Compile with: /W4 /c  
#include "errno.h"  
  
int wrap_overflow(unsigned long a)   
{  
   if (a + sizeof(unsigned long) < a) // C4754  
   {   
      // never executes!  
      return EOVERFLOW;  
   }  
   return 0;  
}  
```  
  
 `sizeof()` 演算子は `size_t` 型を返します。そのサイズはアーキテクチャによって異なります。  このコード例は 32 ビット アーキテクチャで動作します。ここで、`size_t` は 32 ビット型です。  ただし、64 ビット アーキテクチャでは、`size_t` は 64 ビット型です。  整数の変換規則により、式 `a + b < a` で `a` が 64 ビット値にアップキャストされます。これは、`(size_t)a + (size_t)b < (size_t)a` と記述した場合と同等です。  `a` と `b` が 32 ビット整数である場合は、64 ビット加算演算がオーバーフローすることも、制約が適用されることもありません。  その結果、コードは 64 ビット アーキテクチャで整数オーバーフロー状態を検出することはありません。  この例では、コンパイル時に次の警告が出力されます。  
  
  **C4754 警告: C4754b.cpp \(7\) における比較時の算術演算の変換ルールにより、1 つの分岐が実行できないことが示されています。  '4' を 'ULONG' \(または 4 バイトの類似する型\) にキャストしてください。**  警告メッセージでは、元のソース文字列ではなく定数値 4 が明示的に表示されていることに注意してください。警告の分析によって問題のあるコードが検出されるまでに、`sizeof(unsigned long)` は既に定数に変換されています。  したがって、警告メッセージでソース コード内のどの式が定数値に関連付けられているかを追跡する必要があります。  C4754 警告メッセージで定数に解決される最も一般的なコードのソースは `sizeof(TYPE)` や `strlen(szConstantString)` のような式です。  
  
 この場合、修正したコードは次のようになります。  
  
```cpp  
// Casting the result of sizeof() to unsigned long ensures  
// that all the addition operands are 32-bit, so any overflow   
// is detected by the check.  
if (a + (unsigned long)sizeof(unsigned long) < a)  
  
```  
  
 **メモ** コンパイラの警告で言及される行番号はステートメントの最後の行を示します。  複数の行にまたがる複雑な条件文に関する警告メッセージでは、コードの欠陥がある行は、報告された行の前の数行になる場合があります。  たとえば、次のようになります。  
  
```cpp  
unsigned long a;  
  
if (a + sizeof(unsigned long) < a || // incorrect check  
    condition1() ||   
    a == 0) {    // C4754 warning reported on this line  
         // never executes!  
         return INVALID_PARAMETER;  
}  
  
```