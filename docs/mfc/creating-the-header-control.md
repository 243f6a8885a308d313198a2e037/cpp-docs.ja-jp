---
title: "ヘッダー コントロールの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CHeaderCtrl class [MFC], creating
- header controls [MFC], creating
ms.assetid: 7864d9d2-4a2c-4622-b58b-7b110a1e28d2
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 33f536a86a21e56eb36e546109f916ae5d6ca806
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="creating-the-header-control"></a>ヘッダー コントロールの作成
ヘッダー コントロールがダイアログ エディターで直接使用できます (ただし、ヘッダー コントロールが含まれるリスト コントロールを追加することができます)  
  
### <a name="to-put-a-header-control-in-a-dialog-box"></a>ヘッダー コントロール ダイアログ ボックスに配置するには  
  
1.  型のメンバー変数を手動で埋め込む[CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)ダイアログ クラスにします。  
  
2.  [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)作成、およびスタイルを設定、 `CHeaderCtrl`、配置、および表示します。  
  
3.  ヘッダー コントロールに項目を追加します。  
  
4.  ダイアログ クラスのハンドラー関数にマップする任意のヘッダー コントロール通知メッセージのプロパティ ウィンドウで、処理する (を参照してください[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md))。  
  
### <a name="to-put-a-header-control-in-a-view-not-a-clistview"></a>ヘッダー コントロール ビュー (CListView ではない) に配置するには  
  
1.  埋め込み、 [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)ビュー クラス内のオブジェクト。  
  
2.  スタイル、位置、およびビューのヘッダー コントロールのウィンドウを表示[フィルターと並べ替え順序](../mfc/reference/cview-class.md#oninitialupdate)メンバー関数。  
  
3.  ヘッダー コントロールに項目を追加します。  
  
4.  ビュー クラスのハンドラー関数にマップする任意のヘッダー コントロール通知メッセージのプロパティ ウィンドウで、処理する (を参照してください[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md))。  
  
 どちらの場合は、ビューまたはダイアログのオブジェクトが作成されると、埋め込まれたコントロール オブジェクトが作成されます。 呼び出す必要があります[CHeaderCtrl::Create](../mfc/reference/cheaderctrl-class.md#create)コントロール ウィンドウを作成します。 コントロールを配置するには、呼び出す[わけ](../mfc/reference/cheaderctrl-class.md#layout)コントロールの初期サイズと位置を決定して[SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos)を目的の位置を設定します。 」の説明に従って、項目を追加[ヘッダー コントロールへの項目の追加](../mfc/adding-items-to-the-header-control.md)です。  
  
 詳細については、次を参照してください。[ヘッダー コントロールの作成](http://msdn.microsoft.com/library/windows/desktop/bb775238)Windows SDK に含まれています。  
  
## <a name="see-also"></a>参照  
 [CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

