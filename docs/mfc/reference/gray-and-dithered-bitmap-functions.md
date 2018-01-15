---
title: "灰色とディザリングされたビットマップ関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFXWIN/AfxDrawGrayBitmap
- AFXWIN/AfxGetGrayBitmap
- AFXWIN/AfxDrawDitheredBitmap
- AFXWIN/AfxGetDitheredBitmap
dev_langs: C++
helpviewer_keywords: gray and dithered bitmap functions [MFC]
ms.assetid: cb139a77-b85e-4504-9d93-24156ad77a41
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7f895fb22e4f4d2649cdec1e4c9925b69b013e49
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="gray-and-dithered-bitmap-functions"></a>淡色表示 (灰色) ビットマップ関数とディザリングされたビットマップ関数
**淡色表示 (灰色) ビットマップ関数**  
  
 MFC には、ビットマップのコントロールが無効になっていることを示すための 2 つの関数が用意されています。  
  
 ![灰色と元のアイコンの比較](../../mfc/reference/media/vcgraybitmap.gif "vcgraybitmap")  
  
|||  
|-|-|  
|[AfxDrawGrayBitmap](#afxdrawgraybitmap)|灰色のバージョンのビットマップを描画します。|  
|[AfxGetGrayBitmap](#afxgetgraybitmap)|灰色のバージョンのビットマップをコピーします。|  
  
 **淡色表示 (灰色) ビットマップ関数**  
  
 MFC には、ビットマップの背景をディザリングされたパターンに置き換える 2 つの関数も用意されています。  
  
 ![ディザリングされたと元のアイコンの比較](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")  
  
|||  
|-|-|  
|[AfxDrawDitheredBitmap](#afxdrawditheredbitmap)|背景がディザリングされたビットマップを描画します。|  
|[AfxGetDitheredBitmap](#afxgetditheredbitmap)|背景がディザリングされたビットマップをコピーします。|  
  
##  <a name="afxdrawgraybitmap"></a>  AfxDrawGrayBitmap  
 灰色のバージョンのビットマップを描画します。  
  
```   
void AFXAPI AfxDrawGrayBitmap(
    CDC* pDC,  
    int x,  
    int y,  
    const CBitmap& rSrc,  
    COLORREF crBackground); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 宛先 DC を示します。  
  
 *x*  
 宛先の x 座標。  
  
 *y*  
 宛先の y 座標。  
  
 `rSrc`  
 元のビットマップ。  
  
 `crBackground`  
 新しい背景色 (通常は COLOR_MENU などの灰色)。  
  
### <a name="remarks"></a>コメント  
 `AfxDrawGrayBitmap` で描画されるビットマップの外観は、無効なコントロールになります。  
  
 ![灰色と元のアイコンの比較](../../mfc/reference/media/vcgraybitmap.gif "vcgraybitmap")  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#191](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_1.cpp)]  

### <a name="requirements"></a>必要条件  
 **ヘッダー:** afxwin.h  

##  <a name="afxgetgraybitmap"></a>  AfxGetGrayBitmap  
 灰色のバージョンのビットマップをコピーします。  
  
```   
void AFXAPI AfxGetGrayBitmap(
    const CBitmap& rSrc,  
    CBitmap* pDest,  
    COLORREF crBackground); 
```  
  
### <a name="parameters"></a>パラメーター  
 `rSrc`  
 元のビットマップ。  
  
 `pDest`  
 コピー先のビットマップ。  
  
 `crBackground`  
 新しい背景色 (通常は COLOR_MENU などの灰色)。  
  
### <a name="remarks"></a>コメント  
 `AfxGetGrayBitmap` でコピーされるビットマップの外観は、無効なコントロールのようになります。  
  
 ![灰色と元のアイコンの比較](../../mfc/reference/media/vcgraybitmap.gif "vcgraybitmap")  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#193](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_2.cpp)]  

### <a name="requirements"></a>必要条件  
 **ヘッダー:** afxwin.h  
  
##  <a name="afxdrawditheredbitmap"></a>  AfxDrawDitheredBitmap  
 その背景 (チェック) をディザリングされたパターンを置き換える、ビットマップを描画します。  
  
```   
void AFXAPI AfxDrawDitheredBitmap(
    CDC* pDC,  
    int x,  
    int y,  
    const CBitmap& rSrc,  
    COLORREF cr1  ,  
    COLORREF cr2); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 宛先 DC を示します。  
  
 *x*  
 宛先の x 座標。  
  
 *y*  
 宛先の y 座標。  
  
 `rSrc`  
 元のビットマップ。  
  
 `cr1`  
 2 つのディザー カラーのいずれかの通常白色です。  
  
 `cr2`  
 その他のディザー色、通常の明るい灰色で示さ (COLOR_MENU)。  
  
### <a name="remarks"></a>コメント  
 2 色で宛先 DC 上に元のビットマップを描画 (`cr1`と`cr2`) チェッカー パターン ビットマップの背景。 元のビットマップの背景は、その白いピクセルとビットマップの左上隅にあるピクセルの色と一致するすべてのピクセルとして定義されます。  
  
 ![ディザリングされたと元のアイコンの比較](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#190](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_3.cpp)]  

### <a name="requirements"></a>必要条件  
 **ヘッダー:** afxwin.h  


##  <a name="afxgetditheredbitmap"></a>  AfxGetDitheredBitmap  
 その背景 (チェック) をディザリングされたパターンを置き換える、ビットマップをコピーします。  
  
```   
void AFXAPI AfxGetDitheredBitmap(
    const CBitmap& rSrc,  
    CBitmap* pDest,  
    COLORREF cr1  ,  
    COLORREF cr2); 
```  
  
### <a name="parameters"></a>パラメーター  
 `rSrc`  
 元のビットマップ。  
  
 `pDest`  
 コピー先のビットマップ。  
  
 `cr1`  
 2 つのディザー カラーのいずれかの通常白色です。  
  
 `cr2`  
 その他のディザー色、通常の明るい灰色で示さ (COLOR_MENU)。  
  
### <a name="remarks"></a>コメント  
 元のビットマップを 2 色でコピー先ビットマップにコピー (`cr1`と`cr2`) 元のビットマップの背景に置き換えるチェッカーのパターン。 元のビットマップの背景は、その白いピクセルとビットマップの左上隅にあるピクセルの色と一致するすべてのピクセルとして定義されます。  
  
 ![ディザリングされたと元のアイコンの比較](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#192](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_4.cpp)]  

### <a name="requirements"></a>必要条件  
 **ヘッダー:** afxwin.h  
  
## <a name="see-also"></a>参照  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)
