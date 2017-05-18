---
title: "コンパイラ エラー C3894 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3894"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3894"
ms.assetid: 6d5ac903-1dea-431d-8e3a-cebca4342983
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラ エラー C3894
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : initonly スタティック データ メンバーの左辺値は、クラス 'クラス' のクラス コンストラクターでのみ使用することができます  
  
 静的な [initonly](../../dotnet/initonly-cpp-cli.md) データ メンバーは、宣言の位置で左辺値として使用するか、または静的コンストラクター内でのみ使用できます。  
  
 インスタンス \(非静的な\) initonly データ メンバーは、宣言の位置で左辺値として使用するか、またはインスタンス \(非静的な\) コンストラクター内でのみ使用できます。  
  
 次の例では警告 C3894 が生成されます。  
  
```  
// C3894.cpp  
// compile with: /clr  
ref struct Y1 {  
   initonly static int data_var = 0;  
  
public:  
   // class constructor  
   static Y1() {  
      data_var = 99;   // OK  
      System::Console::WriteLine("in static constructor");  
   }  
  
   // not the class constructor  
   Y1(int i) {  
      data_var = i;   // C3894  
   }  
  
   static void Test() {}  
  
};  
  
int main() {  
   Y1::data_var = 88;   // C3894  
   int i = Y1::data_var;  
   Y1 ^ MyY1 = gcnew Y1(99);  
   Y1::Test();  
}  
```