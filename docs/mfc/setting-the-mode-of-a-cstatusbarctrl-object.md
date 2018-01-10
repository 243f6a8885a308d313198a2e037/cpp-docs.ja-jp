---
title: "CStatusBarCtrl オブジェクトのモードの設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CStatusBarCtrl
dev_langs: C++
helpviewer_keywords:
- simple mode and status bar controls
- IsSimple method, using
- SetSimple method [MFC]
- status bar controls [MFC], simple and nonsimple modes
- non-simple mode and status bar controls
- CStatusBarCtrl class [MFC], simple and nonsimple modes
ms.assetid: ca6076e5-1501-4e33-8d35-9308941e46c0
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7c954354321d814952ec3ac5ea148cc9177cd0fe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="setting-the-mode-of-a-cstatusbarctrl-object"></a>CStatusBarCtrl オブジェクトのモードの設定
2 つのモードがある、`CStatusBarCtrl`オブジェクト: 単純なと標準です。 ほとんどの場合、ステータス バー コントロールはテキストとアイコン、またはアイコンと共に、1 つ以上の部分があります。 これは標準モードと呼ばれます。 このモードの詳細については、次を参照してください。 [CStatusBarCtrl オブジェクトの区画の初期化](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md)です。  
  
 、ケースが存在するのみ必要がある 1 行のテキストを表示します。 ここでは、単純なモードはニーズに十分です。 モードを変更する、`CStatusBarCtrl`単にオブジェクト、呼び出しを行う、 [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple)メンバー関数。 ステータス バー コントロールは、単純なモードでは後で呼び出すことによって、テキストを設定、 **SetText**メンバー関数、255 の値として渡すと共に、 **nPane**パラメーター。  
  
 使用することができます、 [IsSimple](../mfc/reference/cstatusbarctrl-class.md#issimple)どのモードを判断する関数、`CStatusBarCtrl`オブジェクトします。  
  
> [!NOTE]
>  単純でないが、シンプルに変更されているステータス バーのオブジェクトまたはその逆の場合、ウィンドウがすぐに再描画される場合と、該当する場合、すべてのパートが定義されている自動的に復元されます。  
  
## <a name="see-also"></a>参照  
 [CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

