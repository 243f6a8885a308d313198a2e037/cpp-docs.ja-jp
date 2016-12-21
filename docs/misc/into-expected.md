---
title: "&#39;Into&#39; が必要です | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc36615"
  - "vbc36615"
helpviewer_keywords: 
  - "BC36615"
ms.assetid: 24062dd9-a973-43b6-88d3-c11adc5a3736
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Into&#39; が必要です
`Aggregate`、`Group By`、または `Group Join` 句が指定されていますが、`Into` 演算子がありません。`Into` 演算子を使用して、クエリ結果に適用する集計関数を識別し、グループ化した結果を格納するクエリの結果型のメンバーを識別します \(`Group` 集計関数を使用\)。  
  
 **エラー ID:** BC36615  
  
### このエラーを解決するには  
  
1.  `Into` 演算子を `Aggregate`、`Group By`、または `Group Join` 句に追加します。 次に例を示します。  
  
    ```vb#  
    Dim orders = From order In orderList _ Order By order.OrderDate _ Group By OrderDate = order.OrderDate _ Into OrdersByDate = Group  
    ```  
  
## 参照  
 [Aggregate Clause](../Topic/Aggregate%20Clause%20\(Visual%20Basic\).md)   
 [Group By 句](../Topic/Group%20By%20Clause%20\(Visual%20Basic\).md)   
 [Group Join Clause](../Topic/Group%20Join%20Clause%20\(Visual%20Basic\).md)   
 [Introduction to LINQ in Visual Basic](../Topic/Introduction%20to%20LINQ%20in%20Visual%20Basic.md)   
 [LINQ](../Topic/LINQ%20in%20Visual%20Basic.md)