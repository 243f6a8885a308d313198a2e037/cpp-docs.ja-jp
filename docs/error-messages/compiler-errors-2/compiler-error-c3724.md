---
title: "コンパイラ エラー C3724 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3724"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3724"
ms.assetid: cab8aba7-14fc-406f-8cc6-32744c8f31c1
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3724
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

イベントの複数のスレッド処理を使用する\> 必要があります。の \#include \<windows.h  
  
 イベントでマルチスレッドを使用する場合は、windows.h ファイルが必要です。  このエラーを解決するには、イベント ソースとイベント レシーバーが定義されているファイルの先頭に `#include <windows.h>` を追加します。  
  
```  
// C3724.cpp  
// uncomment the following line to resolve  
// #include <windows.h>  
  
[event_source(native), threading(apartment)]  
class CEventSrc {  
public:  
   __event void event1();   // C3724  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   void handler1() {  
   }  
  
   void HookEvents(CEventSrc* pSrc) {  
      __hook(CEventSrc::event1, pSrc, CEventRec::handler1);  
   }  
  
   void UnhookEvents(CEventSrc* pSrc) {  
      __unhook(CEventSrc::event1, pSrc, CEventRec::handler1);  
   }  
};  
  
int main() {  
}  
```