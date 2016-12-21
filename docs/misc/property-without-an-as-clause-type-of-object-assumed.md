---
title: "&#39;As&#39; 句のないプロパティです。Object の型と見なされます | Microsoft Docs"
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
  - "BC42022"
  - "vbc42022"
helpviewer_keywords: 
  - "BC42022"
ms.assetid: 3379692b-8278-4488-878a-0afb76e554b1
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;As&#39; 句のないプロパティです。Object の型と見なされます
プロパティ宣言は `As` 句を指定していません。  
  
 `As` 句は、プログラミング要素に関連するデータ型を指定します。[Property Statement](../Topic/Property%20Statement.md) で、この句はプロパティの `Get` プロシージャが呼び出し元のコードに返す値のデータ型を指定します。`Property` ステートメントに `As` 句を含めない場合、プロパティのデータ型は既定で `Object` になります。  
  
 既定では、このメッセージは警告です。 警告を非表示にする方法や、警告をエラーとして扱う方法の詳細については、「[Visual Basic での警告の構成](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md)」を参照してください。  
  
 **エラー ID:** BC42022  
  
### このエラーを解決するには  
  
-   `Property` ステートメントに `As` 句を含めて、プロパティのデータ型を指定します。  
  
## 参照  
 [Property プロシージャ](../Topic/Property%20Procedures%20\(Visual%20Basic\).md)   
 [Property Statement](../Topic/Property%20Statement.md)   
 [Get Statement](../Topic/Get%20Statement.md)