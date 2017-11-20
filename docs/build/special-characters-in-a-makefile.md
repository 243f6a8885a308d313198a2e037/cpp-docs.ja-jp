---
title: "メイクファイルの特殊文字 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, special characters
- makefiles, special characters
- special characters, in NMAKE macros
- macros, special characters
ms.assetid: 92c34ab5-ca6b-4fc0-bcf4-3172eaeda9f0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 53b2457c87e587b4e1ef13e53bf2dfcdd4800d7f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="special-characters-in-a-makefile"></a>メイクファイルの特殊文字
NMAKE の特殊文字をリテラル文字としてを使用するのには、前にキャレット (^) を配置します。 NMAKE では、その他の文字の前にキャレットを無視します。 特殊文字は次のとおりです。  
  
 `:  ;  #  (  )  $  ^  \  {  }  !  @  —`  
  
 引用符で囲まれた文字列内のキャレット (^) は、リテラルのキャレット文字として扱われます。 行の最後のキャレットは、文字列またはマクロでリテラルの改行文字を挿入します。  
  
 マクロ、円記号で (\\) の後に改行を配置して文字がスペースで置き換えられます。  
  
 コマンドでは、パーセント記号 (%) は、ファイル指定子がします。 コマンドでそのまま % を表すためには、1 つの代わりに二重パーセント記号 (%) を指定します。 他の状況で (nmake の) は解釈します単一の % 文字どおりが常に double 型の値を解釈 %% として単一の % です。 そのため、リテラルを表す %%、いずれか 3 つのパーセント記号を指定 %%%、または 4 つのパーセント記号、%%% です。  
  
 コマンド内のリテラル文字として、ドル記号 ($) を使用するには、2 つのドル記号 ($) を指定します。 このメソッドは、他の状況でも使用できます、^ $ が有効です。  
  
## <a name="see-also"></a>関連項目  
 [メイクファイルの内容](../build/contents-of-a-makefile.md)