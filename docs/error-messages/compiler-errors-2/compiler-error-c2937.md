---
title: "コンパイラ エラー C2937 | Microsoft Docs"
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
  - "C2937"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2937"
ms.assetid: 95671ca3-79f7-4b56-a5f2-a92296da1629
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2937
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': type\-class\-id がグローバル typedef として再定義されています  
  
 ジェネリック クラスまたはテンプレート クラスをグローバル `typedef` として使用することはできません。  
  
 次の例では C2937 が生成されます。  
  
```  
// C2937.cpp // compile with: /c template<class T> struct TC { }; typedef int TC<int>;   // C2937 typedef TC<int> c;   // OK  
```  
  
 C2937 は、ジェネリックを使用しているときも発生する場合があります。  
  
```  
// C2937b.cpp // compile with: /clr generic<class T> ref struct GC { }; typedef int GC<int>;   // C2937 typedef GC<int> xx;   // OK  
```