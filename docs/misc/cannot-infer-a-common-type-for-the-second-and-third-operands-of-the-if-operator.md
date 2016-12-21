---
title: "&#39;If&#39; 演算子の 2 番目と 3 番目のオペランドの共通型を推定できません | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc33106"
  - "bc33106"
helpviewer_keywords: 
  - "BC33106"
ms.assetid: 793eed88-a9f9-43e3-b657-c16795ecbbcc
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;If&#39; 演算子の 2 番目と 3 番目のオペランドの共通型を推定できません
'If' 演算子の 2 番目と 3 番目のオペランドの共通型を推定できません。 一方が他方に対する拡大変換を持つ必要があります。  
  
 3 つの引数を指定して `If` 演算子が呼び出される場合、2 番目と 3 番目の引数の間に拡大変換が存在している必要があります。 たとえば、`Integer` と `String` の間にはどちらの方向にも拡大変換がないため、次のコードではこのエラーが発生します。  
  
```vb#  
Dim divisor = 3  
' Not valid.  
' Console.WriteLine(If(divisor <> 0, number \ divisor, "Division by zero"))  
```  
  
 **エラー ID:** BC33106  
  
### このエラーを解決するには  
  
-   可能であれば、いずれか 1 つのオペランドの明示的な変換をコードの中で記述します。  
  
-   `If...Then...Else` ステートメントなど、別の条件構造を使用します。  
  
## 参照  
 [If Operator](../Topic/If%20Operator%20\(Visual%20Basic\).md)   
 [If...Then...Else Statement](../Topic/If...Then...Else%20Statement%20\(Visual%20Basic\).md)   
 [Widening and Narrowing Conversions](../Topic/Widening%20and%20Narrowing%20Conversions%20\(Visual%20Basic\).md)