---
title: "コンパイラの警告 (レベル 3 および 4) C4244 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4244
dev_langs: C++
helpviewer_keywords: C4244
ms.assetid: f116bb09-c479-4b4e-a647-fe629a1383f6
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cc5fdcbced4da3fc4f40a6cbdfa319e026a0f1f5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-levels-3-and-4-c4244"></a>コンパイラの警告 (レベル 3 および 4) C4244
'conversion': 'type1' から 'type2' に変換しました。データが失われている可能性があります。  
  
 整数型が、より小さい整数の型に変換されています。 これは、場合のレベル 4 の警告*type1*は`int`と*type2*よりも小さい`int`です。 それ以外の場合は、レベル 3 (型の値を割り当てられている[_ _int64](../../cpp/int8-int16-int32-int64.md)型の変数に`unsigned int`)。 データが失われた可能性があります。  
  
 C4244 の場合は、互換性のある型を使用するようにプログラムを変更するか、別のロジックをコードに追加して、変換される値の範囲が使用している型と常に互換性があるようにします。  
  
 また c4244 レベル 2 です。参照してください[コンパイラの警告 (レベル 2) C4244](../../error-messages/compiler-warnings/compiler-warning-level-2-c4244.md)詳細についてはします。  
  
 変換では、暗黙の変換によって問題が発生する可能性があります。  
  
 次の例では C4244 が生成されます。  
  
```  
// C4244_level4.cpp  
// compile with: /W4  
int aa;  
unsigned short bb;  
int main() {  
   int b = 0, c = 0;  
   short a = b + c;   // C4244  
  
   bb += c;   // C4244  
   bb = bb + c;   // C4244  
   bb += (unsigned short)aa;   // C4244  
   bb = bb + (unsigned short)aa;   // OK  
}  
```  
  
 詳細については、次を参照してください。[通常の算術変換](../../c-language/usual-arithmetic-conversions.md)です。  
  
```  
// C4244_level3.cpp  
// compile with: /W3  
int main() {  
   __int64 i = 8;  
   unsigned int ii = i;   // C4244  
}  
```  
  
 警告 C4244 は、64 ビット ターゲットのコードをビルドする際に発生することがあり、32 ビット ターゲットのビルドでは発生しません。 たとえば、ポインター間の違いは、32 ビット プラットフォームでは 32 ビット数で、64 ビット プラットフォームでは 64 ビット数ということです。  
  
 次の例では、64 ビット ターゲットのコンパイル時に C4244 が生成されます。  
  
```  
// C4244_level3_b.cpp  
// compile with: /W3   
int main() {  
   char* p1 = 0;  
   char* p2 = 0;  
   int x = p2 - p1;   // C4244  
}  
```