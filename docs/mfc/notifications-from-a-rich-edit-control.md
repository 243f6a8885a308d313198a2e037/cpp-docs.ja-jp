---
title: "エディット コントロールのリッチからの通知 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- messages [MFC], notification [MFC]
- CRichEditCtrl class [MFC], notifications
- rich edit controls [MFC], notifications
- notifications [MFC], from CRichEditCtrl
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fcfcb2e4fe333db1ed629489b405255d4ab050b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="notifications-from-a-rich-edit-control"></a>リッチ エディット コントロールからの通知メッセージ
レポートの編集コントロールのリッチに影響するイベントの通知メッセージ ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md))。 親ウィンドウにより処理可能または、メッセージ リフレクションを使用して、リッチで編集コントロール自体。 リッチ エディット コントロールでは、エディット コントロールに加えて、さらにいくつか使用する通知メッセージのすべてをサポートします。 通知メッセージ、リッチ エディット コントロール親ウィンドウに送る mask を設定して、"イベントです"を指定できます。  
  
 リッチ エディット コントロールのイベント マスクを設定するには、使用、 [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask)メンバー関数。 使用して、リッチ エディット コントロールの現在のイベント マスクを取得することができます、 [GetEventMask](../mfc/reference/cricheditctrl-class.md#geteventmask)メンバー関数。  
  
 次の段落には、いくつかの特定の通知とその用途が一覧表示します。  
  
-   **EN_MSGFILTER**処理、 **EN_MSGFILTER**通知により、クラス、豊富ないずれかのコントロールまたはその親ウィンドウを編集、すべてのキーボードをフィルター処理、およびマウスをコントロールに入力します。 ハンドラーは、キーボードまたはマウスのメッセージが処理するを防ぐことができますか、指定した変更することにより、メッセージを変更できます[MSGFILTER](http://msdn.microsoft.com/library/windows/desktop/bb787936)構造体。  
  
-   **EN_PROTECTED**処理、 **EN_PROTECTED**通知メッセージをユーザーが保護されたテキストを変更しようとしたときを検出します。 保護されているテキストの範囲をマークして、保護されている文字の効果を設定できます。 詳細については、次を参照してください。[リッチ エディット コントロールの文字書式](../mfc/character-formatting-in-rich-edit-controls.md)です。  
  
-   **EN_DROPFILES**を処理することで、リッチ エディット コントロール内のファイルを削除するユーザーを有効にすることができます、 **EN_DROPFILES**通知メッセージです。 指定した[ENDROPFILES](http://msdn.microsoft.com/library/windows/desktop/bb787895)構造が削除されているファイルに関する情報を格納します。  
  
-   **EN_SELCHANGE**処理することで、現在の選択が変更されたときにアプリケーションを検出できます、 **EN_SELCHANGE**通知メッセージです。 通知メッセージを指定します、 [SELCHANGE](http://msdn.microsoft.com/library/windows/desktop/bb787952)新しい選択に関する情報を含む構造体。  
  
## <a name="see-also"></a>参照  
 [CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

