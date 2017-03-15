---
title: "コンパイラ エラー C2447 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2447"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2447"
ms.assetid: d1bd6e9a-ee42-4510-ae5e-6b0378f7b931
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラ エラー C2447
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'{' : 対応する関数ヘッダーがありません \(旧形式の仮引数リスト?\)  
  
 グローバル スコープで予期しない始め中かっこが見つかりました。  この問題は、ほとんどの場合、形式が正しくない関数のヘッダー、誤った場所にある宣言、または無効なセミコロンが原因で発生します。  この問題を解決するには、始め中かっこの前にある関数ヘッダーの形式が正しいこと、および始め中かっこの前に宣言や無効なセミコロンがないことを確認します。  
  
 このエラーは、旧形式の C 言語仮引数リストが原因で発生する場合もあります。  この問題を解決するには、最新の形式を使用するように、つまり、かっこで囲むように引数リストをリファクタリングします。  
  
 次の例では警告 C2447 が生成されます。  
  
```  
// C2447.cpp  
int c;  
{}       // C2447  
```