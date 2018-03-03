---
title: "既定のコントロール イベント |Microsoft ドキュメント"
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
helpviewer_keywords:
- Dialog editor, default control events
- controls [C++], default control events
- events [C++], controls
- dialog box controls, events
ms.assetid: 75556b23-18f5-4390-97a4-2ecad3309741
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 83c7b6e4d019b895973345805027d428d7af766d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="default-control-events"></a>既定のコントロール イベント
次のコントロール名では、既定のイベントがあります。  
  
|コントロール名|既定のイベント|  
|------------------|-------------------|  
|アニメーション化|**ACN_START**|  
|チェック ボックス|**BN_CLICKED**|  
|コンボ ボックス|**CBN_SELCHANGE**|  
|カスタム|**TTN_GETDISPINFO**|  
|日時指定コントロール|**DTN_DATETIMECHANGE**|  
|エディット ボックス|**EN_CHANGE**|  
|グループ ボックス|(適用なし)|  
|ホット キー|**NM_OUTOFMEMORY**|  
|IP アドレス|**IPN_FIELDCHANGED**|  
|リスト|**LVN_ITEMCHANGE**|  
|リスト ボックス|**LBN_SELCHANGE**|  
|月間予定表|**MCN_SELCHANGE**|  
|画像コントロール|(適用なし)|  
|進行状況|**NM_CUSTOMDRAW**|  
|プッシュ ボタン|**BN_CLICKED**|  
|オプション ボタン|**BN_CLICKED**|  
|リッチ エディット|**EN_CHANGE**|  
|スクロール バー|**NM_THEMECHANGED**|  
|スライダー|**NM_CUSTOMDRAW**|  
|スピン|**UDN_DELTAPOS**|  
|静的なテキスト|(適用なし)|  
|タブ|**TCN_SELCHANGE**|  
|ツリー|**TVN_SELCHANGE**|  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
## <a name="requirements"></a>必要条件  
 Win32  
  
## <a name="see-also"></a>参照  
 [ダイアログ コントロールのメンバー変数を定義します。](../windows/defining-member-variables-for-dialog-controls.md)   
 [ユーザー インターフェイス オブジェクトに関連付けられているメッセージの種類](../mfc/reference/message-types-associated-with-user-interface-objects.md)   
 [メッセージ ハンドラーの編集](../mfc/reference/editing-a-message-handler.md)   
 [リフレクション メッセージ用のメッセージ ハンドラーの定義](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md)   
 [新しいコントロール クラスに基づいた変数を宣言します。](../mfc/reference/declaring-a-variable-based-on-your-new-control-class.md)   
 [仮想関数のオーバーライド](../ide/overriding-a-virtual-function-visual-cpp.md)

