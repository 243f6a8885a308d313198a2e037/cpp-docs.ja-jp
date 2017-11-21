---
title: "2.7.2.2 firstprivate |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: ece6ff12-2be1-4e4f-866c-d39345fd87b5
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ac868b33e8a53778faa3fba9724974e4af6ffb90
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="2722-firstprivate"></a>2.7.2.2 firstprivate
**Firstprivate**句によって提供される機能のスーパー セットを提供する、**プライベート**句。 構文、 **firstprivate**句を次に示します。  
  
```  
firstprivate(variable-list)  
```  
  
 指定された変数*変数一覧*が**プライベート**句セマンティクス、」の説明に従って[セクション 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) [25] ページ。 初期化または構築は、コンストラクトのスレッドの実行前に、スレッドあたり 1 回実行された場合に発生します。 **Firstprivate** parallel コンストラクトの句、新しいプライベート オブジェクトの初期値は、元のオブジェクトが見つかると、スレッドの parallel コンストラクトの直前に存在する値。 **Firstprivate** work-sharing コンス トラクターの句、work-sharing コンス トラクターを実行する各スレッドの新しいプライベート オブジェクトの初期値が時間内に、ポイントする前に存在する元のオブジェクトの値を同じスレッドでは、work-sharing コンス トラクターが発生します。 さらに、C++ オブジェクトの各スレッドの新しいプライベート オブジェクトは、元のオブジェクトから構築されたコピーです。  
  
 制限、 **firstprivate**句は、次のようにします。  
  
-   指定された変数、 **firstprivate**句が不完全な型または参照型は必要ありません。  
  
-   として指定されているクラス型の変数**firstprivate**あいまいでないアクセス可能なコピー コンス トラクターを持つ必要があります。  
  
-   変数は、並行領域内でプライベートをまたはに表示される、**削減**の句、**並列**ディレクティブを指定することはできません、 **firstprivate**句で、parallel コンストラクトにバインドされる動作共有ディレクティブです。