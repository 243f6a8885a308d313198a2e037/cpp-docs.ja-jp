---
title: "CDrawingManager クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDrawingManager
- AFXDRAWMANAGER/CDrawingManager
- AFXDRAWMANAGER/CDrawingManager::CDrawingManager
- AFXDRAWMANAGER/CDrawingManager::CreateBitmap_32
- AFXDRAWMANAGER/CDrawingManager::DrawAlpha
- AFXDRAWMANAGER/CDrawingManager::DrawRotated
- AFXDRAWMANAGER/CDrawingManager::DrawEllipse
- AFXDRAWMANAGER/CDrawingManager::DrawGradientRing
- AFXDRAWMANAGER/CDrawingManager::DrawRect
- AFXDRAWMANAGER/CDrawingManager::DrawShadow
- AFXDRAWMANAGER/CDrawingManager::Fill4ColorsGradient
- AFXDRAWMANAGER/CDrawingManager::FillGradient
- AFXDRAWMANAGER/CDrawingManager::FillGradient2
- AFXDRAWMANAGER/CDrawingManager::GrayRect
- AFXDRAWMANAGER/CDrawingManager::HighlightRect
- AFXDRAWMANAGER/CDrawingManager::HLStoRGB_ONE
- AFXDRAWMANAGER/CDrawingManager::HLStoRGB_TWO
- AFXDRAWMANAGER/CDrawingManager::HSVtoRGB
- AFXDRAWMANAGER/CDrawingManager::HuetoRGB
- AFXDRAWMANAGER/CDrawingManager::MirrorRect
- AFXDRAWMANAGER/CDrawingManager::PixelAlpha
- AFXDRAWMANAGER/CDrawingManager::PrepareShadowMask
- AFXDRAWMANAGER/CDrawingManager::RGBtoHSL
- AFXDRAWMANAGER/CDrawingManager::RGBtoHSV
- AFXDRAWMANAGER/CDrawingManager::SetAlphaPixel
- AFXDRAWMANAGER/CDrawingManager::SetPixel
- AFXDRAWMANAGER/CDrawingManager::SmartMixColors
dev_langs:
- C++
helpviewer_keywords:
- CDrawingManager class
ms.assetid: 9e4775ca-101b-4aa9-a85a-4d047c701215
caps.latest.revision: 30
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 53929fff6df57b4e5fe00572f8a7cec8a218c638
ms.lasthandoff: 02/24/2017

