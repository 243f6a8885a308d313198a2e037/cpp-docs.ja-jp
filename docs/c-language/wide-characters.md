---
title: "ワイド文字 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ワイド文字"
ms.assetid: 165c4a12-8ab9-45fb-9964-c55e9956194c
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# ワイド文字
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.1.3.4** 複数の文字を含む整数文字定数、または、複数のマルチバイト文字を含むワイド文字定数の値  
  
 通常の文字定数 'ab' は、整数値 \(int\)0x6162 を持ちます。  1 バイトを超える場合は、以前に読み取られたバイトが **CHAR\_BIT** の値だけ左にシフトされ、次のバイトがビットごとの OR 演算子を使用して **CHAR\_BIT** 分の下位ビットと比較されます。  マルチバイト文字定数のバイト数は sizeof \(int\) を超えることはできません。これは 32 ビット対象のコードでは 4 です。  
  
 マルチバイト文字定数は、上記のように読み取られ、これが `mbtowc` ランタイム関数を使用してワイド文字定数に変換されます。  結果が有効なワイド文字定数でない場合は、エラーが発行されます。  いずれの場合も、`mbtowc` 関数でチェックするバイト数は `MB_CUR_MAX` の値に制限されます。  
  
## 参照  
 [文字](../c-language/characters.md)