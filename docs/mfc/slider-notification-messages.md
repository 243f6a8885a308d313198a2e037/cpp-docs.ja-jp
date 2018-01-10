---
title: "スライダー コントロールの通知メッセージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CSliderCtrl class [MFC], notifications
- slider controls [MFC], notification messages
- messages, notification
- notifications [MFC], CSliderCtrl
ms.assetid: b9121104-3889-4a10-92bf-f3723f1af9d0
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3a4fc9e9065017e04b6375d1e5a8e336d4366755
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="slider-notification-messages"></a>スライダー コントロールの通知メッセージ
スライダー コントロールの親を送信することによってユーザーの操作の親ウィンドウに通知`WM_HSCROLL`または`WM_VSCROLL`スライダー コントロールの向きに応じて、メッセージ。 これらのメッセージを処理するためのハンドラーを追加、`WM_HSCROLL`と`WM_VSCROLL`メッセージを親ウィンドウ。 [OnHScroll](../mfc/reference/cwnd-class.md#onhscroll)と[OnVScroll](../mfc/reference/cwnd-class.md#onvscroll)メンバー関数は、スライダーとへのポインターの位置で、通知コードに渡される、 [CSliderCtrl](../mfc/reference/csliderctrl-class.md)オブジェクト。 ポインター型の**関数\***を指しているにもかかわらず、`CSliderCtrl`オブジェクト。 スライダー コントロールを操作する必要がある場合は、このポインターをキャストする必要があります。  
  
 スクロール バーの通知コードを使用するではなくは、スライダー コントロールは、通知コードの異なるセットを送信します。 スライダー コントロールの送信、 **TB_BOTTOM**、 **TB_LINEDOWN**、 **TB_LINEUP**、および**TB_TOP**通知コードは、ユーザーが操作する場合にのみキーボードを使用して、スライダー コントロール。 **TB_THUMBPOSITION**と**TB_THUMBTRACK**通知メッセージが送信されるときのみ、ユーザーがマウスを使用しています。 **TB_ENDTRACK**、 **TB_PAGEDOWN**、および**TB_PAGEUP**通知コードは、どちらの場合も送信されます。  
  
 次の表には、スライダー コントロールの通知メッセージと送信される通知を発生させるイベント (仮想キー コードまたはマウス イベント) が一覧表示します。 (標準の仮想キー コードの一覧は、Winuser.h を参照してください)。  
  
|通知メッセージ|イベント通知が送信されるが|  
|--------------------------|-------------------------------------------|  
|**TB_BOTTOM**|**VK_END**|  
|**TB_ENDTRACK**|`WM_KEYUP`(ユーザーは、関連する仮想キー コードを送信するキーをリリース)|  
|**TB_LINEDOWN**|**VK_RIGHT**または**VK_DOWN**|  
|**TB_LINEUP**|**VK_LEFT**または**VK_UP**|  
|**TB_PAGEDOWN**|**VK_NEXT** (ユーザーがクリックしたつまみの右側または下のチャネル)|  
|**TB_PAGEUP**|**VK_PRIOR** (ユーザーがクリックしたチャネルの上またはつまみの左側に)|  
|**TB_THUMBPOSITION**|`WM_LBUTTONUP`次の**TB_THUMBTRACK**通知メッセージ|  
|**TB_THUMBTRACK**|スライダーの移動 (ユーザーは、スライダーをドラッグして)|  
|**TB_TOP**|**VK_HOME**|  
  
## <a name="see-also"></a>参照  
 [CSliderCtrl の使い方](../mfc/using-csliderctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

