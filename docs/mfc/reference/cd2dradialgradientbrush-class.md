---
title: "CD2DRadialGradientBrush クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::Attach
- AFXRENDERTARGET/CD2DRadialGradientBrush::Create
- AFXRENDERTARGET/CD2DRadialGradientBrush::Destroy
- AFXRENDERTARGET/CD2DRadialGradientBrush::Detach
- AFXRENDERTARGET/CD2DRadialGradientBrush::Get
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetCenter
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetGradientOriginOffset
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetRadiusX
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetRadiusY
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetCenter
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetGradientOriginOffset
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetRadiusX
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetRadiusY
- AFXRENDERTARGET/CD2DRadialGradientBrush::m_pRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::m_RadialGradientBrushProperties
dev_langs:
- C++
helpviewer_keywords:
- CD2DRadialGradientBrush class
ms.assetid: 6c76d84a-d831-4ee2-96f1-82c1f5b0d6a9
caps.latest.revision: 17
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 8b3fd7f468745567969ba1f7e9d6871a9060582b
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dradialgradientbrush-class"></a>CD2DRadialGradientBrush クラス
ID2D1RadialGradientBrush のラッパーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DRadialGradientBrush : public CD2DGradientBrush;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DRadialGradientBrush::CD2DRadialGradientBrush](#cd2dradialgradientbrush)|CD2DLinearGradientBrush オブジェクトを構築します。|  
|[CD2DRadialGradientBrush:: ~ CD2DRadialGradientBrush](#_dtorcd2dradialgradientbrush)|デストラクターです。 D2D 放射状グラデーション ブラシのオブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DRadialGradientBrush::Attach](#attach)|オブジェクトにリソース インタ フェースを既存の接続|  
|[CD2DRadialGradientBrush::Create](#create)|CD2DRadialGradientBrush を作成します。 (上書き[CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create))。|  
|[CD2DRadialGradientBrush::Destroy](#destroy)|CD2DRadialGradientBrush オブジェクトを破棄します。 (上書き[CD2DGradientBrush::Destroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy))。|  
|[CD2DRadialGradientBrush::Detach](#detach)|オブジェクトからリソース インタ フェースをデタッチします。|  
|[CD2DRadialGradientBrush::Get](#get)|返します。 ID2D1RadialGradientBrush インターフェイス|  
|[CD2DRadialGradientBrush::GetCenter](#getcenter)|グラデーションの楕円の中心を取得します。|  
|[CD2DRadialGradientBrush::GetGradientOriginOffset](#getgradientoriginoffset)|グラデーションのグラデーションの楕円の中心から原点のオフセットを取得します。|  
|[CD2DRadialGradientBrush::GetRadiusX](#getradiusx)|グラデーションの楕円の半径 x の取得します。|  
|[CD2DRadialGradientBrush::GetRadiusY](#getradiusy)|グラデーションの楕円の半径 y を取得します。|  
|[CD2DRadialGradientBrush::SetCenter](#setcenter)|ブラシの座標空間でグラデーションの楕円の中心を指定します。|  
|[CD2DRadialGradientBrush::SetGradientOriginOffset](#setgradientoriginoffset)|グラデーションのグラデーションの楕円の中心から原点のオフセットを指定します|  
|[CD2DRadialGradientBrush::SetRadiusX](#setradiusx)|ブラシの座標空間でグラデーションの楕円の x 半径を指定します。|  
|[CD2DRadialGradientBrush::SetRadiusY](#setradiusy)|ブラシの座標空間でグラデーションの楕円の y 半径を指定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DRadialGradientBrush::operator ID2D1RadialGradientBrush *](#operator_id2d1radialgradientbrush_star)|返します。 ID2D1RadialGradientBrush インターフェイス|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DRadialGradientBrush::m_pRadialGradientBrush](#m_pradialgradientbrush)|ID2D1RadialGradientBrush へのポインター。|  
|[CD2DRadialGradientBrush::m_RadialGradientBrushProperties](#m_radialgradientbrushproperties)|センター、グラデーションの原点のオフセットと半径 x および y 半径ブラシのグラデーションのです。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)  
  
 `CD2DRadialGradientBrush`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="_dtorcd2dradialgradientbrush"></a>CD2DRadialGradientBrush:: ~ CD2DRadialGradientBrush  
 デストラクターです。 D2D 放射状グラデーション ブラシのオブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CD2DRadialGradientBrush();
```  
  
##  <a name="attach"></a>CD2DRadialGradientBrush::Attach  
 オブジェクトにリソース インタ フェースを既存の接続  
  
```  
void Attach(ID2D1RadialGradientBrush* pResource);
```  
  
### <a name="parameters"></a>パラメーター  
 `pResource`  
 既存のリソースのインターフェイスです。 NULL にすることはできません。  
  
##  <a name="cd2dradialgradientbrush"></a>CD2DRadialGradientBrush::CD2DRadialGradientBrush  
 CD2DLinearGradientBrush オブジェクトを構築します。  
  
```  
CD2DRadialGradientBrush(
    CRenderTarget* pParentTarget,  
    const D2D1_GRADIENT_STOP* gradientStops,  
    UINT gradientStopsCount,  
    D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES RadialGradientBrushProperties,  
    D2D1_GAMMA colorInterpolationGamma = D2D1_GAMMA_2_2,  
    D2D1_EXTEND_MODE extendMode = D2D1_EXTEND_MODE_CLAMP,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentTarget`  
 レンダー ターゲットへのポインター。  
  
 `gradientStops`  
 D2D1_GRADIENT_STOP 構造体の配列へのポインター。  
  
 `gradientStopsCount`  
 GradientStops 配列内のグラデーションの分岐点の数を指定する 1 以上の値です。  
  
 `RadialGradientBrushProperties`  
 センター、グラデーションの原点のオフセットと半径 x および y 半径ブラシのグラデーションのです。  
  
 `colorInterpolationGamma`  
 どの色のグラデーションの分岐点間の補間が実行される領域です。  
  
 `extendMode`  
 [0,&1;] の正規化された範囲外のグラデーションの動作です。  
  
 `pBrushProperties`  
 不透明度とブラシの変換へのポインター。  
  
 `bAutoDestroy`  
 所有者 (pParentTarget) によって、オブジェクトが破棄されることを示します。  
  
##  <a name="create"></a>CD2DRadialGradientBrush::Create  
 CD2DRadialGradientBrush を作成します。  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `pRenderTarget`  
 レンダー ターゲットへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
##  <a name="destroy"></a>CD2DRadialGradientBrush::Destroy  
 CD2DRadialGradientBrush オブジェクトを破棄します。  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DRadialGradientBrush::Detach  
 オブジェクトからリソース インタ フェースをデタッチします。  
  
```  
ID2D1RadialGradientBrush* Detach();
```  
  
### <a name="return-value"></a>戻り値  
 デタッチされたリソース インタ フェースへのポインター。  
  
##  <a name="get"></a>CD2DRadialGradientBrush::Get  
 返します。 ID2D1RadialGradientBrush インターフェイス  
  
```  
ID2D1RadialGradientBrush* Get();
```  
  
### <a name="return-value"></a>戻り値  
 ID2D1RadialGradientBrush インターフェイスまたはオブジェクトがまだ初期化されていない場合は NULL へのポインター。  
  
##  <a name="getcenter"></a>CD2DRadialGradientBrush::GetCenter  
 グラデーションの楕円の中心を取得します。  
  
```  
CD2DPointF GetCenter() const;  
```  
  
### <a name="return-value"></a>戻り値  
 グラデーションの楕円の中心です。 この値は、ブラシの座標空間の表示します。  
  
##  <a name="getgradientoriginoffset"></a>CD2DRadialGradientBrush::GetGradientOriginOffset  
 グラデーションのグラデーションの楕円の中心から原点のオフセットを取得します。  
  
```  
CD2DPointF GetGradientOriginOffset() const;  
```  
  
### <a name="return-value"></a>戻り値  
 グラデーションのグラデーションの楕円の中心から原点のオフセット。 この値は、ブラシの座標空間の表示します。  
  
##  <a name="getradiusx"></a>CD2DRadialGradientBrush::GetRadiusX  
 グラデーションの楕円の半径 x の取得します。  
  
```  
FLOAT GetRadiusX() const;  
```  
  
### <a name="return-value"></a>戻り値  
 グラデーションの楕円の x 半径。 この値は、ブラシの座標空間の表示します。  
  
##  <a name="getradiusy"></a>CD2DRadialGradientBrush::GetRadiusY  
 グラデーションの楕円の半径 y を取得します。  
  
```  
FLOAT GetRadiusY() const;  
```  
  
### <a name="return-value"></a>戻り値  
 グラデーションの楕円の y 半径。 この値は、ブラシの座標空間の表示します。  
  
##  <a name="m_pradialgradientbrush"></a>CD2DRadialGradientBrush::m_pRadialGradientBrush  
 ID2D1RadialGradientBrush へのポインター。  
  
```  
ID2D1RadialGradientBrush* m_pRadialGradientBrush;  
```  
  
##  <a name="m_radialgradientbrushproperties"></a>CD2DRadialGradientBrush::m_RadialGradientBrushProperties  
 センター、グラデーションの原点のオフセットと半径 x および y 半径ブラシのグラデーションのです。  
  
```  
D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES m_RadialGradientBrushProperties;  
```  
  
##  <a name="operator_id2d1radialgradientbrush_star"></a>CD2DRadialGradientBrush::operator ID2D1RadialGradientBrush *  
 返します。 ID2D1RadialGradientBrush インターフェイス  
  
```  
operator ID2D1RadialGradientBrush*();
```   
  
### <a name="return-value"></a>戻り値  
 ID2D1RadialGradientBrush インターフェイスまたはオブジェクトがまだ初期化されていない場合は NULL へのポインター。  
  
##  <a name="setcenter"></a>CD2DRadialGradientBrush::SetCenter  
 ブラシの座標空間でグラデーションの楕円の中心を指定します。  
  
```  
void SetCenter(CD2DPointF point);
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 グラデーションの楕円のブラシの座標空間内の中央  
  
##  <a name="setgradientoriginoffset"></a>CD2DRadialGradientBrush::SetGradientOriginOffset  
 グラデーションのグラデーションの楕円の中心から原点のオフセットを指定します  
  
```  
void SetGradientOriginOffset(CD2DPointF gradientOriginOffset);
```  
  
### <a name="parameters"></a>パラメーター  
 `gradientOriginOffset`  
 グラデーションのグラデーションの楕円の中心から原点のオフセット  
  
##  <a name="setradiusx"></a>CD2DRadialGradientBrush::SetRadiusX  
 ブラシの座標空間でグラデーションの楕円の x 半径を指定します。  
  
```  
void SetRadiusX(FLOAT radiusX);
```  
  
### <a name="parameters"></a>パラメーター  
 `radiusX`  
 グラデーションの楕円の x 半径。 この値は、ブラシの座標空間には  
  
##  <a name="setradiusy"></a>CD2DRadialGradientBrush::SetRadiusY  
 ブラシの座標空間でグラデーションの楕円の y 半径を指定します。  
  
```  
void SetRadiusY(FLOAT radiusY);
```  
  
### <a name="parameters"></a>パラメーター  
 `radiusY`  
 グラデーションの楕円の y 半径。 この値は、ブラシの座標空間には  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
