---
title: "レコード ビュー (MFC データ アクセス) のユーザー インターフェイスの更新 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- user interfaces, updating
- menus, updating as context changes
- record views, user interface
ms.assetid: 2c7914b6-2dc3-40c3-b2f2-8371da2a4063
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: aab6ea73fc5726771877640268c89edea4d0745a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="user-interface-updating-for-record-views--mfc-data-access"></a>レコード ビューのユーザー インターフェイスの更新 (MFC データ アクセス)
`CRecordView`ナビゲーション コマンドに対する既定のユーザー インターフェイス更新ハンドラーを提供します。 これらのハンドラーにより、ユーザー インターフェイス オブジェクト (メニュー項目とツール バー ボタン) の有効/無効が自動的に切り替えられます。 アプリケーションのウィザードは、標準メニューを提供し、選択した場合、**ドッキング可能ツールバー**オプション、コマンドのツール バー ボタンのセット。 `CRecordView` を使用してレコード ビュー クラスを作成する場合は、同じユーザー インターフェイス オブジェクトをアプリケーションに追加することが必要になることがあります。  
  
### <a name="to-create-menu-resources-with-the-menu-editor"></a>エディター メニューを使用してメニュー リソースを作成するには  
  
1.  使用に関する情報を参照し、[メニュー エディター](../windows/menu-editor.md)、4 つのコマンドを独自のメニューを作成します。  
  
#### <a name="to-create-toolbar-buttons-with-the-graphics-editor"></a>グラフィックス エディターを使用してツール バー ボタンを作成するには  
  
1.  使用に関する情報を参照し、[ツール バー エディター](../windows/toolbar-editor.md)、レコード移動コマンド用のツール バー ボタンを追加するツール バー リソースを編集します。  
  
## <a name="see-also"></a>関連項目  
 [レコード ビューのナビゲーションをサポートします。](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)   
 [レコード ビューを使用します。](../data/using-a-record-view-mfc-data-access.md)