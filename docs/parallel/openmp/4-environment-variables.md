---
title: "4. 環境変数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cef1bac78afbcc8b852c3bd42e0904e1963137c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="4-environment-variables"></a>4.環境変数
OpenMP C および C++ API の環境変数 (または同等のプラットフォーム固有のメカニズム) を説明並列コードの実行を制御します。  環境変数の名前を大文字にする必要があります。 割り当てられている値は大文字と小文字であり、先頭および末尾の空白文字があります。  プログラムが開始した後の値に変更は無視されます。  
  
 環境変数は次のとおりです。  
  
-   **OMP_SCHEDULE**ランタイムのスケジュールの種類とチャンクのサイズを設定します。  
  
-   **OMP_NUM_THREADS**の実行中に使用するスレッドの数を設定します。  
  
-   **OMP_DYNAMIC**有効またはスレッドの数を動的に調整を無効にします。  
  
-   **OMP_NESTED**有効または入れ子になった並列処理を無効にします。  
  
 この章の例では、Unix C シェル (csh) 環境でこれらの変数を設定する方法のみを示します。 Korn シェルと DOS 環境、アクションと同様に、次に示します。  
  
 csh:  
 setenv OMP_SCHEDULE「動的」  
  
 ksh:  
 エクスポート OMP_SCHEDULE =「動的」  
  
 DOS:  
 OMP_SCHEDULE 設定 =「動的」