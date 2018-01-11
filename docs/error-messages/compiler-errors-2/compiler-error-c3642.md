---
title: "コンパイラ エラー C3642 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3642
dev_langs: C++
helpviewer_keywords: C3642
ms.assetid: 429790c2-9614-4d85-b31c-687c8d8f83ff
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3dace0204f4534ee630924bd443d028efc2afc14
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3642"></a>コンパイラ エラー C3642
' return_type/args ': _ _clrcall 呼び出し規約をネイティブ コードからの関数を呼び出すことはできません  
  
 マークされている関数、 [_ _clrcall](../../cpp/clrcall.md)呼び出し規約は、ネイティブ (アンマネージ) コードから呼び出すことができません。  
  
 *return_type/args*は関数の名前またはの種類、`__clrcall`関数を呼び出すしようとしています。  関数ポインターを通じて呼び出す場合に、型を使用します。  
  
 マネージ関数を呼び出すネイティブ コンテキストから、「ラッパー」関数を呼び出すを追加することができます、`__clrcall`関数。 または、CLR マーシャ リング機構を使用することができます。参照してください[する方法: PInvoke を使用して関数ポインターをマーシャ リング](../../dotnet/how-to-marshal-function-pointers-using-pinvoke.md)詳細についてはします。  
  
 次の例では、C3642 が生成されます。  
  
```  
// C3642.cpp  
// compile with: /clr  
using namespace System;  
struct S {  
   void Test(String ^ s) {   // CLR type in signature, implicitly __clrcall  
      Console::WriteLine(s);  
   }  
   void Test2(char * s) {  
      Test(gcnew String(s));  
   }  
};  
  
#pragma unmanaged  
int main() {  
   S s;  
   s.Test("abc");   // C3642  
   s.Test2("abc");   // OK  
}  
```