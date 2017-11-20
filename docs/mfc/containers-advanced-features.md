---
title: "コンテナー: 拡張機能 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- links [MFC], to embedded OLE objects
- containers [MFC], links to embedded OLE objects
- containers [MFC], advanced features
- container/server applications [MFC]
- embedded objects [MFC]
- OLE controls [MFC], containers
- OLE containers [MFC], advanced features
- server/container applications [MFC]
- containers [MFC], container applications
ms.assetid: 221fd99c-b138-40fa-ad6a-974e3b3ad1f8
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6e55ed4fec962fcafa97b155d8688fcf62c1f2fb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="containers-advanced-features"></a>コンテナー : 高度な機能
この記事では、既存のコンテナー アプリケーションに省略可能な高度な機能を組み込む必要な手順について説明します。 これらの機能は次のとおりです。  
  
-   [コンテナーとサーバーの両方のアプリケーション](#_core_creating_a_container_server_application)  
  
-   [埋め込みオブジェクトへのリンク](#_core_links_to_embedded_objects)  
  
##  <a name="_core_creating_a_container_server_application"></a>コンテナー/サーバー アプリケーションを作成します。  
 コンテナー/サーバー アプリケーションは、コンテナーとサーバーの両方として機能するアプリケーションです。 Windows 用 Microsoft Word では、この例を示します。 Word のドキュメントを他のアプリケーションに埋め込むことができますし、Word のドキュメントにアイテムを埋め込むこともできます。 コンテナーと (組み合わせコンテナー/ミニサーバー アプリケーションを作成することはできません)、フル サーバーの両方であるコンテナー アプリケーションを変更するためのプロセスは、フル サーバーを作成するためのプロセスに似ています。  
  
 アーティクル[サーバー: サーバーの実装](../mfc/servers-implementing-a-server.md)サーバー アプリケーションの実装に必要なタスクの数を一覧表示します。 コンテナー/サーバー アプリケーションにはコンテナー アプリケーションを変換する場合、同じタスクの一部を実行するコードをコンテナーに追加します。 重要な考慮事項を次に示します。  
  
-   アプリケーション ウィザードで既に作成されたコードをコンテナーには、OLE サブシステムを初期化します。 変更または追加をサポートするに対しては何もする必要はありません。  
  
-   ドキュメント クラスの基本クラスの任意の場所は`COleDocument`、基底クラスに変更`COleServerDoc`です。  
  
-   オーバーライド`COleClientItem::CanActivate`インプレース編集するサーバー自体が使用されている場所に項目を編集しないようにします。  
  
     たとえば、MFC OLE サンプル[OCLIENT](../visual-cpp-samples.md)コンテナー/サーバー アプリケーションによって作成されたアイテムが埋め込まれています。 OCLIENT アプリケーションを開くし、インプレースでコンテナー/サーバー アプリケーションによって作成されたアイテムの編集します。 アプリケーションのアイテムを編集している間にする MFC OLE サンプルで作成されたアイテムを埋め込む[HIERSVR](../visual-cpp-samples.md)です。 これを行うには、インプレース アクティブ化を使用することはできません。 完全には、この項目をアクティブ化する HIERSVR を開く必要があります。 Microsoft Foundation Class ライブラリがこの OLE の機能をサポートしていないためにオーバーライド`COleClientItem::CanActivate`すると、このような状況を確認して、アプリケーションで可能な実行時エラーを防ぐことができます。  
  
 新しいアプリケーションを作成してコンテナー/サーバー アプリケーションとして機能する場合は、アプリケーションのウィザードでこのサポート OLE オプション ダイアログ ボックスのオプションが自動的に作成されることを選択します。 詳細については、記事を参照してください。[概要: ActiveX コントロール コンテナーの作成](../mfc/reference/creating-an-mfc-activex-control-container.md)です。 MFC のサンプルについては、MFC のサンプルを参照してください。  
  
 それ自体に MDI アプリケーションを挿入することはできませんに注意してください。 SDI アプリケーションである場合を除き、コンテナー/サーバー アプリケーションをそれ自体に挿入できません。  
  
##  <a name="_core_links_to_embedded_objects"></a>埋め込みオブジェクトへのリンク  
 埋め込みオブジェクトの機能へのリンクは、コンテナー アプリケーション内の埋め込みオブジェクトへのリンクでドキュメントを作成するユーザーを使用できます。 たとえば、スプレッドシートを埋め込むワード プロセッサでドキュメントを作成します。 アプリケーションでは、埋め込みオブジェクトへのリンクをサポートする場合、ワード プロセッサの文書に含まれる、スプレッドシートへのリンクを貼り付けることができます。 この機能は、ワード プロセッサもともと入手がわからなくても、ワークシートに含まれている情報を使用して、アプリケーションを使用します。  
  
#### <a name="to-link-to-embedded-objects-in-your-application"></a>アプリケーション内の埋め込みオブジェクトにリンクするには  
  
1.  ドキュメント クラスを派生させる`COleLinkingDoc`の代わりに`COleDocument`です。  
  
2.  OLE クラス ID の作成 (**CLSID**) OLE 開発ツールに含まれているクラス ID ジェネレーターを使用してアプリケーションにします。  
  
3.  OLE アプリケーションを登録します。  
  
4.  作成、`COleTemplateServer`アプリケーション クラスのメンバーとしてオブジェクト。  
  
5.  アプリケーション クラス`InitInstance`メンバー関数を次の操作します。  
  
    -   接続、`COleTemplateServer`オブジェクトを呼び出して、オブジェクトのドキュメント テンプレートを`ConnectTemplate`メンバー関数。  
  
    -   呼び出す、 **COleTemplateServer::RegisterAll** OLE システム クラスのすべてのオブジェクトに登録します。  
  
    -   `COleTemplateServer::UpdateRegistry` を呼び出す。 唯一のパラメーターを`UpdateRegistry`する必要があります`OAT_CONTAINER`「/埋め込み」スイッチを使用してアプリケーションを起動していない場合。 これは、埋め込みオブジェクトへのリンクをサポートできるコンテナーとして、アプリケーションを登録します。  
  
         「/埋め込み」スイッチを使用して、アプリケーションを起動する場合は、サーバー アプリケーションに似ていますのメイン ウィンドウは表示する必要があります。  
  
 MFC OLE サンプル[OCLIENT](../visual-cpp-samples.md)この機能を実装します。 これを行う方法の例は、次を参照してください。、 `InitInstance` 、OCLIENT 内の関数。このサンプル アプリケーションの CPP ファイルです。  
  
## <a name="see-also"></a>関連項目  
 [コンテナー](../mfc/containers.md)   
 [サーバー](../mfc/servers.md)

