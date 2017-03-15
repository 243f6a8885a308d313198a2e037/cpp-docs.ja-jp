---
title: "CMFCPropertyGridFontProperty クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertyGridFontProperty
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridFontProperty::OnClickButton method
- CMFCPropertyGridFontProperty class
- CMFCPropertyGridFontProperty::FormatProperty method
ms.assetid: 83693f33-bbd3-4fcb-a9ad-fa79fcf2ca24
caps.latest.revision: 23
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
ms.openlocfilehash: 05d1db7e7de2ee72244e885d8a083ac3cda20142
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpropertygridfontproperty-class"></a>CMFCPropertyGridFontProperty クラス
`CMFCPropertyGridFileProperty`クラスは、フォントの選択 ダイアログ ボックスを開くプロパティ リスト コントロール項目をサポートしています。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCPropertyGridFontProperty : public CMFCPropertyGridProperty  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty](#cmfcpropertygridfontproperty)|`CMFCPropertyGridFontProperty` オブジェクトを構築します。|  
|`CMFCPropertyGridFontProperty::~CMFCPropertyGridFontProperty`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCPropertyGridFontProperty::FormatProperty`|プロパティ値のテキスト表現の書式を設定します  (上書き[CMFCPropertyGridProperty::FormatProperty](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty))。|  
|[CMFCPropertyGridFontProperty::GetColor](#getcolor)|ユーザーが、[フォント] ダイアログ ボックスから選択したフォントの色を取得します。|  
|[CMFCPropertyGridFontProperty::GetLogFont](#getlogfont)|ユーザーが、[フォント] ダイアログ ボックスから選択したフォントを取得します。|  
|`CMFCPropertyGridFontProperty::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|`CMFCPropertyGridFontProperty::OnClickButton`|プロパティに含まれているボタンをユーザーがクリックすると、フレームワークによって呼び出されます  (上書き[CMFCPropertyGridProperty::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton))。|  
  
## <a name="remarks"></a>コメント  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridFontProperty](../../mfc/reference/cmfcpropertygridfontproperty-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxpropertygridctrl.h  
  
##  <a name="a-namecmfcpropertygridfontpropertya--cmfcpropertygridfontpropertycmfcpropertygridfontproperty"></a><a name="cmfcpropertygridfontproperty"></a>CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty  
 `CMFCPropertyGridFontProperty` オブジェクトを構築します。  
  
```  
CMFCPropertyGridFontProperty(
    const CString& strName,  
    LOGFONT& lf,  
    DWORD dwFontDialogFlags = CF_EFFECTS | CF_SCREENFONTS,  
    LPCTSTR lpszDescr = NULL,  
    DWORD_PTR dwData = 0,  
    COLORREF color = (COLORREF)-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `strName`  
 プロパティの名前。  
  
 [入力] `lf`  
 フォントの属性を指定するための論理フォント構造体。  
  
 [入力] `dwFontDialogFlags`  
 プロパティ値のドロップダウン ボタンをクリックするときに表示される [フォント] ダイアログ ボックスに適用されるスタイルです。 既定値は、CF_EFFECTS と CF_SCREENFONTS のビットごとの組み合わせ (OR です)。 詳細については、次を参照してください。、`Flags`のパラメーター、 [CHOOSEFONT 構造](http://msdn.microsoft.com/library/windows/desktop/ms646832)します。  
  
 [入力] `lpszDescr`  
 フォントのプロパティの説明です。 既定値は `NULL` です。  
  
 [入力] `dwData`  
 整数値またはプロパティに関連付けられているその他のデータへのポインターなどのアプリケーションに固有のデータです。 既定値は 0 です。  
  
 [入力] `color`  
 フォントの色。 既定値は既定の色です。  
  
### <a name="remarks"></a>コメント  
 A`CMFCPropertyGridFontProperty`オブジェクトのフォントのプロパティ グリッド コントロールのフォント プロパティを表します。  
  
### <a name="example"></a>例  
 次の例でのオブジェクトを作成する方法、`CMFCPropertyGridFontProperty`クラスです。 この例は、[新しいコントロールのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_NewControls #&26;](../../mfc/reference/codesnippet/cpp/cmfcpropertygridfontproperty-class_1.cpp)]  
  
##  <a name="a-namegetcolora--cmfcpropertygridfontpropertygetcolor"></a><a name="getcolor"></a>CMFCPropertyGridFontProperty::GetColor  
 ユーザーが、[フォント] ダイアログ ボックスから選択したフォントの色を取得します。  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択したフォントの色を表す RGB カラー値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namegetlogfonta--cmfcpropertygridfontpropertygetlogfont"></a><a name="getlogfont"></a>CMFCPropertyGridFontProperty::GetLogFont  
 ユーザーが、[フォント] ダイアログ ボックスから選択したフォントを取得します。  
  
```  
LPLOGFONT GetLogFont();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)選択したフォントを表す構造体。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertyGridCtrl クラス](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [CMFCPropertyGridProperty クラス](../../mfc/reference/cmfcpropertygridproperty-class.md)

