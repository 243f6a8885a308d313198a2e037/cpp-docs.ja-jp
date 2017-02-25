---
title: "コンパイラ エラー C2646 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2646"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2646"
ms.assetid: 92ff1f02-5eaf-40a5-8b7a-a682f149e967
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラ エラー C2646
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

グローバルまたは名前空間スコープの匿名構造体または匿名共用体は静的に宣言する必要があります  
  
 匿名構造体または匿名共用体にはグローバル スコープまたは名前空間のスコープがありますが、`static` 宣言されていません。  
  
 次の例では、C2646 を生成し、その修正方法を示しています。  
  
```  
// C2646.cpp  
// compile with: /c  
union { int i; };   // C2646 not static  
  
// OK  
static union { int j; };  
union U { int i; };  
```