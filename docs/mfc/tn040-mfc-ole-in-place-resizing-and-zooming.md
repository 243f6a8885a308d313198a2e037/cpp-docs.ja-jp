---
title: "TN040: MFC OLE の埋め込み先サイズ変更とズーム |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.ole
dev_langs: C++
helpviewer_keywords:
- resizing in-place
- TN040
- zooming and in-place activation
- in-place activation, zooming and resizing
ms.assetid: 4d7859bd-0b2e-4254-be62-2735cecf02c6
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b1113da01e58ec00cd4420aab4424b1c20e127e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="tn040-mfcole-in-place-resizing-and-zooming"></a>テクニカル ノート 40: MFC/OLE 埋め込み先サイズ変更とズーム
> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 このメモは、埋め込み先編集に関連する問題と、サーバーが正しいズームを実行および埋め込み先サイズ変更について説明します。 インプレース アクティブ化では、WYSIWYG の概念はそのコンテナーに 1 つの手順をさらを実行とサーバーが相互の連携しほぼ OLE 仕様と同じ方法を具体的には解釈します。  
  
 コンテナーと、インプレース アクティブ化をサポートしているサーバーの間で閉じる操作のためには、さまざまな維持する必要があるエンドユーザーからの期待があります。  
  
-   プレゼンテーションのディスプレイ (に描画するメタファイル、`COleServerItem::OnDraw`オーバーライド) を正確に同じように見えます (する点を除いて編集ツールには表示されません) を編集するため描画されます。  
  
-   コンテナーが拡大表示時に [サーバー] ウィンドウする必要がありますすぎます。  
  
-   コンテナーとサーバーの両方には、同じメトリックを使用してオブジェクトを表示する必要があります。 数に基づくマッピング モードを使用してつまり*論理*インチあたりのピクセル — 物理インチあたりのピクセル、ディスプレイ デバイスに表示するときにします。  
  
> [!NOTE]
>  インプレース アクティブ化のみに適用されるため (リンクされていない) は埋め込まれているアイテムにはズームの埋め込みオブジェクトにのみ適用されます。 両方の Api を参照して、`COleServerDoc`と`COleServerItem`拡大表示するために使用されています。 この二分の理由は、リンクと埋め込みの両方の項目に対して有効では関数のみがである`COleServerItem`(これにより、一般的な実装があります) には埋め込みオブジェクトに対してのみ有効な関数が存在し、 `COleServerDoc`クラス (サーバーの観点からは、`document`が埋め込まれている)。  
  
 サーバーをコンテナーの倍率を認識する、必要に応じて編集インターフェイスを変更する必要があります、負担の大部分は、サーバーの実行者に配置されます。 サーバーが、コンテナーを使用して倍率に決定します。  
  
## <a name="mfc-support-for-zooming"></a>ズームの MFC サポート  
 現在のズームを呼び出すことで決定できます`COleServerDoc::GetZoomFactor`です。 ドキュメントが、インプレース アクティブでないときに呼び出すことが 100% のズーム要素 (または 1 対 1 の比率) で常に発生します。 呼び出すと、インプレース アクティブが 100% 以外のものを返す可能性があります。  
  
 ズームを正しくの例については、MFC OLE サンプルを参照してください。 [HIERSVR](../visual-cpp-samples.md)です。 ズーム イン HIERSVR では複雑にという事実のテキストが、表示テキスト、一般に、スケールを設定しません直線的に (ヒント、表記規則、デザインの幅および高さすべての重要なは複雑になります)。 それでも、HIERSVR ズームを正しく実装するための適切な参照は、そのため、MFC のチュートリアル[SCRIBBLE](../visual-cpp-samples.md) (手順 7)。  
  
 `COleServerDoc::GetZoomFactor`実装からまたはコンテナーから別のメトリックの数に基づいてズームの倍率を決定して`COleServerItem`と`COleServerDoc`クラスです。 つまり、現在のズームは、次の数式によって決定されます。  
  
```  
Position Rectangle (PR) / Container Extent (CE)  
```  
  
 位置の四角形は、コンテナーによって決定されます。 インプレース アクティブ化時に、サーバーに返されるときに`COleClientItem::OnGetItemPosition`が呼び出され、コンテナーの呼び出し、サーバーの場合は更新`COleServerDoc::OnSetItemRects`(への呼び出しに`COleClientItem::SetItemRects`)。  
  
 コンテナーのエクステントを計算するやや複雑です。 コンテナーが呼び出された場合`COleServerItem::OnSetExtent`(への呼び出しに`COleClientItem::SetExtent`)、コンテナーの範囲はこの値をピクセル単位の論理インチあたりのピクセルの数に変換します。 コンテナーは (これは通常の大文字と小文字) SetExtent が呼び出されない場合は、コンテナー エクステントから返されるサイズ`COleServerItem::OnGetExtent`です。 そのため、コンテナーが SetExtent が呼び出されない場合、フレームワーク前提として こと場合は、コンテナーがその呼び出し元が 100% の自然なエクステントの (から返された値**COleServerItem::GetExtent**)。 別の方法を説明したように、フレームワークでは、コンテナーの項目の 100% (でない) が表示されている前提としています。  
  
 重要な点がある`COleServerItem::OnSetExtent`と`COleServerItem::OnGetExtent`のような名前を持つ項目の同じ属性を操作しません。 `OnSetExtent`サーバーにオブジェクトの量が (ズーム倍数) に関係なく、コンテナーに表示されるかを認識させるために呼び出されると`OnGetExtent`はオブジェクトの理想的なサイズを決定するコンテナーによって呼び出されます。  
  
 各 Api に関連する問題を調べることで、わかりやすい画像を取得できます。  
  
