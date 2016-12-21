---
title: "コンパイラ エラー C2227 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2227"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2227"
ms.assetid: d470e8b8-7e15-468b-84fa-37d1a0132271
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2227
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\-\>member' : 左側がクラス、構造体、共用体、ジェネリック型へのポインターではありません  
  
 `->` の左側のオペランドがクラス、構造体、または共用体へのポインターではありません。  
  
 次の例では C2227 が生成されます。  
  
```  
// C2227.cpp int *pInt; struct S { public: int member; } s, *pS = &s; int main() { pInt->member = 0;   // C2227 pInt points to an int pS->member = 0;   // OK }  
```