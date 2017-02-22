---
title: "コンパイラの警告 (レベル 4) C4626 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4626"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4626"
ms.assetid: 7f822ff4-a4a3-4f17-b45b-e8b7b4659a14
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラの警告 (レベル 4) C4626
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'derived class' : 基底クラスの代入演算子がアクセスできないか削除されているため、代入演算子は暗黙的に削除済みとして定義されました  
  
 代入演算子は基底クラスで削除されているかアクセスできないため、派生クラスでは生成されません。  この型のオブジェクトを代入しようとすると、コンパイラ エラーが発生します。  
  
 既定では、この警告はオフに設定されています。  詳細については、「[既定で無効になっているコンパイラ警告](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)」を参照してください。  
  
 次の例では、C4626 を生成し、その修正方法を示しています。  
  
```  
// C4626  
// compile with: /W4  
#pragma warning(default : 4626)  
class B  
{  
// public:  
   B& operator = (const B&)  
   {  
      return *this;  
   }  
};  
  
class D : public B  
{  
  
}; // C4626 - to fix, make B's copy constructor public  
  
int main()  
{  
   D m;  
   D n;  
   // m = n;   // this line will cause an error  
}  
```