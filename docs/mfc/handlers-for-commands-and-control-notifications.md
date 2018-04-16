---
title: "コマンドとコントロール通知のハンドラー |Microsoft ドキュメント"
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
- commands [MFC], handlers for
- functions [MFC], handler
- handlers [MFC]
- controls [MFC], notifications
- handlers [MFC], control notification [MFC]
- notifications [MFC], handlers for control
- handlers [MFC], command
ms.assetid: 20f57f4a-f577-4c09-80a2-43faf32a1c2e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 748bdd1a2ce6b94a2c935df94de68767ee36875e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="handlers-for-commands-and-control-notifications"></a>コマンドとコントロール通知のハンドラー
コマンドまたはコントロール通知メッセージの既定のハンドラーはありません。 したがって、これらのカテゴリのメッセージのハンドラーの名前付け規則でのみバインドされます。 コマンドまたはコントロールの通知をハンドラーにマップするときに、[プロパティ] ウィンドウは、コマンドの ID またはコントロール通知のコードに基づく名前を提案します。 提案された名前を受け入れる、変更するか、または置換できます。  
  
 規則は、それらが表すユーザー インターフェイス オブジェクトの両方のカテゴリ内のハンドラーを付けることをお勧めします。 したがって、[編集] メニューの [切り取り] コマンドのハンドラーという名前  
  
 [!code-cpp[NVC_MFCMessageHandling#4](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_1.h)]  
  
 コマンド ID として [切り取り] コマンドを使わため切り取りコマンドは、アプリケーションで、 **ID_EDIT_CUT**です。 定義済みのすべてのコマンド Id の一覧は、コマ ファイルを参照してください。H. 詳細については、次を参照してください。[標準コマンド](../mfc/standard-commands.md)です。  
  
 さらに、規則がのハンドラーを提案、 **BN_CLICKED** "My Button"というラベルの付いたボタンからの通知メッセージの名前を指定する場合があります  
  
 [!code-cpp[NVC_MFCMessageHandling#5](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_2.h)]  
  
 このコマンドの ID を割り当てることが`IDC_MY_BUTTON`をアプリケーションに固有のユーザー インターフェイス オブジェクトと等価であるためです。  
  
 メッセージの両方のカテゴリは、引数を受け取らずし、値を返しません。  
  
## <a name="see-also"></a>参照  
 [メッセージ ハンドラー関数の宣言](../mfc/declaring-message-handler-functions.md)
