---
title: "コンパイラの警告 (レベル 1) C4620 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4620"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4620"
ms.assetid: fed29934-b797-47e8-bbea-c7e5f8dd6e93
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 1) C4620
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

型 'type' に対して後置形式の 'operator \+\+' は見つかりません。前置形式を使用します  
  
 指定した型の後置インクリメント演算子の定義がありません。 コンパイラは、オーバーロードされた前置演算子を使用します。  
  
 この警告は、後置 `++` 演算子を定義することで回避できます。 次に示すように、引数が 2 つのバージョンの `++` 演算子を作成します。  
  
```  
// C4620.cpp // compile with: /W1 class A { public: A(int nData) : m_nData(nData) { } A operator++() { m_nData -= 1; return *this; } // A operator++(int) // { //    A tmp = *this; //    m_nData -= 1; //    return tmp; // } private: int m_nData; }; int main() { A a(10); ++a; a++;   // C4620 }  
```