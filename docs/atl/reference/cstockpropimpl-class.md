---
title: "CStockPropImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStockPropImpl
- ATL::CStockPropImpl
- ATL.CStockPropImpl
dev_langs:
- C++
helpviewer_keywords:
- CStockPropImpl class
- controls [ATL], stock properties
- stock properties, ATL controls
ms.assetid: 45f11d7d-6580-4a0e-872d-3bc8b836cfda
caps.latest.revision: 20
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 366da264f62364a39f6dfe9903a1a19a89266d33
ms.lasthandoff: 02/24/2017

---
# <a name="cstockpropimpl-class"></a>CStockPropImpl クラス
このクラスは、ストック プロパティの値をサポートするためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T, class InterfaceName,
    const IID* piid = &_ATL_IIDOF(InterfaceName),
    const GUID* plibid = &CComModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0, class tihclass = CcomTypeInfoHolder>  
class ATL_NO_VTABLE CStockPropImpl : public IDispatchImpl<InterfaceName, piid,
 plibid,
    wMajor,
 wMinor,
    tihclass>
```   
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 コントロールを実装してから派生するクラス`CStockPropImpl`します。  
  
 `InterfaceName`  
 ストック プロパティを公開するデュアル インターフェイスです。  
  
 `piid`  
 IID へのポインター`InterfaceName`します。  
  
 `plibid`  
 定義が含まれるタイプ ライブラリの LIBID へのポインター`InterfaceName`します。  
  
 `wMajor`  
 タイプ ライブラリのメジャー バージョン。 既定値は 1 です。  
  
 `wMinor`  
 タイプ ライブラリのマイナー バージョン。 既定値は 0 です。  
  
 `tihclass`  
 型情報の管理に使用されるクラス`T`します。 既定値は `CComTypeInfoHolder` です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|[get_Appearance](#get_appearance)|フラット、コントロールで使われるペイント スタイルまたは 3D を取得するには、このメソッドを呼び出します。|  
|[get_AutoSize](#get_autosize)|コントロールが他の任意のサイズを変更できないかどうかを示すフラグの状態を取得するには、このメソッドを呼び出します。|  
|[get_BackColor](#get_backcolor)|コントロールの背景色を取得するには、このメソッドを呼び出します。|  
|[get_BackStyle](#get_backstyle)|透明または不透明のコントロールの背景スタイルを取得するには、このメソッドを呼び出します。|  
|[get_BorderColor](#get_bordercolor)|コントロールの境界線の色を取得するには、このメソッドを呼び出します。|  
|[get_BorderStyle](#get_borderstyle)|コントロールの境界線のスタイルを取得するには、このメソッドを呼び出します。|  
|[get_BorderVisible](#get_bordervisible)|コントロールの境界線が表示されているかどうかを示すフラグの状態を取得するには、このメソッドを呼び出します。|  
|[get_BorderWidth](#get_borderwidth)|コントロールの境界線の幅をピクセル単位で取得するには、このメソッドを呼び出します。|  
|[get_Caption](#get_caption)|オブジェクトのキャプションで指定したテキストを取得するには、このメソッドを呼び出します。|  
|[get_DrawMode](#get_drawmode)|XOR ペン、色の反転など、コントロールの描画モードを取得するには、このメソッドを呼び出します。|  
|[get_DrawStyle](#get_drawstyle)|実線、破線、点線などのコントロールの描画スタイルを取得するには、このメソッドを呼び出します。|  
|[get_DrawWidth](#get_drawwidth)|コントロールの描画メソッドで使われる図面の幅をピクセル単位で取得するには、このメソッドを呼び出します。|  
|[get_Enabled](#get_enabled)|コントロールが有効になっているかどうかを示すフラグの状態を取得するには、このメソッドを呼び出します。|  
|[get_FillColor](#get_fillcolor)|コントロールの塗りつぶしの色を取得するには、このメソッドを呼び出します。|  
|[get_FillStyle](#get_fillstyle)|ソリッド、透過的なまたはのクロスハッチなどのコントロールの塗りつぶしのスタイルを取得するには、このメソッドを呼び出します。|  
|[get_Font](#get_font)|コントロールのフォント プロパティへのポインターを取得するには、このメソッドを呼び出します。|  
|[get_ForeColor](#get_forecolor)|コントロールの前景色を取得するには、このメソッドを呼び出します。|  
|[get_HWND](#get_hwnd)|コントロールに関連付けられているウィンドウ ハンドルを取得するには、このメソッドを呼び出します。|  
|[get_MouseIcon](#get_mouseicon)|(アイコン、ビットマップまたはメタファイル) マウスがコントロール上にあるときに表示される画像の画像のプロパティを取得するには、このメソッドを呼び出します。|  
|[get_MousePointer](#get_mousepointer)|マウス ポインターが、マウスが、コントロールの上にある場合に表示される、矢印、間、または砂時計の型を取得するには、このメソッドを呼び出します。|  
|[get_Picture](#get_picture)|(アイコン、ビットマップまたはメタファイル) 表示される画像の画像のプロパティへのポインターを取得するには、このメソッドを呼び出します。|  
|[get_ReadyState](#get_readystate)|ロードまたはアンロードなどのコントロールの準備完了の状態を取得するには、このメソッドを呼び出します。|  
|[get_TabStop](#get_tabstop)|コントロールがタブ ストップがかどうかかを示すフラグを取得するには、このメソッドを呼び出します。|  
|[get_Text](#get_text)|コントロールに表示されるテキストを取得するには、このメソッドを呼び出します。|  
|[getvalid](#get_valid)|コントロールが有効かどうかどうかかを示すフラグの状態を取得するには、このメソッドを呼び出します。|  
|[get_Window](#get_window)|コントロールに関連付けられているウィンドウ ハンドルを取得するには、このメソッドを呼び出します。 同じ[CStockPropImpl::get_HWND](#get_hwnd)します。|  
|[put_Appearance](#put_appearance)|フラット、コントロールで使われるペイント スタイルまたは 3D を設定するには、このメソッドを呼び出します。|  
|[put_AutoSize](#put_autosize)|コントロールが他の任意のサイズを変更できないかどうかを示すフラグの値を設定するには、このメソッドを呼び出します。|  
|[put_BackColor](#put_backcolor)|コントロールの背景色を設定するには、このメソッドを呼び出します。|  
|[put_BackStyle](#put_backstyle)|コントロールの背景のスタイルを設定するには、このメソッドを呼び出します。|  
|[put_BorderColor](#put_bordercolor)|コントロールの境界線の色を設定するには、このメソッドを呼び出します。|  
|[put_BorderStyle](#put_borderstyle)|コントロールの境界線のスタイルを設定するには、このメソッドを呼び出します。|  
|[put_BorderVisible](#put_bordervisible)|コントロールの境界線が表示されているかどうかを示すフラグの値を設定するには、このメソッドを呼び出します。|  
|[put_BorderWidth](#put_borderwidth)|コントロールの境界線の幅を設定するには、このメソッドを呼び出します。|  
|[put_Caption](#put_caption)|コントロールに表示されるテキストを設定するには、このメソッドを呼び出します。|  
|[put_DrawMode](#put_drawmode)|XOR ペン、色の反転など、コントロールの描画モードを設定するには、このメソッドを呼び出します。|  
|[put_DrawStyle](#put_drawstyle)|実線、破線、点線などのコントロールの描画スタイルを設定するには、このメソッドを呼び出します。|  
|[put_DrawWidth](#put_drawwidth)|コントロールの描画メソッドで使用されるピクセル単位の幅を設定するには、このメソッドを呼び出します。|  
|[put_Enabled](#put_enabled)|コントロールが有効になっているかどうかを示すフラグを設定するには、このメソッドを呼び出します。|  
|[put_FillColor](#put_fillcolor)|コントロールの塗りつぶしの色を設定するには、このメソッドを呼び出します。|  
|[put_FillStyle](#put_fillstyle)|ソリッド、透過的なまたはのクロスハッチなどのコントロールの塗りつぶしのスタイルを設定するには、このメソッドを呼び出します。|  
|[put_Font](#put_font)|コントロールのフォント プロパティを設定するには、このメソッドを呼び出します。|  
|[put_ForeColor](#put_forecolor)|コントロールの前景の色を設定するには、このメソッドを呼び出します。|  
|[put_HWND](#put_hwnd)|このメソッドには、E_FAIL が返されます。|  
|[put_MouseIcon](#put_mouseicon)|(アイコン、ビットマップまたはメタファイル) マウスがコントロール上にあるときに表示される画像の画像のプロパティを設定するには、このメソッドを呼び出します。|  
|[put_MousePointer](#put_mousepointer)|マウス ポインターが、マウスが、コントロールの上にある場合に表示される、矢印、間、または砂時計の種類を設定するには、このメソッドを呼び出します。|  
|[put_Picture](#put_picture)|(アイコン、ビットマップまたはメタファイル) 表示される画像の画像のプロパティを設定するには、このメソッドを呼び出します。|  
|[put_ReadyState](#put_readystate)|ロードまたはアンロードなどのコントロールの準備完了の状態を設定するには、このメソッドを呼び出します。|  
|[put_TabStop](#put_tabstop)|コントロールがタブ ストップがかどうかかを示すフラグの値を設定するには、このメソッドを呼び出します。|  
|[put_Text](#put_text)|コントロールに表示されるテキストを設定するには、このメソッドを呼び出します。|  
|[putvalid](#put_valid)|コントロールが有効かどうかどうかかを示すフラグを設定するには、このメソッドを呼び出します。|  
|[put_Window](#put_window)|このメソッドを呼び出す[CStockPropImpl::put_HWND](#put_hwnd)E_FAIL が返されます。|  
|[putref_Font](#putref_font)|参照カウント付きのコントロールのフォント プロパティを設定するには、このメソッドを呼び出します。|  
|[putref_MouseIcon](#putref_mouseicon)|参照カウントを持つ (アイコン、ビットマップまたはメタファイル) マウスがコントロール上にあるときに表示される画像の画像のプロパティを設定するには、このメソッドを呼び出します。|  
|[putref_Picture](#putref_picture)|参照カウントを持つ (アイコン、ビットマップまたはメタファイル) 表示される画像の画像のプロパティを設定するには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>コメント  
 `CStockPropImpl`提供**配置**と**取得**各ストック プロパティのメソッドです。 これらのメソッドは、各プロパティに関連付けられているデータ メンバーを取得または設定とを通知し、プロパティが変更されたときに、コンテナーを同期に必要なコードを提供します。  
  
 Visual C では、そのウィザードを使用するストック プロパティがサポートされています。 ストック プロパティをコントロールに追加する方法の詳細については、次を参照してください。、 [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)します。  
  
 旧バージョンとの互換性のため`CStockPropImpl`も公開`get_Window`と`put_Window`を単に呼び出すメソッド`get_HWND`と`put_HWND`、それぞれします。 既定の実装`put_HWND`返します**E_FAIL**ので`HWND`読み取り専用プロパティである必要があります。  
  
 次のプロパティもある、 **putref**実装します。  
  
-   フォント  
  
-   MouseIcon  
  
-   Picture  
  
 同じ&3; つのストック プロパティが、対応するデータ メンバーの型を必要と`CComPtr`か、適切なインターフェイスの参照を提供する他のクラスは、代入演算子を使用してカウントされます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `T`  
  
 [IDispatchImpl](../../atl/reference/idispatchimpl-class.md)  
  
 `CStockPropImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="a-namegetappearancea--cstockpropimplgetappearance"></a><a name="get_appearance"></a>CStockPropImpl::get_Appearance  
 フラット、コントロールで使われるペイント スタイルまたは 3D を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_Appearance(SHORT pnAppearance);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnAppearance*  
 コントロールの描画スタイルを受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegetautosizea--cstockpropimplgetautosize"></a><a name="get_autosize"></a>CStockPropImpl::get_AutoSize  
 コントロールが他の任意のサイズを変更できないかどうかを示すフラグの状態を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_Autosize(VARIANT_BOOL* pbAutoSize);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbAutoSize*  
 フラグの状態を受け取る変数。 TRUE は、コントロールが他の任意のサイズを変更できないことを示します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegetbackcolora--cstockpropimplgetbackcolor"></a><a name="get_backcolor"></a>CStockPropImpl::get_BackColor  
 コントロールの背景色を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_BackColor(OLE_COLOR* pclrBackColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *pclrBackColor*  
 コントロールの背景色を受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegetbackstylea--cstockpropimplgetbackstyle"></a><a name="get_backstyle"></a>CStockPropImpl::get_BackStyle  
 透明または不透明のコントロールの背景スタイルを取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_BackStyle(LONG* pnBackStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnBackStyle*  
 コントロールの背景のスタイルを受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegetbordercolora--cstockpropimplgetbordercolor"></a><a name="get_bordercolor"></a>CStockPropImpl::get_BorderColor  
 コントロールの境界線の色を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_BorderColor(OLE_COLOR* pclrBorderColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *pclrBorderColor*  
 コントロールの境界線の色を受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegetborderstylea--cstockpropimplgetborderstyle"></a><a name="get_borderstyle"></a>CStockPropImpl::get_BorderStyle  
 コントロールの境界線のスタイルを取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_BorderStyle(LONG* pnBorderStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnBorderStyle*  
 コントロールの境界線のスタイルを受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegetbordervisiblea--cstockpropimplgetbordervisible"></a><a name="get_bordervisible"></a>CStockPropImpl::get_BorderVisible  
 コントロールの境界線が表示されているかどうかを示すフラグの状態を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_BorderVisible(VARIANT_BOOL* pbBorderVisible);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbBorderVisible*  
 フラグの状態を受け取る変数。 TRUE は、コントロールの境界線が表示されていることを示します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegetborderwidtha--cstockpropimplgetborderwidth"></a><a name="get_borderwidth"></a>CStockPropImpl::get_BorderWidth  
 コントロールの境界線の幅を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_BorderWidth(LONG* pnBorderWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnBorderWidth*  
 コントロールの境界線の幅を受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegetcaptiona--cstockpropimplgetcaption"></a><a name="get_caption"></a>CStockPropImpl::get_Caption  
 オブジェクトのキャプションで指定したテキストを取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_Caption(BSTR* pbstrCaption);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbstrCaption*  
 コントロールに表示されるテキスト。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegetdrawmodea--cstockpropimplgetdrawmode"></a><a name="get_drawmode"></a>CStockPropImpl::get_DrawMode  
 XOR ペン、色の反転など、コントロールの描画モードを取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_DrawMode(LONG* pnDrawMode);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnDrawMode*  
 コントロールの描画モードを受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegetdrawstylea--cstockpropimplgetdrawstyle"></a><a name="get_drawstyle"></a>CStockPropImpl::get_DrawStyle  
 実線、破線、点線などのコントロールの描画スタイルを取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_DrawStyle(LONG* pnDrawStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnDrawStyle*  
 コントロールの描画スタイルを受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegetdrawwidtha--cstockpropimplgetdrawwidth"></a><a name="get_drawwidth"></a>CStockPropImpl::get_DrawWidth  
 コントロールの描画メソッドで使われる図面の幅をピクセル単位で取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_DrawWidth(LONG* pnDrawWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnDrawWidth*  
 ピクセル単位で、コントロールの幅の値を受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegetenableda--cstockpropimplgetenabled"></a><a name="get_enabled"></a>CStockPropImpl::get_Enabled  
 コントロールが有効になっているかどうかを示すフラグの状態を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_Enabled(VARIANT_BOOL* pbEnabled);
```  
  
### <a name="parameters"></a>パラメーター  
 `pbEnabled`  
 フラグの状態を受け取る変数。 TRUE は、コントロールが有効になっていることを示します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegetfillcolora--cstockpropimplgetfillcolor"></a><a name="get_fillcolor"></a>CStockPropImpl::get_FillColor  
 コントロールの塗りつぶしの色を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_FillColor(OLE_COLOR* pclrFillColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *pclrFillColor*  
 コントロールの塗りつぶしの色を受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegetfillstylea--cstockpropimplgetfillstyle"></a><a name="get_fillstyle"></a>CStockPropImpl::get_FillStyle  
 ハッチ ソリッドなど透過的な場合は、たとえば、コントロールの塗りつぶしのスタイルを取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_FillStyle(LONG* pnFillStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnFillStyle*  
 コントロールの塗りつぶしのスタイルを受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegetfonta--cstockpropimplgetfont"></a><a name="get_font"></a>CStockPropImpl::get_Font  
 コントロールのフォント プロパティへのポインターを取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_Font(IFontDisp** ppFont);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppFont`  
 コントロールのフォント プロパティへのポインターを受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegetforecolora--cstockpropimplgetforecolor"></a><a name="get_forecolor"></a>CStockPropImpl::get_ForeColor  
 コントロールの前景色を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_ForeColor(OLE_COLOR* pclrForeColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *pclrForeColor*  
 コントロールの前景の色を受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegethwnda--cstockpropimplgethwnd"></a><a name="get_hwnd"></a>CStockPropImpl::get_HWND  
 コントロールに関連付けられているウィンドウ ハンドルを取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_HWND(LONG_PTR* phWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `phWnd`  
 コントロールに関連付けられているウィンドウ ハンドル。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegetmouseicona--cstockpropimplgetmouseicon"></a><a name="get_mouseicon"></a>CStockPropImpl::get_MouseIcon  
 (アイコン、ビットマップまたはメタファイル) マウスがコントロール上にあるときに表示される画像の画像のプロパティを取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_MouseIcon(IPictureDisp** ppPicture);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppPicture`  
 グラフィックの画像のプロパティへのポインターを受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegetmousepointera--cstockpropimplgetmousepointer"></a><a name="get_mousepointer"></a>CStockPropImpl::get_MousePointer  
 マウス ポインターが、マウスが、コントロールの上にある場合に表示される、矢印、間、または砂時計の型を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_MousePointer(LONG* pnMousePointer);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnMousePointer*  
 マウス ポインターの型を受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegetpicturea--cstockpropimplgetpicture"></a><a name="get_picture"></a>CStockPropImpl::get_Picture  
 (アイコン、ビットマップまたはメタファイル) 表示される画像の画像のプロパティへのポインターを取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_Picture(IPictureDisp** ppPicture);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppPicture`  
 画像のプロパティへのポインターを受け取る変数。 参照してください[IPictureDisp](http://msdn.microsoft.com/library/windows/desktop/ms680762)詳細です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegetreadystatea--cstockpropimplgetreadystate"></a><a name="get_readystate"></a>CStockPropImpl::get_ReadyState  
 ロードまたはアンロードなどのコントロールの準備完了の状態を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_ReadyState(LONG* pnReadyState);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnReadyState*  
 コントロールの準備完了状態を受け取る変数。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegettabstopa--cstockpropimplgettabstop"></a><a name="get_tabstop"></a>CStockPropImpl::get_TabStop  
 コントロールがタブ ストップがかどうかかを示すフラグの状態を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_TabStop(VARIANT_BOOL* pbTabStop);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbTabStop*  
 フラグの状態を受け取る変数。 TRUE は、コントロールにタブ ストップがあることを示します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegettexta--cstockpropimplgettext"></a><a name="get_text"></a>CStockPropImpl::get_Text  
 コントロールに表示されるテキストを取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE get_Text(BSTR* pbstrText);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbstrText*  
 コントロールに表示されるテキストです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegetvalida--cstockpropimplgetvalid"></a><a name="get_valid"></a>CStockPropImpl::getvalid  
 コントロールが有効かどうかどうかかを示すフラグの状態を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL* pbValid);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbValid*  
 フラグの状態を受け取る変数。 TRUE は、コントロールが有効であることを示します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-namegetwindowa--cstockpropimplgetwindow"></a><a name="get_window"></a>CStockPropImpl::get_Window  
 コントロールに関連付けられているウィンドウ ハンドルを取得するには、このメソッドを呼び出します。 同じ[CStockPropImpl::get_HWND](#get_hwnd)します。  
  
```
HRESULT STDMETHODCALLTYPE get_Window(LONG_PTR* phWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `phWnd`  
 コントロールに関連付けられているウィンドウ ハンドル。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputappearancea--cstockpropimplputappearance"></a><a name="put_appearance"></a>CStockPropImpl::put_Appearance  
 フラット、コントロールで使われるペイント スタイルまたは 3D を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_Appearance(SHORT nAppearance);
```  
  
### <a name="parameters"></a>パラメーター  
 `nAppearance`  
 コントロールで使用する新しいペイント スタイル。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputautosizea--cstockpropimplputautosize"></a><a name="put_autosize"></a>CStockPropImpl::put_AutoSize  
 コントロールが他の任意のサイズを変更できないかどうかを示すフラグの値を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_AutoSize(VARIANT_BOOL bAutoSize,);
```  
  
### <a name="parameters"></a>パラメーター  
 *bAutoSize*  
 コントロールは、その他の任意のサイズを変更できない場合は TRUE。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputbackcolora--cstockpropimplputbackcolor"></a><a name="put_backcolor"></a>CStockPropImpl::put_BackColor  
 コントロールの背景色を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_BackColor(OLE_COLOR clrBackColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *clrBackColor*  
 新しいコントロールの背景色。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputbackstylea--cstockpropimplputbackstyle"></a><a name="put_backstyle"></a>CStockPropImpl::put_BackStyle  
 コントロールの背景のスタイルを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_BackStyle(LONG nBackStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 *nBackStyle*  
 新しいコントロールの背景のスタイル。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputbordercolora--cstockpropimplputbordercolor"></a><a name="put_bordercolor"></a>CStockPropImpl::put_BorderColor  
 コントロールの境界線の色を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_BorderColor(OLE_COLOR clrBorderColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *clrBorderColor*  
 新しい境界線の色。 OLE_COLOR データ型は内部的に 32 ビット長整数として表されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputborderstylea--cstockpropimplputborderstyle"></a><a name="put_borderstyle"></a>CStockPropImpl::put_BorderStyle  
 コントロールの境界線のスタイルを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_BorderStyle(LONG nBorderStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 *nBorderStyle*  
 新しい境界線のスタイル。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputbordervisiblea--cstockpropimplputbordervisible"></a><a name="put_bordervisible"></a>CStockPropImpl::put_BorderVisible  
 コントロールの境界線が表示されているかどうかを示すフラグの値を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_BorderVisible(VARIANT_BOOL bBorderVisible);
```  
  
### <a name="parameters"></a>パラメーター  
 *bBorderVisible*  
 境界線が表示されるようにあれば TRUE です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputborderwidtha--cstockpropimplputborderwidth"></a><a name="put_borderwidth"></a>CStockPropImpl::put_BorderWidth  
 コントロールの境界線の幅を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_BorderWidth(LONG nBorderWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 `nBorderWidth`  
 コントロールの境界線の幅。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputcaptiona--cstockpropimplputcaption"></a><a name="put_caption"></a>CStockPropImpl::put_Caption  
 コントロールに表示されるテキストを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_Caption(BSTR bstrCaption);
```  
  
### <a name="parameters"></a>パラメーター  
 *bstrCaption*  
 コントロールに表示されるテキスト。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputdrawmodea--cstockpropimplputdrawmode"></a><a name="put_drawmode"></a>CStockPropImpl::put_DrawMode  
 XOR ペン、色の反転など、コントロールの描画モードを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_DrawMode(LONG nDrawMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `nDrawMode`  
 コントロールの新しい描画モード。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputdrawstylea--cstockpropimplputdrawstyle"></a><a name="put_drawstyle"></a>CStockPropImpl::put_DrawStyle  
 実線、破線、点線などのコントロールの描画スタイルを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_DrawStyle(LONG pnDrawStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 *nDrawStyle*  
 コントロールの新しい描画スタイル。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputdrawwidtha--cstockpropimplputdrawwidth"></a><a name="put_drawwidth"></a>CStockPropImpl::put_DrawWidth  
 コントロールの描画メソッドで使用されるピクセル単位の幅を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_DrawWidth(LONG nDrawWidth);
```  
  
### <a name="parameters"></a>パラメーター  
 *nDrawWidth*  
 コントロールで使用する新しい幅での描画メソッドを使用します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputenableda--cstockpropimplputenabled"></a><a name="put_enabled"></a>CStockPropImpl::put_Enabled  
 コントロールが有効になっているかどうかを示すフラグの値を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_Enabled(VARIANT_BOOL bEnabled);
```  
  
### <a name="parameters"></a>パラメーター  
 `bEnabled`  
 コントロールが有効になっている場合は TRUE。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputfillcolora--cstockpropimplputfillcolor"></a><a name="put_fillcolor"></a>CStockPropImpl::put_FillColor  
 コントロールの塗りつぶしの色を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_FillColor(OLE_COLOR clrFillColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *clrFillColor*  
 コントロールの新しい塗りつぶしの色。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputfillstylea--cstockpropimplputfillstyle"></a><a name="put_fillstyle"></a>CStockPropImpl::put_FillStyle  
 ソリッド、透過的なまたはのクロスハッチなどのコントロールの塗りつぶしのスタイルを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_FillStyle(LONG nFillStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 *nFillStyle*  
 コントロールの新しい塗りつぶしのスタイル。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputfonta--cstockpropimplputfont"></a><a name="put_font"></a>付きます  
 コントロールのフォント プロパティを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_Font(IFontDisp* pFont);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFont`  
 コントロールのフォント プロパティへのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputforecolora--cstockpropimplputforecolor"></a><a name="put_forecolor"></a>CStockPropImpl::put_ForeColor  
 コントロールの前景の色を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_ForeColor(OLE_COLOR clrForeColor);
```  
  
### <a name="parameters"></a>パラメーター  
 *clrForeColor*  
 コントロールの新しい前景色。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputhwnda--cstockpropimplputhwnd"></a><a name="put_hwnd"></a>CStockPropImpl::put_HWND  
 このメソッドには、E_FAIL が返されます。  
  
```
HRESULT STDMETHODCALLTYPE put_HWND(LONG_PTR /* hWnd */);
```  
  
### <a name="parameters"></a>パラメーター  
 */\*hwnd の分離\*/*  
 予約済み。  
  
### <a name="return-value"></a>戻り値  
 E_FAIL を返します。  
  
### <a name="remarks"></a>コメント  
 ウィンドウ ハンドルは、読み取り専用値です。  
  
##  <a name="a-nameputmouseicona--cstockpropimplputmouseicon"></a><a name="put_mouseicon"></a>付きます  
 (アイコン、ビットマップまたはメタファイル) マウスがコントロール上にあるときに表示される画像の画像のプロパティを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_MouseIcon(IPictureDisp* pPicture);
```  
  
### <a name="parameters"></a>パラメーター  
 `pPicture`  
 グラフィックの画像のプロパティへのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputmousepointera--cstockpropimplputmousepointer"></a><a name="put_mousepointer"></a>CStockPropImpl::put_MousePointer  
 マウス ポインターが、マウスが、コントロールの上にある場合に表示される、矢印、間、または砂時計の種類を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_MousePointer(LONG nMousePointer);
```  
  
### <a name="parameters"></a>パラメーター  
 *nMousePointer*  
 マウス ポインターの型。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputpicturea--cstockpropimplputpicture"></a><a name="put_picture"></a>付きます  
 (アイコン、ビットマップまたはメタファイル) 表示される画像の画像のプロパティを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_Picture(IPictureDisp* pPicture);
```  
  
### <a name="parameters"></a>パラメーター  
 `pPicture`  
 画像のプロパティへのポインター。 参照してください[IPictureDisp](http://msdn.microsoft.com/library/windows/desktop/ms680762)詳細です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputreadystatea--cstockpropimplputreadystate"></a><a name="put_readystate"></a>CStockPropImpl::put_ReadyState  
 ロードまたはアンロードなどのコントロールの準備完了の状態を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_ReadyState(LONG nReadyState);
```  
  
### <a name="parameters"></a>パラメーター  
 *nReadyState*  
 コントロールの準備完了状態。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputtabstopa--cstockpropimplputtabstop"></a><a name="put_tabstop"></a>CStockPropImpl::put_TabStop  
 コントロールがタブ ストップかかどうかかを示すフラグを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_TabStop(VARIANT_BOOL bTabStop);
```  
  
### <a name="parameters"></a>パラメーター  
 *bTabStop*  
 コントロールがタブ ストップの場合は TRUE。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputtexta--cstockpropimplputtext"></a><a name="put_text"></a>CStockPropImpl::put_Text  
 コントロールに表示されるテキストを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE put_Text(BSTR bstrText);
```  
  
### <a name="parameters"></a>パラメーター  
 `bstrText`  
 コントロールに表示されるテキストです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputvalida--cstockpropimplputvalid"></a><a name="put_valid"></a>CStockPropImpl::putvalid  
 コントロールが有効かどうかどうかかを示すフラグを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL bValid);
```  
  
### <a name="parameters"></a>パラメーター  
 *bValid*  
 コントロールが有効な場合は TRUE。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="a-nameputwindowa--cstockpropimplputwindow"></a><a name="put_window"></a>CStockPropImpl::put_Window  
 このメソッドを呼び出す[CStockPropImpl::put_HWND](#put_hwnd)E_FAIL が返されます。  
  
```
HRESULT STDMETHODCALLTYPE put_Window(LONG_PTR hWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 ウィンドウ ハンドル。  
  
### <a name="return-value"></a>戻り値  
 E_FAIL を返します。  
  
### <a name="remarks"></a>コメント  
 ウィンドウ ハンドルは、読み取り専用値です。  
  
##  <a name="a-nameputreffonta--cstockpropimplputreffont"></a><a name="putref_font"></a>CStockPropImpl::putref_Font  
 参照カウント付きのコントロールのフォント プロパティを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE putref_Font(IFontDisp* pFont);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFont`  
 コントロールのフォント プロパティへのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 同じ[付きます](#put_font)、ですが、参照カウントをインクリメントします。  
  
##  <a name="a-nameputrefmouseicona--cstockpropimplputrefmouseicon"></a><a name="putref_mouseicon"></a>CStockPropImpl::putref_MouseIcon  
 参照カウントを持つ (アイコン、ビットマップまたはメタファイル) マウスがコントロール上にあるときに表示される画像の画像のプロパティを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE putref_MouseIcon(IPictureDisp* pPicture);
```  
  
### <a name="parameters"></a>パラメーター  
 `pPicture`  
 グラフィックの画像のプロパティへのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 同じ[付きます](#put_mouseicon)、ですが、参照カウントをインクリメントします。  
  
##  <a name="a-nameputrefpicturea--cstockpropimplputrefpicture"></a><a name="putref_picture"></a>CStockPropImpl::putref_Picture  
 参照カウントを持つ (アイコン、ビットマップまたはメタファイル) 表示される画像の画像のプロパティを設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE putref_Picture(IPictureDisp* pPicture);
```  
  
### <a name="parameters"></a>パラメーター  
 `pPicture`  
 画像のプロパティへのポインター。 参照してください[IPictureDisp](http://msdn.microsoft.com/library/windows/desktop/ms680762)詳細です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 同じ[付きます](#put_picture)、ですが、参照カウントをインクリメントします。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [IDispatchImpl クラス](../../atl/reference/idispatchimpl-class.md)

