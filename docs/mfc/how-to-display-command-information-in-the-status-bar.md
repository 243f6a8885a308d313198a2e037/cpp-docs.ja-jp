---
title: "方法: ステータス バーにコマンド情報を表示 |Microsoft ドキュメント"
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
- prompts [MFC]
- displaying command status [MFC]
- status bars [MFC], message area
- status bars [MFC], displaying command information
ms.assetid: de895cbe-61ee-46bf-9787-76b247527d6d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: da836f48592d97b3526c568eb9d9a830428f53a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-display-command-information-in-the-status-bar"></a>ステータス バーにコマンド情報を表示する方法
アプリケーションのスケルトンを作成するアプリケーションのウィザードを実行すると、ツールバーとステータス バーをサポートできます。 アプリケーション ウィザードでの 1 つのオプションは、両方をサポートします。 ステータス バーが存在する場合は、ユーザーは、メニュー項目にポインターを移動すると、アプリケーションがその操作に役立つ情報を自動的に提供します。 アプリケーションは、メニュー項目が強調表示すると自動的にプロンプト文字列とステータス バーに表示します。 たとえば、ときに、ユーザー、ポインター上に移動、**切り取り**コマンドを**編集**] メニューの [ステータス バー、ステータス バーの [メッセージ] 領域で"選択範囲を切り取って、クリップボードに"と表示可能性があります。 プロンプトでは、ユーザーがメニュー項目の目的を理解するのに役立ちます。 これは、ユーザーがツール バー ボタンをクリックしたときにでも動作します。  
  
 プログラムを追加するメニュー項目の表示文字列を定義することで、このステータス バーのヘルプを追加できます。 これを行うには、メニュー エディターのメニュー項目のプロパティを編集するときに、プロンプト文字列を提供します。 定義する文字列は、アプリケーションのリソース ファイルに格納します。説明するコマンドと同じ Id があります。  
  
 既定では、アプリケーションが追加されます`AFX_IDS_IDLEMESSAGE`プログラムが新しいメッセージを待機しているときに表示される標準的な「準備完了」メッセージの ID。 アプリケーション ウィザードで、状況依存のヘルプ オプションを指定する場合、メッセージは「ヘルプについては、F1 キーを押します」に変更します。  
  
## <a name="see-also"></a>参照  
 [メッセージの処理とマップ](../mfc/message-handling-and-mapping.md)

