---
title: "&#39;Private&#39; アクセサーを含むため、プロパティを &#39;&lt;propertymodifier&gt;&#39; と宣言できません | Microsoft Docs"
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
  - "vbc31108"
  - "bc31108"
helpviewer_keywords: 
  - "BC31108"
ms.assetid: 74fb36f4-54cd-4fda-bcc6-e965b5c7c37b
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Private&#39; アクセサーを含むため、プロパティを &#39;&lt;propertymodifier&gt;&#39; と宣言できません
`Private` プロパティ プロシージャ \(`Get` または `Set`\) を持つプロパティは [Overridable](../Topic/Overridable%20\(Visual%20Basic\).md) としてマークされます。  
  
 基底クラスのプロパティまたはプロシージャが [Private](../Topic/Private%20\(Visual%20Basic\).md) として宣言されている場合、派生クラスはそのプロパティまたはプロシージャにアクセスできないため、それをオーバーライドできません。 このため、`Private` を `Overridable` と組み合わせて使用することはできません。 これは、プロパティ自体だけでなく、個々のプロパティ プロシージャにも同様に適用されます。  
  
 **エラー ID:** BC31108  
  
### このエラーを解決するには  
  
-   [Property Statement](../Topic/Property%20Statement.md) から `Overridable` キーワードを削除するか、[Get Statement](../Topic/Get%20Statement.md) または [Set Statement](../Topic/Set%20Statement%20\(Visual%20Basic\).md) から `Private` キーワードを削除します。  
  
## 参照  
 [Property プロシージャ](../Topic/Property%20Procedures%20\(Visual%20Basic\).md)   
 [How to: Declare a Property with Mixed Access Levels](../Topic/How%20to:%20Declare%20a%20Property%20with%20Mixed%20Access%20Levels%20\(Visual%20Basic\).md)