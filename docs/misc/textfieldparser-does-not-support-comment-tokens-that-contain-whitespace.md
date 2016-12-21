---
title: "TextFieldParser は空白を含むコメント トークンをサポートしていません | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrTextFieldParser_WhitespaceInToken"
ms.assetid: 55107656-270e-4bbb-841a-478904df8e07
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# TextFieldParser は空白を含むコメント トークンをサポートしていません
空白を含むコメント トークンが指定されています。 トークンの先頭に空白がある場合を除き、`TextFieldParser` は空白を含むコメント トークンをサポートしません。 トークンの先頭にある空白は無視されます。  
  
### このエラーを解決するには  
  
-   適切なコメント トークンを指定します。  
  
## 参照  
 [TextFieldParser.CommentTokens プロパティ](http://msdn.microsoft.com/ja-jp/2e6b6435-4bee-4c14-a353-e8f2c82e2d61)   
 [Parsing Text Files with the TextFieldParser Object](../Topic/Parsing%20Text%20Files%20with%20the%20TextFieldParser%20Object%20\(Visual%20Basic\).md)   
 [TextFieldParser Object](../Topic/TextFieldParser%20Object.md)