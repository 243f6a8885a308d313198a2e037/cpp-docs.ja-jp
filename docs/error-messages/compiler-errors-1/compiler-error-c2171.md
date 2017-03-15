---
title: "コンパイラ エラー C2171 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2171"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2171"
ms.assetid: a80343b5-ab3f-4413-b6f1-3ce9d7e519e5
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラ エラー C2171
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator': 型 'type' のオペランドが無効です  
  
 単項演算子が無効なオペランド型で使用されています。  
  
## 使用例  
 次の例では C2171 が生成されます。  
  
```  
// C2171.cpp int main() { double d, d1; d = ~d1;   // C2171 // OK int d2 = 0, d3 = 0; d2 = ~d3; }  
```  
  
## 使用例  
 次の例では C2171 が生成されます。  
  
```  
// C2171_b.cpp // compile with: /c class A { public: A() { STF( &A::D ); } void D() {} void DTF() { (*TF)();   // C2171 (this->*TF)();   // OK } void STF(void (A::*fnc)()) { TF = fnc; } private: void (A::*TF)(); };  
```