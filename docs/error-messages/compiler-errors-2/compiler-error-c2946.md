---
title: "コンパイラ エラー C2946 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2946"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2946"
ms.assetid: c86dfbfc-7702-4f09-8a53-d205710e99c2
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C2946
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

明示的なインスタンス生成。'class' はテンプレート クラスの特殊化ではありません  
  
 非テンプレート クラスは明示的にインスタンス化できません。  
  
## 使用例  
 次の例では C2946 が生成されます。  
  
```  
// C2946.cpp class C {}; template C;  // C2946 int main() {}  
```