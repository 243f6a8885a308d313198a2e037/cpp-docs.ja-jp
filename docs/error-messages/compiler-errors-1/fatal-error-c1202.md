---
title: "致命的なエラー C1202 | Microsoft Docs"
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
  - "C1202"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1202"
ms.assetid: c859adb8-17a7-4fa1-a1f3-5820b7bf3849
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 致命的なエラー C1202
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

再帰的な型の指定または関数の依存関係が複雑すぎます。  
  
 テンプレート定義が再帰的であるか、複雑さの制限を超えました。  
  
## 使用例  
 次の例では C1202 が生成されます。  
  
```  
// C1202.cpp // processor: x86 IPF template<int n> class Factorial : public Factorial<n-1>  {   // C1202 public: operator int () { return Factorial <n-1>::operator int () * n; } }; Factorial<7> facSeven;  
```  
  
## 使用例  
 考えられる解決策。  
  
```  
// C1202b.cpp // compile with: /c template<int n> class Factorial : public Factorial<n-1> { public: operator int () { return Factorial <n-1>::operator int () * n; } }; template <> class Factorial<0> { public: operator int () { return 1; } }; Factorial<7> facSeven;  
```