---
# <a name="cdrawingmanager-class"></a>CDrawingManager クラス
`CDrawingManager`クラスは複雑な描画アルゴリズムを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDrawingManager : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDrawingManager::CDrawingManager](#cdrawingmanager)|`CDrawingManager` オブジェクトを構築します。|  
|`CDrawingManager::~CDrawingManager`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDrawingManager::CreateBitmap_32](#createbitmap_32)|32 ビット版のデバイスに依存しないビットマップ (DIB) に直接書き込むことができるアプリケーションを作成します。|  
|[CDrawingManager::DrawAlpha](#drawalpha)|透明または半透明ピクセルのビットマップを表示します。|  
|[CDrawingManager::DrawRotated](#drawrotated)|ソース DC コンテンツ 90 ° +/-によって指定された四角形の内部を回転させる|  
|[CDrawingManager::DrawEllipse](#drawellipse)|指定された塗りつぶしと境界線の色で楕円を描画します。|  
|[CDrawingManager::DrawGradientRing](#drawgradientring)|リングを描画し、色のグラデーションで塗りつぶします。|  
|[CDrawingManager::DrawLine CDrawingManager::DrawLineA](#drawline_cdrawingmanager__drawlinea)|直線を描画します。|  
|[CDrawingManager::DrawRect](#drawrect)|指定された塗りつぶしと境界線の色を含む四角形を描画します。|  
|[CDrawingManager::DrawShadow](#drawshadow)|四角形の領域に影を描画します。|  
|[CDrawingManager::Fill4ColorsGradient](#fill4colorsgradient)|2 つの色のグラデーションで四角形の領域を塗りつぶします。|  
|[CDrawingManager::FillGradient](#fillgradient)|四角形の領域を指定した色のグラデーションで塗りつぶします。|  
|[CDrawingManager::FillGradient2](#fillgradient2)|四角形の領域を指定した色のグラデーションで塗りつぶします。 グラデーションの色の変更の方向も指定します。|  
|[CDrawingManager::GrayRect](#grayrect)|指定した色の灰色の四角形を格納します。|  
|[CDrawingManager::HighlightRect](#highlightrect)|四角形の領域を強調表示されます。|  
|[CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)|HLS 表現から色を RGB 表現に変換します。|  
|[CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)|HLS 表現から色を RGB 表現に変換します。|  
|[CDrawingManager::HSVtoRGB](#hsvtorgb)|HSV 表現から色を RGB 表現に変換します。|  
|[CDrawingManager::HuetoRGB](#huetorgb)|色合いの値を赤、緑、青の各要素に変換するヘルパー メソッドです。|  
|[CDrawingManager::MirrorRect](#mirrorrect)|四角形の領域を反転します。|  
|[CDrawingManager::PixelAlpha](#pixelalpha)|半透明ピクセルの最終的な色を決定するヘルパー メソッド。|  
|[CDrawingManager::PrepareShadowMask](#prepareshadowmask)|影として使用できるビットマップを作成します。|  
|[CDrawingManager::RGBtoHSL](#rgbtohsl)|色を RGB 表現から HSL 表現に変換します。|  
|[CDrawingManager::RGBtoHSV](#rgbtohsv)|色を RGB 表現から HSV 表現に変換します。|  
|[CDrawingManager::SetAlphaPixel](#setalphapixel)|ヘルパー メソッドはビットマップで部分的に透明なピクセルの色です。|  
|[CDrawingManager::SetPixel](#setpixel)|ビットマップ内の単一のピクセルを指定した色に変更するヘルパー メソッドです。|  
|[CDrawingManager::SmartMixColors](#smartmixcolors)|重み付け比率に基づいて&2; つの色を結合します。|  
  
## <a name="remarks"></a>コメント  
 `CDrawingManager`クラスは、影と色のグラデーションと強調表示された四角形を描画するための関数を提供します。 アルファ ブレンドも実行します。 このクラスを使用して、アプリケーションの UI を直接変更することができます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
 `CDrawingManager`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdrawmanager.h  
  
##  <a name="cdrawingmanager"></a>CDrawingManager::CDrawingManager  
 構築、 [CDrawingManager](../../mfc/reference/cdrawingmanager-class.md)オブジェクトです。  
  
```  
CDrawingManager(CDC& dc);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dc`  
 デバイス コンテキストへの参照。 `CDrawingManager`描画のため、このコンテキストを使用します。  
  
##  <a name="createbitmap_32"></a>CDrawingManager::CreateBitmap_32  
 32 ビット版のデバイスに依存しないビットマップ (DIB) に直接書き込むことができるアプリケーションを作成します。  
  
```  
static HBITMAP __stdcall CreateBitmap_32(
    const CSize& size,  
    void** pBits);
 
static HBITMAP __stdcall CreateBitmap_32(
    HBITMAP bitmap,  
    COLORREF clrTransparent = -1);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `size`|A [CSize](../../atl-mfc-shared/reference/csize-class.md)ビットマップのサイズを示すパラメーターです。|  
|[出力] `pBits`|DIB の場所を受信するデータ ポインターへのポインターのビット値。|  
|`bitmap`|元のビットマップを識別するハンドル|  
|`clrTransparent`|元のビットマップの透明色を指定する RGB 値。|  
  
### <a name="return-value"></a>戻り値  
 このメソッドが成功した場合は、新しく作成した DIB ビットマップへのハンドルそれ以外の場合`NULL`します。  
  
### <a name="remarks"></a>コメント  
 DIB ビットマップを作成する方法の詳細については、次を参照してください。 [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183491)します。  
  
##  <a name="drawalpha"></a>CDrawingManager::DrawAlpha  
 透明または半透明ピクセルのビットマップを表示します。  
  
```  
void DrawAlpha(
    CDC* pDstDC,  
    const CRect& rectDst,  
    CDC* pSrcDC,  
    const CRect& rectSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDstDC`  
 コピー先のデバイス コンテキストへのポインター。  
  
 [入力] `rectDst`  
 移行先の四角形。  
  
 [入力] `pSrcDC`  
 ソースのデバイス コンテキストへのポインター。  
  
 [入力] `rectSrc`  
 元の四角形。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、アルファ ブレンドを実行&2; つのビットマップ。 アルファ ブレンドの詳細については、次を参照してください。 [AlphaBlend](http://msdn.microsoft.com/library/windows/desktop/dd183351) Windows SDK に含まれています。  
  
##  <a name="drawellipse"></a>CDrawingManager::DrawEllipse  
 指定された塗りつぶしと境界線の色で楕円を描画します。  
  
```  
void DrawEllipse(
    const CRect& rect,  
    COLORREF clrFill,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
 楕円の外接する四角形。  
  
 [入力] `clrFill`  
 このメソッドは、楕円の塗りつぶしに使用する色。  
  
 [入力] `clrLine`  
 このメソッドは、楕円の境界として使用する色。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、どちらかの色が-1 に設定されている場合は、楕円を描画せずに復帰します。 外接する四角形のいずれかのサイズが 0 の場合は、楕円を描画せずも返されます。  
  
##  <a name="drawgradientring"></a>CDrawingManager::DrawGradientRing  
 リングを描画し、色のグラデーションで塗りつぶします。  
  
```  
BOOL DrawGradientRing(
    CRect rect,  
    COLORREF colorStart,  
    COLORREF colorFinish,  
    COLORREF colorBorder,  
    int nAngle,  
    int nWidth,  
    COLORREF clrFace = (COLORREF)-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
 A [CRect](../../atl-mfc-shared/reference/crect-class.md)グラデーションのリングの境界を指定するパラメーターです。  
  
 [入力] `colorStart`  
 グラデーションの最初の色。  
  
 [入力] `colorFinish`  
 グラデーションの最後の色。  
  
 [入力] `colorBorder`  
 罫線の色。  
  
 [入力] `nAngle`  
 初期のグラデーションの描画角度を指定するパラメーター。 この値は、0 ~ 360 の間にする必要があります。  
  
 [入力] `nWidth`  
 リングの境界線の幅。  
  
 [入力] `clrFace`  
 リングの内部の色です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 によって定義された四角`rect`には、少なくとも 5 ピクセル高さ全体に適用され、5 ピクセルにする必要があります。  
  
##  <a name="drawline_cdrawingmanager__drawlinea"></a>CDrawingManager::DrawLine CDrawingManager::DrawLineA  
 直線を描画します。  
  
```  
void DrawLine(
    int x1,  
    int y1,  
    int x2,  
    int y2,  
    COLORREF clrLine);
 
void DrawLineA(
    double x1,  
    double y1,  
    double x2,  
    double y2,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `x1`|直線の開始位置の x 座標。|  
|[入力] `y1`|直線の開始位置の y 座標。|  
|[入力] `x2`|直線の終了位置の x 座標。|  
|[入力] `y2`|直線の終了位置の y 座標。|  
|[入力] `clrLine`|線の色。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは失敗`clrLine`-1 です。  
  
##  <a name="drawrect"></a>CDrawingManager::DrawRect  
 指定された塗りつぶしと境界線の色を含む四角形を描画します。  
  
```  
void DrawRect(
    const CRect& rect,  
    COLORREF clrFill,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
 四角形の境界です。  
  
 [入力] `clrFill`  
 このメソッドは四角形の塗りつぶしの色。  
  
 [入力] `clrLine`  
 このメソッドを使用して四角形の枠線の色。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、どちらかの色が-1 に設定されている場合は、四角形を描画せずに復帰します。 また、四角形のいずれかのサイズは 0 を返します。  
  
##  <a name="drawshadow"></a>CDrawingManager::DrawShadow  
 四角形の領域に影を描画します。  
  
```  
BOOL DrawShadow(
    CRect rect,  
    int nDepth,  
    int iMinBrightness = 100,  
    int iMaxBrightness = 50,  
    CBitmap* pBmpSaveBottom = NULL,  
    CBitmap* pBmpSaveRight = NULL,  
    COLORREF clrBase = (COLORREF)-1,  
    BOOL bRightShadow = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
 アプリケーションで四角形領域。 描画のマネージャーは、この領域の下に影を描画します。  
  
 [入力] `nDepth`  
 幅と影の高さ。  
  
 [入力] `iMinBrightness`  
 影の最小の明るさです。  
  
 [入力] `iMaxBrightness`  
 影の最大の明るさです。  
  
 [入力] `pBmpSaveBottom`  
 影の下部にある一部のイメージを含むビットマップへのポインター。  
  
 [入力] `pBmpSaveRight`  
 四角形の右側に描画されているシャドウのイメージを含むビットマップへのポインター。  
  
 [入力] `clrBase`  
 影の色。  
  
 [入力] `bRightShadow`  
 影を描画する方法を示すブール値パラメーターです。 場合`bRightShadow`は`TRUE`、`DrawShadow`右側にある四角形の影を描画します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 パラメーターを使用して、下部にあると適切影の&2; つの有効なビットマップを提供できます`pBmpSaveBottom`と`pBmpSaveRight`です。 これら[CBitmap](../../mfc/reference/cbitmap-class.md)オブジェクトがアタッチされた GDI オブジェクトをある`DrawShadow`シャドウとしてこれらのビットマップを使用します。 場合、`CBitmap`パラメーターにアタッチされた GDI オブジェクトがない`DrawShadow`影を描画し、パラメーターに、ビットマップをアタッチします。 呼び出し後で`DrawShadow`、これらのビットマップを描画プロセスを高速化を指定することができます。 詳細については、`CBitmap`クラスと GDI オブジェクトを参照してください[グラフィック オブジェクト](../../mfc/graphic-objects.md)します。  
  
 これらのパラメーターのいずれかの場合`NULL`、`DrawShadow`は自動的に影を描画します。  
  
 設定した場合`bRightShadow`に`FALSE`、下にあると、四角形領域の左側に影を描画します。  
  
### <a name="example"></a>例  
 次の例では、使用して、`DrawShadow`のメソッド、`CDrawingManager`クラスです。 このコード スニペットの一部である、[プロパティ シートのデモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_PropSheetDemo&#1;](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_1.cpp)]  
  
##  <a name="fill4colorsgradient"></a>CDrawingManager::Fill4ColorsGradient  
 2 つの色のグラデーションで四角形の領域を塗りつぶします。  
  
```  
void Fill4ColorsGradient(
    CRect rect,  
    COLORREF colorStart1,  
    COLORREF colorFinish1,  
    COLORREF colorStart2,  
    COLORREF colorFinish2,  
    BOOL bHorz = TRUE,  
    int nPercentage = 50);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
 塗りつぶす四角形。  
  
 [入力] `colorStart1`  
 最初の色のグラデーションの初期の色。  
  
 [入力] `colorFinish1`  
 最初の色のグラデーションの終了色。  
  
 [入力] `colorStart2`  
 2 番目の色のグラデーションの初期の色。  
  
 [入力] `colorFinish2`  
 2 番目の色のグラデーションの終了色。  
  
 [入力] `bHorz`  
 示すブール値パラメーターかどうか`Fill4ColorsGradient`水平または垂直グラデーションの色します。 `TRUE`水平方向のグラデーションを示します。  
  
 [入力] `nPercentage`  
 0 ~ 100 の整数。 この値は、最初の色のグラデーションで塗りつぶす四角形の割合を示します。  
  
### <a name="remarks"></a>コメント  
 相互の上にあるかの値に応じて、次は四角形がいっぱいになる&2; つの色グラデーションに`bHorz`します。 メソッドを使用して各色のグラデーションが個別に計算が[CDrawingManager::FillGradient](#fillgradient)します。  
  
 場合、このメソッドは、アサーション エラーを生成`nPercentage`が 0 未満か、100 を超えています。  
  
##  <a name="fillgradient"></a>CDrawingManager::FillGradient  
 四角形の領域を指定した色のグラデーションで塗りつぶします。  
  
```  
void FillGradient(
    CRect rect,  
    COLORREF colorStart,  
    COLORREF colorFinish,  
    BOOL bHorz = TRUE,  
    int nStartFlatPercentage = 0,  
    int nEndFlatPercentage = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
 塗りつぶす四角形領域。  
  
 [入力] `colorStart`  
 グラデーションの最初の色。  
  
 [入力] `colorFinish`  
 グラデーションの終了色。  
  
 [入力] `bHorz`  
 ブール型パラメーターを指定するかどうか`FillGradient`水平または垂直グラデーションを描画する必要があります。  
  
 [入力] `nStartFlatPercentage`  
 四角形の割合を`FillGradient`で塗りつぶします`colorStart`グラデーションを開始する前にします。  
  
 [入力] `nEndFlatPercentage`  
 四角形の割合を`FillGradient`で塗りつぶします`colorFinish`グラデーションを終了するとします。  
  
### <a name="example"></a>例  
 次の例では、使用して、`FillGradient`のメソッド、`CDrawingManager`クラスです。 このコード スニペットの一部である、 [MS Office 2007 デモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo&#12;](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_2.cpp)]  
  
##  <a name="fillgradient2"></a>CDrawingManager::FillGradient2  
 四角形の領域を指定した色のグラデーションで塗りつぶします。  
  
```  
void FillGradient2 (
    CRect rect,  
    COLORREF colorStart,  
    COLORREF colorFinish,  
    int nAngle = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
 塗りつぶす四角形領域。  
  
 [入力] `colorStart`  
 グラデーションの最初の色。  
  
 [入力] `colorFinish`  
 グラデーションの最後の色。  
  
 [入力] `nAngle`  
 0 ~ 360 の間の整数。 このパラメーターは、色のグラデーションの方向を指定します。  
  
### <a name="remarks"></a>コメント  
 使用`nAngle`色のグラデーションの方向を指定します。 色のグラデーションの方向を指定するときにも指定する色のグラデーションの開始位置。 値 0 を`nAngle`四角形の上部にあるグラデーションの開始を示します。 として`nAngle`増加すると、グラデーションが角度に基づいて反時計回りの方向に移動の開始位置。  
  
### <a name="example"></a>例  
 次の例では、使用して、`FillGradient2`のメソッド、`CDrawingManager`クラスです。 このコード スニペットの一部である、[新しいコントロールのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_NewControls #&37;](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_3.cpp)]  
  
##  <a name="grayrect"></a>CDrawingManager::GrayRect  
 指定した色の灰色の四角形を格納します。  
  
```  
BOOL GrayRect(
    CRect rect,  
    int nPercentage = -1,  
    COLORREF clrTransparent = (COLORREF)-1,  
    COLORREF clrDisabled = (COLORREF)-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
 塗りつぶす四角形領域。  
  
 [入力] `nPercentage`  
 四角形に使用灰色の割合。  
  
 [入力] `clrTransparent`  
 透明色。  
  
 [入力] `clrDisabled`  
 このメソッドの場合、彩度を使用する色`nPercentage`が-1 に設定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メソッドが成功した場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 パラメーターの`nPercentage`値が低い方が暗い色を示します。  
  
 最大値`nPercentage`200 です。 200 を超える値は、四角形の外観を変更していません。 このメソッドを使用して、値が-1 の場合は、`clrDisabled`を四角形の彩度を制限します。  
  
##  <a name="highlightrect"></a>CDrawingManager::HighlightRect  
 四角形の領域を強調表示されます。  
  
```  
BOOL HighlightRect(
    CRect rect,  
    int nPercentage = -1,  
    COLORREF clrTransparent = (COLORREF)-1,  
    int nTolerance = 0,  
    COLORREF clrBlend = (COLORREF)-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
 四角形の領域を強調表示します。  
  
 [入力] `nPercentage`  
 透明度、強調表示するかを示す割合。  
  
 [入力] `clrTransparent`  
 透明色。  
  
 [入力] `nTolerance`  
 色の許容範囲を示す 0 から 255 までの整数。  
  
 [入力] `clrBlend`  
 描画の基本色です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メソッドが成功した場合それ以外の場合`FALSE`します。  
  
### <a name="remarks"></a>コメント  
 場合`nPercentage`は 0 ~ 99 の`HighlightRect`アルファ ブレンディング アルゴリズムを使用します。 アルファ ブレンドの詳細については、次を参照してください。[アルファ ブレンドの直線と塗りつぶし](http://msdn.microsoft.com/library/5440f48c-3ac9-44c3-b170-c1c110bdbab8)します。 場合`nPercentage`-1 で、このメソッドは、既定の強調表示のレベルを使用します。 場合`nPercentage`100 は、このメソッドは何も実行し、返します`TRUE`します。  
  
 メソッド パラメーターを使用して`nTolerance`を四角形の領域を強調表示するかどうかを判断します。 四角形をアプリケーションの背景色の違いを強調表示して`clrTransparent`する必要がありますより小さい`nTolerance`(赤、緑、および青) の各色成分にします。  
  
##  <a name="hlstorgb_one"></a>CDrawingManager::HLStoRGB_ONE  
 HLS 表現から色を RGB 表現に変換します。  
  
```  
static COLORREF __stdcall HLStoRGB_ONE(
    double H,  
    double L,  
    double S);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `H`  
 色の色合いを表す 0 ~ 1 の数値。  
  
 [入力] `L`  
 0 ~ 1 の範囲の数値では、色の明るさを示します。  
  
 [入力] `S`  
 0 ~ 1 の範囲の数値では、色の彩度を示します。  
  
### <a name="return-value"></a>戻り値  
 提供された HLS 色の RGB 表現です。  
  
### <a name="remarks"></a>コメント  
 色は、HSV (色合い、鮮やかさ、および値)、HSL (色合い、鮮やかさ、および明るさ) または RGB (赤、緑、および青) として表現できます。 色の異なる表現の詳細については、次を参照してください。[色](http://go.microsoft.com/fwlink/linkid=119126)します。  
  
 このメソッドと`CDrawingManager::HLStoRGB_TWO`メソッドは、同じ操作を実行しますに別の値が必要、`H`パラメーター。 このメソッドで`H`円に占める割合です。 `CDrawingManager::HLStoRGB_TWO`メソッド、`H`は 0 ~ 360 両方が表している赤の間の角度の値。 たとえば、 `HLStoRGB_ONE`、値は 0.25 の`H`と 90 の値と同じ`HLStoRGB_TWO`します。  
  
##  <a name="hlstorgb_two"></a>CDrawingManager::HLStoRGB_TWO  
 HLS 表現から色を RGB 表現に変換します。  
  
```  
static COLORREF __stdcall HLStoRGB_TWO(
    double H,  
    double L,  
    double S);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `H`  
 色の色合いを表す 0 ~ 360 の間数です。  
  
 [入力] `L`  
 0 ~ 1 の範囲の数値では、色の明るさを示します。  
  
 [入力] `S`  
 0 ~ 1 の範囲の数値では、色の彩度を示します。  
  
### <a name="return-value"></a>戻り値  
 提供された HLS 色の RGB 表現です。  
  
### <a name="remarks"></a>コメント  
 色は、HSV (色合い、鮮やかさ、および値)、HSL (色合い、鮮やかさ、および明るさ) または RGB (赤、緑、および青) として表現できます。 色の異なる表現の詳細については、次を参照してください。[色](http://go.microsoft.com/fwlink/linkid=119126)します。  
  
 このメソッドと[CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)メソッドは、同じ操作を実行しますに別の値が必要、`H`パラメーター。 このメソッドで`H`は 0 ~ 360 両方が表している赤の間の角度の値。 [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)メソッド、`H`円に占める割合です。 たとえば、 `HLStoRGB_ONE`、値は 0.25 の`H`と 90 の値と同じ`HLStoRGB_TWO`します。  
  
##  <a name="hsvtorgb"></a>CDrawingManager::HSVtoRGB  
 HSV 表現から色を RGB 表現に変換します。  
  
```  
static COLORREF __stdcall HSVtoRGB(
    double H,  
    double S,  
    double V);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `H`|色の色合いを表す数値 0 ~ 360 の間です。|  
|[入力] `S`|0 ~ 1 の範囲の数値では、色の彩度を示します。|  
|[入力] `V`|0 ~ 1 の範囲の数値は、色の値を示します。|  
  
### <a name="return-value"></a>戻り値  
 提供される HSV 色の RGB 表現です。  
  
### <a name="remarks"></a>コメント  
 色は、HSV (色合い、鮮やかさ、および値)、HSL (色合い、鮮やかさ、および明るさ) または RGB (赤、緑、および青) として表現できます。 色の異なる表現の詳細については、次を参照してください。[色](http://go.microsoft.com/fwlink/linkid=119126)します。  
  
##  <a name="huetorgb"></a>CDrawingManager::HuetoRGB  
 色合いの値を赤、緑、青の各要素に変換します。  
  
```  
static double __stdcall HuetoRGB(
    double m1,  
    double m2,  
    double h);

 
static BYTE __stdcall HueToRGB(
    float rm1,  
    float rm2,  
    float rh);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `m1`  
 「解説」を参照してください。  
  
 [入力] `m2`  
 「解説」を参照してください。  
  
 [入力] `h`  
 「解説」を参照してください。  
  
 [入力] `rm1`  
 「解説」を参照してください。  
  
 [入力] `rm2`  
 「解説」を参照してください。  
  
 [入力] `rh`  
 「解説」を参照してください。  
  
### <a name="return-value"></a>戻り値  
 指定された色合いの個別赤、緑、または青コンポーネント。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ヘルパー メソッドを`CDrawingManager`クラス HSV または HSL の表現で使用する色の個々 の赤、緑、および青のコンポーネントを計算するために使用します。 このメソッドは、プログラマが直接呼び出すためのものではありません。 入力パラメーターは、変換アルゴリズムに依存する値です。  
  
 HSV または HSL の色を RGB 表現に変換するには、次の方法のいずれかを呼び出します。  
  
- [CDrawingManager::HSVtoRGB](#hsvtorgb)  
  
- [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)  
  
- [CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)  
  
##  <a name="mirrorrect"></a>CDrawingManager::MirrorRect  
 四角形の領域を反転します。  
  
```  
void MirrorRect(
    CRect rect,  
    BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
 反転対象の領域に外接する四角形。  
  
 [入力] `bHorz`  
 四角形が水平方向または垂直方向に反転するかどうかを示すブール値パラメーターです。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、によって所有されているデバイス コンテキストの任意の領域を反転させること、`CDrawingManager`クラスです。 場合`bHorz`に設定されている`TRUE`、このメソッドは、領域を水平方向に反転します。 それ以外の場合、領域が垂直方向に反転します。  
  
##  <a name="pixelalpha"></a>CDrawingManager::PixelAlpha  
 半透明ピクセルの最終的な色を計算します。  
  
```  
static COLORREF __stdcall PixelAlpha(
    COLORREF srcPixel,  
    int percent);
 
static COLORREF __stdcall PixelAlpha(
    COLORREF srcPixel,  
    double percentR,  
    double percentG,  
    double percentB);

static COLORREF __stdcall PixelAlpha(
    COLORREF srcPixel,  
    COLORREF dstPixel,  
    int percent);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `srcPixel`  
 ピクセルの初期の色。  
  
 [入力] `percent`  
 透明度の割合を表す 0 ~ 100 の数値。 100 の値は、初期の色が完全に透過的であることを示します。  
  
 [入力] `percentR`  
 赤の要素の透明度の割合を表す 0 ~ 100 の範囲数です。  
  
 [入力] `percentG`  
 緑の成分の透明度の割合を表す 0 ~ 100 の範囲数です。  
  
 [入力] `percentB`  
 青の要素の透明度の割合を表す 0 ~ 100 の範囲数です。  
  
 [入力] `dstPixel`  
 ピクセルの基本色です。  
  
### <a name="return-value"></a>戻り値  
 半透明のピクセルの最終的な色です。  
  
### <a name="remarks"></a>コメント  
 これは半透明のビットマップの色を付けるためのヘルパー クラスであり、プログラマが直接呼び出されるものではありません。  
  
 持つメソッドのバージョンを使用する場合`dstPixel`、最終的な色の組み合わせは、`dstPixel`と`srcPixel`です。 `srcPixel`色は、部分的に透明な色を基本の色の上`dstPixel`します。  
  
##  <a name="prepareshadowmask"></a>CDrawingManager::PrepareShadowMask  
 影として使用できるビットマップを作成します。  
  
```  
static HBITMAP __stdcall PrepareShadowMask (
    int nDepth,  
    COLORREF clrBase,  
    int iMinBrightness = 0,  
    int iMaxBrightness = 100);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nDepth`  
 幅と影の高さ。  
  
 [入力] `clrBase`  
 影の色。  
  
 [入力] `iMinBrightness`  
 影の最小の明るさです。  
  
 [入力] `iMaxBrightness`  
 影の最大の明るさです。  
  
### <a name="return-value"></a>戻り値  
 このメソッドが成功した場合、作成したビットマップへのハンドルそれ以外の場合`NULL`します。  
  
### <a name="remarks"></a>コメント  
 場合`nDepth`は 0、このメソッドに設定されるは終了し、返します`NULL`します。 場合`nDepth`が 3 未満の場合、幅と高さの影が 3 ピクセルに設定します。  
  
##  <a name="rgbtohsl"></a>CDrawingManager::RGBtoHSL  
 色を赤、緑、および青 (RGB) 形式から色合い、鮮やかさ、および明るさ (HSL) 表現を変換します。  
  
```  
static void __stdcall RGBtoHSL(
    COLORREF rgb,  
    double* H,  
    double* S,  
    double* L);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `rgb`|RGB 値の色。|  
|[出力] `H`|メソッドが色の色合いを格納する double 型へのポインター。|  
|[出力] `S`|メソッドが色の彩度を格納する double 型へのポインター。|  
|[出力] `L`|メソッドが、色の明るさを格納する double 型へのポインター。|  
  
### <a name="remarks"></a>コメント  
 色は、HSV (色合い、鮮やかさ、および値)、HSL (色合い、鮮やかさ、および明るさ) または RGB (赤、緑、および青) として表現できます。 色の異なる表現の詳細については、次を参照してください。[色](http://go.microsoft.com/fwlink/linkid=119126)します。  
  
 返された値`H`は 0 ~ 0 と 1 の両方が赤を表す位置 1 の比率として表されます。 戻り値`S`と`L`0 ~ 1 の範囲の数値します。  
  
##  <a name="rgbtohsv"></a>CDrawingManager::RGBtoHSV  
 色を RGB 表現から HSV 表現に変換します。  
  
```  
static void __stdcall RGBtoHSV(
    COLORREF rgb,  
    double* H,  
    double* S,  
    double* V);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rgb`  
 RGB 表現に変換する色。  
  
 [出力] `H`  
 このメソッドが最終的な色の色合いを格納する double 型へのポインター。  
  
 [出力] `S`  
 このメソッドが最終的な色の彩度を格納する double 型へのポインター。  
  
 [出力] `V`  
 このメソッドが、色の結果として得られる値を格納する double 型へのポインター。  
  
### <a name="remarks"></a>コメント  
 色は、HSV (色合い、鮮やかさ、および値)、HSL (色合い、鮮やかさ、および明るさ) または RGB (赤、緑、および青) として表現できます。 色の異なる表現の詳細については、次を参照してください。[色](http://go.microsoft.com/fwlink/linkid=119126)します。  
  
 返された値`H`0 ~ 360 の間の数は、0 から 360 の両方が赤を示します。 戻り値は、`S`と`V`0 ~ 1 の範囲の数値します。  
  
##  <a name="setalphapixel"></a>CDrawingManager::SetAlphaPixel  
 ビットマップ内の透明なピクセルを色します。  
  
```  
static void __stdcall SetAlphaPixel(
    COLORREF* pBits,  
    CRect rect,  
    int x,  
    int y,  
    int percent,  
    int iShadowSize,  
    COLORREF clrBase = (COLORREF)-1,  
    BOOL bIsRight = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBits`  
 ビットマップのビット値へのポインター。  
  
 [入力] `rect`  
 アプリケーションで四角形領域。 描画のマネージャーでは、下にあると、この領域の右側に影を描画します。  
  
 [入力] `x`  
 色を付けるピクセルの水平座標。  
  
 [入力] `y`  
 色を付けるピクセルの垂直座標。  
  
 [入力] `percent`  
 透明度の割合。  
  
 [入力] `iShadowSize`  
 幅と影の高さ。  
  
 [入力] `clrBase`  
 影の色。  
  
 [入力] `bIsRight`  
 色を付けるピクセルを示すブール値パラメーターです。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ヘルパー メソッドで使用される、 [CDrawingManager::DrawShadow](#drawshadow)メソッドです。 影を描画する場合を呼び出すことをお勧め`CDrawingManager::DrawShadow`代わりにします。  
  
 場合`bIsRight`に設定されている`TRUE`、ピクセルの色には、測定`x`の右端からピクセル`rect`します。 ある場合`FALSE`、ピクセルの色には、測定`x`の左端からピクセル`rect`します。  
  
##  <a name="setpixel"></a>CDrawingManager::SetPixel  
 ビットマップ内の単一のピクセルを指定した色に変更します。  
  
```  
static void __stdcall SetPixel(
    COLORREF* pBits,  
    int cx,  
    int cy,  
    int x,  
    int y,  
    COLORREF color);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pBits`|ビットマップのビット値へのポインター。|  
|[入力] `cx`|ビットマップの幅の合計です。|  
|[入力] `cy`|ビットマップの高さの合計です。|  
|[入力] `x`|変更するビットマップのピクセルの x 座標。|  
|[入力] `y`|変更するビットマップのピクセルの y 座標。|  
|[入力] `color`|指定された座標で識別されるピクセルの新しい色。|  
  
##  <a name="smartmixcolors"></a>CDrawingManager::SmartMixColors  
 重み付け比率に基づいて&2; つの色を結合します。  
  
```  
static COLORREF __stdcall SmartMixColors(
    COLORREF color1,  
    COLORREF color2,  
    double dblLumRatio = 1.,  
    int k1 = 1,  
    int k2 = 1);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `color1`|最初の色を混在させる。|  
|[入力] `color2`|2 番目の色を混在させる。|  
|[入力] `dblLumRatio`|新しい色の明るさの比率。 `SmartMixColors`最終的な色を決定する前に、この比率で混在した色の明るさを乗算します。|  
|[入力] `k1`|最初の色の重み付け比率。|  
|[入力] `k2`|2 番目の色の重み付けの比率。|  
  
### <a name="return-value"></a>戻り値  
 指定された色の重み付けの組み合わせを表す色です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、どちらの場合はエラーで失敗`k1`または`k2`が&0; 未満です。 メソッドが戻るかどうかは、0 にこれらのパラメーターの両方の設定は、`RGB(0, 0, 0)`です。  
  
 重み付けの比率は、次の式で計算します。 (color1 * k1 + color2 \* k2)/(k1 + k2) します。 重み付け比率を決定した後は、メソッドは、混在した色の明るさを計算します。 明るさを乗算し、`dblLumRatio`です。 値が 1.0 よりも大きい場合は、メソッドは新しい値に混在の色の明るさを設定します。 それ以外の場合、明るさは 1.0 に設定されます。  
  
##  <a name="drawrotated"></a>CDrawingManager::DrawRotated  
 指定した四角形内の DC のコンテンツのソースを 90 度回転させます。  
  
```  
void DrawRotated(
    CRect rectDest,  
    CDC& dcSrc,  
    BOOL bClockWise);
```  
  
### <a name="parameters"></a>パラメーター  
 `rectDest`  
 コピー先の四角形。  
  
 `dcSrc`  
 元のデバイス コンテキスト。  
  
 `bClockWise`  
 `TRUE`回転 +90 度を示す`FALSE`回転の向きを示します。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)

