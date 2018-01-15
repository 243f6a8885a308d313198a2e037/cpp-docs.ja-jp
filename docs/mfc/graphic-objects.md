---
title: "グラフィック オブジェクト |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- HRGN
- HFONT
- HBITMAP
dev_langs: C++
helpviewer_keywords:
- CRgn class [MFC], HRGN handle type
- HPEN [MFC]
- objects [MFC], graphic
- palettes [MFC], creating in device context
- pens [MFC], creating in device context
- bitmaps [MFC], creating in device contexts
- palette objects [MFC]
- memory [MFC], display contexts
- MFC, graphic objects
- regions [MFC], creating in device context
- CPen class [MFC], HPEN handle type
- GDI objects [MFC]
- HRGN [MFC]
- graphic objects [MFC]
- GDI objects [MFC], graphic-object classes
- CFont class [MFC], HFONT handle type
- HFONT and class CFont [MFC]
- HBITMAP and class CBitmap [MFC]
- fonts [MFC], creating in device context
- images [MFC], graphic objects [MFC]
- CBitmap class [MFC], HBITMAP handle type
- HPALETTE and class CPalette [MFC]
- CBrush class [MFC], HBRUSH handle type
- objects [MFC], graphic objects
- drawing [MFC], in device contexts
- device contexts [MFC], graphic objects [MFC]
- brushes [MFC], creating in device context
- region objects [MFC]
- pen objects [MFC]
- GDI [MFC], graphic-object classes
- graphic objects [MFC], creating in device context
- HBRUSH and class CBrush [MFC]
- painting and device context [MFC]
- CPalette class [MFC], HPALETTE handle type
ms.assetid: 41963b25-34b7-4343-8446-34ba516b83ca
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0fabeeae17b5bc81fdf592ed452a088b75bae544
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="graphic-objects"></a>グラフィック オブジェクト
Windows には、さまざまなデバイス コンテキストで使用する描画ツールが用意されています。 たとえば、線を描画するためのペン、内部を塗りつぶすためのブラシ、テキストを描画するためのフォントがあります。 MFC には、Windows の描画ツールと同等のグラフィック オブジェクト クラスが用意されています。 使用可能なクラスと、それに対応する Windows グラフィックス デバイス インターフェイス (GDI) ハンドル型を次の表に示します。  
  
> [!NOTE]
>  GDI+ は Windows XP に含まれており、Windows NT 4.0 SP6、Windows 2000、Windows 98、および Windows Me の再頒布可能物として使用できます。 最新再頒布可能パッケージをダウンロードするを参照してください。 [http://www.microsoft.com/msdownload/platformsdk/sdkupdate/psdkredist.htm](http://www.microsoft.com/msdownload/platformsdk/sdkupdate/psdkredist.htm)です。 詳細については、GDI + SDK のドキュメントを参照してください: [http://msdn.microsoft.com/library/default.aspurl=/library/gdicpp/GDIPlus/GDIPlus.asp](http://msdn.microsoft.com/library/default.aspurl=/library/gdicpp/gdiplus/gdiplus.asp)です。  
  
 この記事では、これらのグラフィック オブジェクト クラスの使用方法について説明します。  
  
### <a name="classes-for-windows-gdi-objects"></a>Windows GDI オブジェクトのクラス  
  
|クラス|Windows のハンドル型|  
|-----------|-------------------------|  
|[CPen](../mfc/reference/cpen-class.md)|`HPEN`|  
|[CBrush](../mfc/reference/cbrush-class.md)|`HBRUSH`|  
|[CFont](../mfc/reference/cfont-class.md)|**HFONT**|  
|[CBitmap](../mfc/reference/cbitmap-class.md)|`HBITMAP`|  
|[CPalette](../mfc/reference/cpalette-class.md)|`HPALETTE`|  
|[CRgn](../mfc/reference/crgn-class.md)|**HRGN**|  
  
> [!NOTE]
>  クラス[CImage](../atl-mfc-shared/reference/cimage-class.md)ビットマップの拡張サポートを提供します。  
  
 クラス ライブラリに含まれる各グラフィック オブジェクト クラスには、そのクラスのグラフィック オブジェクトを作成するためのコンストラクターがあります。グラフィック オブジェクトは、`CreatePen` などの適切な関数を使用して初期化する必要があります。  
  
 クラス ライブラリに含まれる各グラフィック オブジェクト クラスには、MFC オブジェクトを関連付けられた Windows ハンドルにキャストするキャスト演算子があります。 結果として得られるハンドルは、関連付けられたオブジェクトによってデタッチされるまで有効です。 オブジェクトの**デタッチ**ハンドルをデタッチするメンバー関数。  
  
 次のコードは、`CPen` オブジェクトを Windows ハンドルにキャストしています。  
  
 [!code-cpp[NVC_MFCDocViewSDI#5](../mfc/codesnippet/cpp/graphic-objects_1.cpp)]  
  
#### <a name="to-create-a-graphic-object-in-a-device-context"></a>デバイス コンテキストでグラフィック オブジェクトを作成するには  
  
1.  スタック フレーム上でグラフィック オブジェクトを定義します。 型に固有の作成関数 (たとえば、`CreatePen`) を使用して、オブジェクトを初期化します。 または、コンストラクター内でオブジェクトを初期化します。 説明を参照して[1 段階および 2 段階の作成](../mfc/one-stage-and-two-stage-construction-of-objects.md)コード例を提供します。  
  
2.  [現在のデバイス コンテキストにオブジェクトを選択](../mfc/selecting-a-graphic-object-into-a-device-context.md)、前に選択された古いグラフィック オブジェクトを保存します。  
  
3.  現在のグラフィック オブジェクトの操作が完了したら、古いグラフィック オブジェクトをデバイス コンテキストに選択してその状態を復元します。  
  
4.  スコープが終了したときにフレームによって割り当てられたグラフィック オブジェクトが自動的に削除されるように設定します。  
  
> [!NOTE]
>  グラフィック オブジェクトを繰り返し使用する場合は、1 回割り当てておけば、後で必要になったときに各デバイス コンテキストに選択できます。 これらのオブジェクトが不要になったときは必ず削除してください。  
  
### <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [グラフィック オブジェクトの 1 つのステージと 2 段階の構築](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [1 番目と 2 段階でペンを作成する例](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [グラフィック オブジェクトをデバイス コンテキストに選択する](../mfc/selecting-a-graphic-object-into-a-device-context.md)  
  
-   [デバイス コンテキスト](../mfc/device-contexts.md)  
  
-   [以前のオペレーティング システムにおける CImage の制限](../mfc/cimage-limitations-with-earlier-operating-systems.md)  
  
## <a name="see-also"></a>参照  
 [Window オブジェクト](../mfc/window-objects.md)

