---
title: "リンカ ツール エラー LNK2013 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2013
dev_langs: C++
helpviewer_keywords: LNK2013
ms.assetid: 21408e2d-3f56-4d1f-a031-00df70785ed4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8cf88f768f05eee06ae8ffaa66f8de5a9c443f82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2013"></a>リンカ ツール エラー LNK2013
fixup type フィックスアップのオーバーフローです。 ターゲット 'symbol name' が範囲を超えています。  
  
 ターゲット シンボルが命令の位置から離れすぎているため、リンカーは必要なアドレスまたはオフセットを指定された命令に収めることができません。  
  
 この問題を解決するには、複数のイメージを作成するかを使用して、 [/order](../../build/reference/order-put-functions-in-order.md)のため、命令とターゲットは一緒に近いはオプションです。  
  
 シンボルがユーザー定義シンボルであり、コンパイラが生成したシンボルでない場合は、次の処理を実行して、エラーを解決することもできます。  
  
-   静的関数を非静的関数に変更します。  
  
-   静的関数を含むコード セクションを呼び出し側と同じ名前に変更します。  
  
 `DUMPBIN /SYMBOLS` を使用して、関数が静的かどうかを調べます。