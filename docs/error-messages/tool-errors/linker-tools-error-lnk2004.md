---
title: "リンカ ツール エラー LNK2004 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2004
dev_langs: C++
helpviewer_keywords: LNK2004
ms.assetid: 07645371-e67b-4a2c-b0e0-dde24c94ef7e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3fdbd32bbc59d9c18df5544f07ec7e7097b9e02e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2004"></a>リンカ ツール エラー LNK2004
gp 相対 fixup オーバーフローを 'ターゲット';short セクション 'section' が大きすぎるか範囲外です。  
  
 セクションが大きすぎます。  
  
 このエラーを解決するか、#pragma セクション (".sectionname"を読み取り、書き込み、時間の長い) を使用して、長いセクションでデータを明示的に設定しを使用して、短い セクションのサイズを小さく`__declspec(allocate(".sectionname"))`でデータ定義と宣言します。  たとえば、オブジェクトに適用された  
  
```  
#pragma section(".data$mylong", read, write, long)  
__declspec(allocate(".data$mylong"))  
char    rg0[1] = { 1 };  
char    rg1[2] = { 1 };  
char    rg2[4] = { 1 };  
char    rg3[8] = { 1 };  
char    rg4[16] = { 1 };  
char    rg5[32] = { 1 };  
```  
  
 8 バイトであり、長い形式のデータ セクションで、コンパイラが割り当てられますよりも大きいデータのコレクションであるが、独自の構造体に論理的にグループ化されたデータを移動することもできます。  たとえば、オブジェクトに適用された  
  
```  
// from this...  
int     w1  = 23;  
int     w2 = 46;  
int     w3 = 23*3;  
int     w4 = 23*4;  
  
// to this...  
struct X {  
    int     w1;  
    int     w2;  
    int     w3;  
    int     w4;  
} x  = { 23, 23*2, 23*3, 23*4 };  
  
```  
  
 このエラーの致命的なエラーが続く`LNK1165`です。