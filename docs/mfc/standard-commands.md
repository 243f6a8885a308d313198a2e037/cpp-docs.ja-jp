---
title: "標準コマンド |Microsoft ドキュメント"
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
- File menu
- identifiers [MFC], command IDs
- command IDs, standard commands
- OLE commands
- commands [MFC], standard
- standard command IDs
- Window menu commands
- standard commands
- View menu commands
- Edit menu standard commands
- Help [MFC], menus
- programmer-defined IDs [MFC]
ms.assetid: 88cf3ab4-79b3-4ac6-9365-8ac561036fbf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bbdb763b2d7da04267a195e5d534da9528f2b74d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="standard-commands"></a>標準コマンド
フレームワークでは、多くの標準コマンド メッセージを定義します。 通常、これらのコマンド Id は、形式をとります。  
  
 **Id _** *ソース*_*項目*  
  
 ここで*ソース*、通常はメニュー名と*項目*のメニュー項目。 たとえば、[ファイル] メニューの新しいコマンドのコマンド ID は`ID_FILE_NEW`します。 標準コマンド Id は、ドキュメントで太字で表示されます。 プログラマが定義する Id は、周囲のテキストとは異なるフォントで表示されます。  
  
 サポートされる最も重要なコマンドのいくつかの一覧を次に示します。  
  
 *メニュー、コマンド ファイル*  
 新規、開く、閉じるには、保存、名前を付けて保存、ページ設定、プリンターの設定、印刷、印刷プレビュー、終了時に、最近使ったファイル。  
  
 *[編集] メニューのコマンド*  
 クリア、チェック ボックスをオフすべてであるため、コピー、切り取り、検索、貼り付け、繰り返すには、元に戻す、置換、[すべて選択]、および再実行します。  
  
 *[表示] メニューのコマンド*  
 ツールバーとステータス バーです。  
  
 *[ウィンドウ] メニューのコマンド*  
 新規、配置、連鎖的に水平方向に並べて表示し、垂直方向に並べて表示分割されます。  
  
 *[ヘルプ] メニューのコマンド*  
 インデックスを作成、ヘルプを使用して、バージョン情報。  
  
 *OLE コマンド ([編集] メニュー)*  
 新しいオブジェクト、リンクの編集リンク貼り付け、貼り付け、挿入と*typename*オブジェクト (動詞コマンド)。  
  
 フレームワークは、これらのコマンドのさまざまなレベルのサポートを提供します。 いくつかのコマンドは、他のユーザーが完全に実装でサポートされているときに定義したコマンド Id としてのみサポートされます。 など、フレームワークは、新しいドキュメント オブジェクトを作成する、[開く] ダイアログ ボックスを表示および開くと、ファイルの読み取りを [ファイル] メニュー、[開く] コマンドを実装します。 これに対し、する必要があります [編集] メニューのコマンド自分で実装するなどのコマンドから**ID_EDIT_COPY**をコピーするデータの性質によって異なります。  
  
 詳細についてはサポートされているコマンドと提供される実装のレベルでは、「[テクニカル ノート 22:](../mfc/tn022-standard-commands-implementation.md)です。 標準のコマンドは、コマ ファイルで定義されます。H.  
  
## <a name="see-also"></a>参照  
 [ユーザー インターフェイス オブジェクトとコマンド ID](../mfc/user-interface-objects-and-command-ids.md)

