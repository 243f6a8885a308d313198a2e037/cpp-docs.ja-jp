---
title: "ツール ヒント用 TTN_NEEDTEXT 通知の処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: TTN_NEEDTEXT
dev_langs: C++
helpviewer_keywords:
- TTN_NEEDTEXT message [MFC]
- notifications [MFC], tool tips
- tool tips [MFC], notifications
ms.assetid: d0370a65-21ba-4676-bcc5-8cf851bbb15c
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 26a3b74ca0bc11b169e195599c5172b245cf0529
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="handling-ttnneedtext-notification-for-tool-tips"></a>ツール ヒント用 TTN_NEEDTEXT 通知の処理
一部として[ツール ヒントを有効にする](../mfc/enabling-tool-tips.md)、処理する、 **TTN_NEEDTEXT**オーナー ウィンドウのメッセージ マップに次のエントリを追加することによって、メッセージ。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#40](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_1.cpp)]  
  
 `memberFxn`  
 このボタンのテキストが必要なときに呼び出されるメンバー関数。  
  
 なお、ツール ヒントの ID は常に 0 です。  
  
 とおり、クラス定義でハンドラー関数を宣言します。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#53](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_2.h)]  
  
 ここで斜体のパラメーターがあります。  
  
 `id`  
 通知を送信したコントロールの識別子です。 使用しません。 コントロールの id を取得、 **NMHDR**構造体。  
  
 `pNMHDR`  
 ポインター、 [NMTTDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb760258)構造体。 この構造体についても説明でさらに[体](../mfc/tooltiptext-structure.md)です。  
  
 `pResult`  
 結果コードへのポインターを返す前に設定できます。 **TTN_NEEDTEXT**ハンドラーを無視することができます、`pResult`パラメーター。  
  
 フォーム ビューの通知ハンドラーの例です。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#54](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_3.cpp)]  
  
 呼び出す`EnableToolTips`(から作成されたこのフラグメント`OnInitDialog`)。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#55](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_4.cpp)]  
  
## <a name="see-also"></a>参照  
 [CFrameWnd から派生していないウィンドウのツール ヒント](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

