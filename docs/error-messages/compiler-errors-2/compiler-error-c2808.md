---
title: "コンパイラ エラー C2808 | Microsoft Docs"
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
  - "C2808"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2808"
ms.assetid: 3d745102-d3b3-4735-a7d2-ad42d5bf3cfa
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2808
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

unary 'operator operator' が規定より多くのパラメーターを伴って宣言されています。  
  
 単項演算子に void 型でないパラメーター リストが指定されています。  
  
 次の例では警告 C2808 が生成されます。  
  
```  
// C2808.cpp  
// compile with: /c  
class X {  
public:  
   X operator! ( X );   // C2808 nonvoid parameter list  
   X operator! ( void );   // OK  
};  
  
```