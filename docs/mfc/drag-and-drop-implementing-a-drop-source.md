---
title: "ドラッグ アンド ドロップ: ドロップ ソースの実装 |Microsoft ドキュメント"
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
- OLE drag and drop [MFC], initiating drag operations
- drag and drop [MFC], calling DoDragDrop
- OLE drag and drop [MFC], drop source
- OLE drag and drop [MFC], calling DoDragDrop
- drag and drop [MFC], initiating drag operations
- drag and drop [MFC], drop source
ms.assetid: 0ed2fda0-63fa-4b1e-b398-f1f142f40035
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 301980f7f5a901aa4e2cba40357b18311eef581e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="drag-and-drop-implementing-a-drop-source"></a>ドラッグ アンド ドロップ: ドロップ ソースの実装
この記事では、ドラッグ アンド ドロップ操作にデータを提供するアプリケーションを取得する方法について説明します。  
  
 ドロップ ソースの基本的な実装では、比較的単純です。 最初の手順では、どのようなイベントは、ドラッグ操作の開始を決定します。 ユーザー インターフェイス ガイドライン データの選択としては、ドラッグ操作の先頭を定義することをお勧めおよび`WM_LBUTTONDOWN`選択したデータ内のポイントで発生するイベントです。 MFC OLE サンプル[OCLIENT](../visual-cpp-samples.md)と[HIERSVR](../visual-cpp-samples.md)これらのガイドラインに従ってください。  
  
 アプリケーションが、コンテナーと、選択したデータは、リンクまたは型の埋め込みオブジェクト`COleClientItem`、呼び出すその`DoDragDrop`メンバー関数。 それ以外の場合、構築、`COleDataSource`オブジェクトし、選択内容の初期化、データ ソース オブジェクトの`DoDragDrop`メンバー関数。 アプリケーションがサーバーの場合を使用して`COleServerItem::DoDragDrop`です。 標準的なドラッグ アンド ドロップの動作をカスタマイズする方法の詳細については、記事を参照してください。[ドラッグ アンド ドロップ: カスタマイズ](../mfc/drag-and-drop-customizing.md)です。  
  
 場合`DoDragDrop`返します`DROPEFFECT_MOVE`、ソース データをすぐに、ソース ドキュメントから削除します。 他の戻り値の`DoDragDrop`ドロップ ソースに影響がありません。  
  
 詳細については次を参照してください:  
  
-   [ドロップ ターゲットの実装](../mfc/drag-and-drop-implementing-a-drop-target.md)  
  
-   [カスタマイズのドラッグ アンド ドロップ](../mfc/drag-and-drop-customizing.md)  
  
-   [作成と破棄 OLE データ オブジェクトとデータ ソース](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [OLE データ オブジェクトとデータ ソースを操作します。](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## <a name="see-also"></a>参照  
 [ドラッグ アンド ドロップ (OLE)](../mfc/drag-and-drop-ole.md)   
 [された](../mfc/reference/coledatasource-class.md#dodragdrop)   
 [クラス](../mfc/reference/coleclientitem-class.md#dodragdrop)   
 [CView::OnDragLeave](../mfc/reference/cview-class.md#ondragleave)

