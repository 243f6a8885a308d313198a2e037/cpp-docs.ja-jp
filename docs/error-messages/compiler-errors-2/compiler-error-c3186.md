---
title: "コンパイラ エラー C3186 | Microsoft Docs"
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
  - "C3186"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3186"
ms.assetid: 60540c31-b858-4dc0-8736-04a6b432087d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3186
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

多次元ネイティブ配列は使用できません  
  
 ネイティブの多次元配列が正しく宣言されていません。  
  
 次の例では警告 C3186 が生成されます。  
  
```  
// C3186.cpp  
// compile with: /clr  
#using <mscorlib.dll>  
int main()  
{  
   int a[,];   // C3186  
   int b[2][3];   // native multidimension array  
   array<int,2> ^c = new array<int, 2>(2,5);   // managed multidimension array  
}  
```