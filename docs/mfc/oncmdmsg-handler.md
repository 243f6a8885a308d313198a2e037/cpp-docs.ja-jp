---
title: "OnCmdMsg ハンドラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OnCmdMsg
dev_langs: C++
helpviewer_keywords:
- messages, routing
- handlers [MFC]
- command routing [MFC], OnCmdMsg handler
- handlers, OnCmdMessage [MFC]
- OnCmdMessage method [MFC]
ms.assetid: 8df07024-506f-47e7-bba9-1c3bc5ad8ab6
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 173741ef73cd4bf6426787ef56e8334f504d7c0e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="oncmdmsg-handler"></a>OnCmdMsg ハンドラー
各コマンド ターゲットを呼び出してコマンドのルーティングを実現する、`OnCmdMsg`次のコマンド ターゲット シーケンス内のメンバー関数。 コマンドの使用対象`OnCmdMsg`コマンドを処理できるかどうかを判断し、処理できない場合は、別のコマンド ターゲットにルーティングします。  
  
 各コマンド ターゲット クラスがオーバーライド可能性があります、`OnCmdMsg`メンバー関数。 上書きは、次の特定のターゲットを各クラスのルート コマンドを使用できます。 フレーム ウィンドウ (ルートなど) 常にコマンドをその現在の子ウィンドウまたはビューの表に示すように[標準のコマンド ルート](../mfc/command-routing.md)です。  
  
 既定値`CCmdTarget`の実装`OnCmdMsg`コマンド ターゲット クラスのメッセージ マップを使用して受信する各コマンド メッセージのハンドラー関数の検索: 標準的なメッセージを検索することと同じ方法でします。 一致が見つかった場合は、ハンドラーを呼び出します。 」で説明されてメッセージ マップ検索[方法、フレームワークのメッセージ マップ検索](../mfc/how-the-framework-searches-message-maps.md)です。  
  
## <a name="see-also"></a>参照  
 [フレームワークがハンドラーを呼び出す方法](../mfc/how-the-framework-calls-a-handler.md)

