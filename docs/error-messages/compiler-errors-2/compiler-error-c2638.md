---
title: "コンパイラ エラー C2638 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2638"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2638"
ms.assetid: 9d4275e8-406d-455e-afee-3a37799230e0
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2638
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : \_\_based 修飾子がメンバーへのポインターに指定されています。  
  
 `__based` 修飾子は、メンバーへのポインターには使用できません。  
  
 次の例では警告 C2638 が生成されます。  
  
```  
// C2638.cpp  
void *a;  
  
class C {  
public:  
   int i;  
   int j;  
   int func();  
};  
int __based (a) C::* cpi = &C::i;  // C2638  
int (__based (a) C::* cpf)() = &C::func; // c2638  
```