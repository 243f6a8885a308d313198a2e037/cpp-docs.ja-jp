---
title: "MFC ActiveX コントロール: ストック プロパティ ページを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CLSID_CPicturePropPage
- CLSID_CColorPropPage
- CLSID_CFontPropPage
dev_langs: C++
helpviewer_keywords:
- picture stock property pages [MFC]
- CLSID_CFontPropPage [MFC]
- color stock property pages [MFC]
- CLSID_CColorPropPage [MFC]
- fonts [MFC], ActiveX controls
- stock properties [MFC], stock property pages
- CLSID_CPicturePropPage [MFC]
- MFC ActiveX controls [MFC], property pages
ms.assetid: 22638d86-ff3e-4124-933e-54b7c2a25968
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ed2d8cd6c852a15c4190c16c049e29577b754ce7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-using-stock-property-pages"></a>MFC ActiveX コントロール : ストック プロパティ ページの使用
この記事では、ActiveX コントロールとその使用方法の使用可能なストック プロパティ ページについて説明します。  
  
 ActiveX コントロールのプロパティ ページを使用する方法については、次の記事を参照してください。  
  
-   [MFC ActiveX コントロール: プロパティ ページ](../mfc/mfc-activex-controls-property-pages.md)  
  
-   [MFC ActiveX コントロール: カスタム プロパティ ページの追加](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)  
  
 MFC ActiveX コントロールで使用するための 3 つのストック プロパティ ページの提供:**できる**、 **CLSID_CFontPropPage**、および**あります**です。 これらのページでは、株価の色、フォント、および画像のプロパティのユーザー インターフェイスがそれぞれ表示されます。  
  
 これらのプロパティ ページをコントロールに組み込むするには、プロパティ ページ Id のコントロールの配列を初期化するコードをその Id を追加します。 次の例では、このコードは、コントロール実装ファイルにあります (です。CPP)、3 つすべてのストック プロパティ ページおよび既定のプロパティ ページを格納する配列を初期化します (名前付き`CMyPropPage`この例では)。  
  
 [!code-cpp[NVC_MFC_AxOpt#21](../mfc/codesnippet/cpp/mfc-activex-controls-using-stock-property-pages_1.cpp)]  
  
 プロパティの数ページで、メモ、`BEGIN_PROPPAGEIDS`マクロは 4 です。 これは、ActiveX コントロールでサポートされているプロパティ ページの数を表します。  
  
 このような変更が完了したら、プロジェクトをリビルドします。 フォント、画像、および色のプロパティのプロパティ ページがコントロールに追加します。  
  
> [!NOTE]
>  コントロールのストック プロパティ ページにアクセスできない場合は、MFC DLL (MFCxx.DLL) が正常に登録されていません、現在のオペレーティング システム可能性があります。 これは、通常、現在実行されている 1 つから別のオペレーティング システムで Visual C のインストールから発生します。  
  
> [!TIP]
>  ストック プロパティ ページが表示されない場合 (前のメモを参照)、DLL への完全なパス名をコマンドラインから RegSvr32.exe を実行して、DLL を登録します。  
  
## <a name="see-also"></a>参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX コントロール: ストック プロパティの追加](../mfc/mfc-activex-controls-adding-stock-properties.md)

