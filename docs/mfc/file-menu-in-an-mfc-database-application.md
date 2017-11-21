---
title: "MFC データベース アプリケーションの [ファイル] メニュー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- File menu
- database applications [MFC], File menu commands
ms.assetid: 92dafb75-c1b3-4860-80a0-87a83bfc36f2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c9e75a88eb4093387317a3cdb84be4b0b73f4201
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="file-menu-in-an-mfc-database-application"></a>MFC データベース アプリケーションの [ファイル] メニュー
MFC データベース アプリケーションを作成してシリアル化を使用しない場合どのようにする必要がある、オープン、クローズを解釈、保存、および名前を付けてコマンドを使ってファイル] メニューの [この質問のスタイル ガイドラインはありませんが、ここでは、いくつか提案します。  
  
-   [ファイル] メニューの [開く] コマンドを完全に排除します。  
  
-   「データベースを開く」として開く コマンドを解釈し、ユーザー、アプリケーションが認識されるデータ ソースの一覧を表示します。  
  
-   名前を付けておそらく、「プロファイルを開きます」[開く] コマンドを解釈します。 含む、彼のユーザーの設定など、「ユーザー プロファイル」の情報を含むシリアル化されたドキュメントを格納するファイルを使用するが、シリアル化されたファイルを開くか (必要に応じてパスワードを除く) 自分のログイン ID と、データ ソースと最も開くを保持します。最近使用したとします。  
  
 MFC アプリケーション ウィザードでは、ドキュメントに関連するファイル メニューのコマンドを持たないアプリケーションの作成をサポートします。 選択、**ファイル サポートのないデータベース ビュー**  オプションを選択、**データベース サポート**ページ。  
  
 特別な方法で、[ファイル] メニュー コマンドを解釈する多くの場合に 1 つまたは複数のコマンド ハンドラーをオーバーライドする必要があります、 `CWinApp`-クラスを派生します。 たとえば、完全にオーバーライドする`OnFileOpen`(を実装する、`ID_FILE_OPEN`コマンド) ことを意味する"データベースを開く:"  
  
-   基本クラスのバージョンを呼び出しません。`OnFileOpen`コマンドのフレームワークの既定の実装を完全に置換するため、します。  
  
-   ハンドラーを使用して、代わりにデータ ソースを一覧表示するダイアログ ボックスを表示します。 このようなダイアログを表示するには呼び出すことによって`CDatabase::OpenEx`または`CDatabase::Open`パラメーターを使用して**NULL**です。 ユーザーのコンピューターですべての利用可能なデータ ソースを表示する ODBC ダイアログ ボックスが開きます。  
  
-   データベース アプリケーションは通常、ドキュメント全体を保存しない、ためにがおそらくを削除する、保存し、シリアル化されたドキュメントを使用してプロファイル情報を格納しない限り実装として保存します。 それ以外の場合、たとえば、「トランザクションをコミットします」[保存] コマンドを実装する場合があります。 参照してください[テクニカル ノート 22:](../mfc/tn022-standard-commands-implementation.md)詳細については、これらのコマンドをオーバーライドします。  
  
## <a name="see-also"></a>関連項目  
 [シリアル化: シリアル化とデータベースの入力/出力](../mfc/serialization-serialization-vs-database-input-output.md)

