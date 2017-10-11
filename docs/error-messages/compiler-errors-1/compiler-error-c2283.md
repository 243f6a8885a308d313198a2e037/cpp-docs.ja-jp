---
title: "コンパイラ エラー C2283 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2283
dev_langs:
- C++
helpviewer_keywords:
- C2283
ms.assetid: 8a5b3175-b480-4598-a1f7-0b50504c5caa
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c6c3a02fcd88f5bb61e6856ad841883a17718d1a
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2283"></a>コンパイラ エラー C2283
'identifier' : 名前指定されていない struct が、純粋関数または抽象オーバーライド関数として指定されています  
  
 名前が指定されていないクラスまたは構造体のメンバー関数が、純粋指定子で宣言されていますが、これは許可されません。  
  
 次の例では C2283 が生成されます。  
  
```  
// C2283.cpp  
// compile with: /c  
struct {  
   virtual void func() = 0;   // C2283  
};  
struct T {  
   virtual void func() = 0;   // OK  
};  
```
