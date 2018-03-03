---
title: "クラスのドキュメント |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.document
dev_langs:
- C++
helpviewer_keywords:
- document classes [MFC]
ms.assetid: 4bf19b02-0a4f-4319-b68e-cddcba2705cb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5a2436b46b7486bd30398dffc530d2adea3d2e48
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="document-classes"></a>ドキュメント クラス
ドキュメント テンプレート オブジェクトによって作成された、ドキュメント クラスのオブジェクトは、アプリケーションのデータを管理します。 これらのクラスのいずれかから、ドキュメントのクラスが派生されます。  
  
 ドキュメント クラスのオブジェクトは、オブジェクトの表示と対話します。 ビュー オブジェクトは、ウィンドウのクライアント領域を表す、ドキュメントのデータを表示およびサービスと対話するユーザーを許可します。 ドキュメントとビューは、ドキュメント テンプレート オブジェクトによって作成されます。  
  
 [CDocument](../mfc/reference/cdocument-class.md)  
 アプリケーション固有のドキュメントの基底クラスです。 ドキュメント クラスまたはクラスから派生**CDocument**です。  
  
 [COleDocument](../mfc/reference/coledocument-class.md)  
 複合ドキュメントの実装、および基本的なコンテナー サポートに対して使用されます。 派生したクラスのコンテナーとして機能する[CDocItem](../mfc/reference/cdocitem-class.md)です。 このクラスは、文書化しの基本クラスは、コンテナーの基底クラスとして使用できる`COleServerDoc`です。  
  
 [直接](../mfc/reference/colelinkingdoc-class.md)  
 派生したクラス`COleDocument`をリンクするため、インフラストラクチャを提供します。 代わりにこのクラスから、コンテナー アプリケーションのドキュメント クラスを派生させる必要があります`COleDocument`埋め込みオブジェクトへのリンクをサポートするようにする場合。  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 リッチ エディット コントロールに含まれる OLE クライアント アイテムの一覧を保持します。 と共に使用[CRichEditView](../mfc/reference/cricheditview-class.md)と[CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)です。  
  
 [COleServerDoc](../mfc/reference/coleserverdoc-class.md)  
 サーバー アプリケーションのドキュメント クラスの基底クラスとして使用します。 `COleServerDoc`オブジェクトとの対話を通じてサーバーのサポートの大部分を提供する[COleServerItem](../mfc/reference/coleserveritem-class.md)オブジェクト。 ビジュアル編集機能は、クラス ライブラリのドキュメント/ビュー アーキテクチャを使用して提供されます。  
  
 [関数](../mfc/reference/chtmleditdoc-class.md)  
 で[CHtmlEditView](../mfc/reference/chtmleditview-class.md)、MFC ドキュメント/ビュー アーキテクチャのコンテキストで WebBrowser HTML 編集プラットフォームの機能です。  
  
## <a name="related-classes"></a>関連するクラス  
 ドキュメント クラスのオブジェクトを永続的なことができる — をストレージ メディアへの状態を記述し、それを読み出すのつまり、します。 MFC には、`CArchive`をストレージ メディアのドキュメントのデータの転送を容易にするクラス。  
  
 [CArchive](../mfc/reference/carchive-class.md)  
 連携して、 [CFile](../mfc/reference/cfile-class.md)シリアル化を使用したオブジェクトの永続的なストレージを実装するオブジェクト (を参照してください[cobject::serialize](../mfc/reference/cobject-class.md#serialize))。  
  
 ドキュメントは、OLE オブジェクトを含めることもできます。 `CDocItem`サーバーとクライアントの項目の基本クラスです。  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 抽象基本クラスの[COleClientItem](../mfc/reference/coleclientitem-class.md)と[COleServerItem](../mfc/reference/coleserveritem-class.md)です。 派生したクラスのオブジェクトを`CDocItem`文書の一部を表します。  
  
## <a name="see-also"></a>参照  
 [クラスの概要](../mfc/class-library-overview.md)

