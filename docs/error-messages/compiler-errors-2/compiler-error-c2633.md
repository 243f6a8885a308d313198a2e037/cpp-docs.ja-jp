---
title: "コンパイラ エラー C2633 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2633"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2633"
ms.assetid: a7aceb65-4255-42d6-a8fb-e3cb6c4d2270
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2633
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 'inline' のみがコンストラクターの正しいストレージ クラスです。  
  
 コンストラクターがインライン以外のストレージ クラスで宣言されています。  
  
 次の例では警告 C2633 が生成されます。  
  
```  
// C2633.cpp  
// compile with: /c  
class C {  
   extern C();   // C2633, not inline  
   inline C();   // OK  
};  
```