---
title: "XML 属性 &#39;attribute1&#39; は、XML 属性 &#39;attribute2&#39; よりも前に存在しなければなりません | Microsoft Docs"
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
  - "bc31157"
  - "vbc31157"
helpviewer_keywords: 
  - "BC31157"
ms.assetid: d8d8769e-533d-454e-b145-99955ce45cc5
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# XML 属性 &#39;attribute1&#39; は、XML 属性 &#39;attribute2&#39; よりも前に存在しなければなりません
XML ドキュメント リテラル内の属性が無効な順序で指定されています。 XML ドキュメント リテラル内の属性の有効な属性順序は、XML 1.0 仕様に基づいています。 たとえば、XML ドキュメント リテラルの `encoding` 属性は、`version` 属性の直後にする必要があります。  
  
 **エラー ID:** BC31157  
  
### このエラーを解決するには  
  
-   XML 1.0 仕様で指定されているガイドラインを使用して、XML ドキュメント リテラルの属性の順序を更新します。  
  
## 参照  
 [XML Literals and the XML 1.0 Specification](../Topic/XML%20Literals%20and%20the%20XML%201.0%20Specification%20\(Visual%20Basic\).md)   
 [XML Document Literal](../Topic/XML%20Document%20Literal%20\(Visual%20Basic\).md)   
 [XML Literals](../Topic/XML%20Literals%20\(Visual%20Basic\).md)   
 [XML](../Topic/XML%20in%20Visual%20Basic.md)