## <a name="coleserveritemongetextent"></a>COleServerItem::OnGetExtent  
 この関数は、アイテムの HIMETRIC 単位「自然サイズ」を返す必要があります。 「自然サイズ」と考える最善の方法では、印刷されたときに表示されるサイズとして定義します。 ここで返されるサイズは、特定の項目の内容 (非常によく似たは特定のアイテムの定数、メタファイル) の定数です。 ズームを項目に適用すると、このサイズは変わりません。 通常は変更されません、コンテナーが複数個以下の領域を呼び出して`OnSetExtent`です。 変更の例は、コンテナーによって送信された最後の範囲でテキストを折り返して表示する「余白」容量がない単純なテキスト エディターの可能性があります。 サーバーが、システム レジストリ内のビット OLEMISC_RECOMPOSEONRESIZE を設定する必要があります可能性があります変更する場合は、サーバーは、(このオプションの詳細については、OLE SDK のマニュアルを参照してください)。  
  
## <a name="coleserveritemonsetextent"></a>COleServerItem::OnSetExtent  
 コンテナーが「増減」オブジェクトの表示時に、この関数が呼び出されます。 ほとんどのコンテナーを呼び出しませんこのまったくです。 既定の実装で使用されている 'です' 内のコンテナーから受信した最後の値を格納する`COleServerDoc::GetZoomFactor`上で説明したコンテナーの範囲値を計算するときにします。  
  
## <a name="coleserverdoconsetitemrects"></a>COleServerDoc::OnSetItemRects  
 ドキュメントが、インプレース アクティブである場合にのみ、この関数が呼び出されます。 コンテナーの項目の位置またはアイテムに適用される領域のいずれかを更新するときに呼び出されます。 位置の四角形、前述のとおりズーム率計算の分子を提供します。 呼び出して、項目の位置を変更すること、サーバーに要求できます`COleServerDoc::RequestPositionChange`です。 コンテナーのことがありますまたは呼び出すことによってこの要求に応答しない可能性があります`OnSetItemRects`(への呼び出しに**必要**)。  
  
## <a name="coleserverdocondraw"></a>COleServerDoc::OnDraw  
 メタファイルがのオーバーライドすることによって作成されたことを実現することが重要`COleServerItem::OnDraw`現在のズームに関係なく、正確に同じメタファイルが生成されます。 コンテナーには、必要に応じてメタファイルは拡大縮小します。 これは、ビューの間で重要な相違点`OnDraw`とサーバーのアイテムの`OnDraw`します。 ズーム ビュー ハンドル、項目を作成します、*ズーム可能な*メタファイルを適切なズームを行うには、コンテナーまで状態のままとします。  
  
 実装を使用する、サーバーが正常に動作できることを確認する最善の方法は、`COleServerDoc::GetZoomFactor`文書の場合は、インプレース アクティブです。  
  
## <a name="mfc-support-for-in-place-resizing"></a>MFC で埋め込み先サイズ変更のサポート  
 OLE 2 の仕様」の説明に従って、MFC は完全に埋め込み先サイズ変更のインターフェイスを実装します。 によって、ユーザー インターフェイスがサポートされている、`COleResizeBar`クラス、カスタム メッセージ**WM_SIZECHILD**、および特別な処理でこのメッセージの`COleIPFrameWnd`します。  
  
 フレームワークによって提供されるよりもこのメッセージのさまざまな処理を実装する場合があります。 前述のように、フレームワークがコンテナーの最大サイズを変更するインプレースでの結果を離れる — サーバー、倍率の変更に応答します。 場合は、両方を設定して、コンテナーが反応コンテナー エクステントおよび位置四角形の処理中にその`COleClientItem::OnChangeItemPosition`(への呼び出しの結果として呼び出された`COleServerDoc::RequestPositionChange`)、埋め込み先サイズ変更が、編集中「とは」アイテムの表示中に発生し、ウィンドウです。 場合の処理中に四角形の位置を設定するだけで、コンテナーが反応`COleClientItem::OnChangeItemPosition`ズームの倍率を変更、および「拡大または縮小します」項目が表示されます。  
  
 サーバーは、このネゴシエーションの実行時の動作 (ある程度) に制御できます。 たとえば、スプレッドシート、またはより少ないセルときに表示するユーザー、項目の編集中にウィンドウのサイズ変更、インプレース変える必要があります。 ワード プロセッサは、余白を変更する、"ページ"、ウィンドウと同じですし、新しい余白の折り返し変える必要があります。 サーバーが本来のエクステントを変更することによってこれを実装 (から返されるサイズ`COleServerItem::OnGetExtent`)、サイズ変更が完了するとします。 これは、位置四角形とで同じ倍率が大きくまたは小さく表示領域は、同じ量だけを変更するコンテナーのエクステントの両方により、します。 さらより小さいか、ドキュメントに表示されますによって生成されたメタファイル`OnDraw`です。 ここでは、ドキュメント自体では、ユーザー表示領域での代わりに、アイテムのサイズが変更されます。  
  
 カスタムのサイズ変更を実装し、によって提供されるユーザー インターフェイスを活用することができます`COleResizeBar`オーバーライドすることで、 **WM_SIZECHILD**でメッセージ、`COleIPFrameWnd`クラスです。 仕様の詳細については**WM_SIZECHILD**を参照してください[テクニカル ノート 24](../mfc/tn024-mfc-defined-messages-and-resources.md)です。  
  
## <a name="see-also"></a>参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

