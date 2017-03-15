---
title: "標準的なダイアログ データ バリデーション ルーチン |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- standard dialog, data validation routines
ms.assetid: 44dbc222-a897-4949-925e-7660e8964ccd
caps.latest.revision: 13
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 87cf0389b7b58579a8674d4075d2601186b1ae95
ms.lasthandoff: 02/24/2017

---
# <a name="standard-dialog-data-validation-routines"></a>標準的なダイアログ データ検証ルーチン
このトピックでは、共通の MFC ダイアログ コントロールに使用される標準的なダイアログ データ バリデーション (DDV) ルーチンを示します。  
  
> [!NOTE]
>  標準的なダイアログ データ エクス チェンジ ルーチンは、ヘッダー ファイル afxdd_.h で定義されます。 ただし、アプリケーションでは、afxwin.h を含める必要があります。  
  
### <a name="ddv-functions"></a>DDV 関数  
  
|||  
|-|-|  
|[DDV_MaxChars](#ddv_maxchars)|指定されたコントロール値の文字の数が指定された最大値を超えていないことを確認します。|  
|[DDV_MinMaxByte](#ddv_minmaxbyte)|指定されたコントロール値を超えていないことを確認、指定された**バイト**範囲です。|  
|[DDV_MinMaxDateTime](#ddv_minmaxdatetime)|指定されたコントロール値が特定の時間範囲を超えていないことを確認します。|  
|[DDV_MinMaxDouble](#ddv_minmaxdouble)|指定されたコントロール値を超えていないことを確認、指定された**二重**範囲です。|  
|[DDV_MinMaxDWord](#ddv_minmaxdword)|指定されたコントロール値を超えていないことを確認、指定された**DWORD**範囲です。|  
|[DDV_MinMaxFloat](#ddv_minmaxfloat)|指定されたコントロール値を超えていないことを確認、指定された**float**範囲です。|  
|[DDV_MinMaxInt](#ddv_minmaxint)|指定されたコントロール値を超えていないことを確認、指定された**int**範囲です。|  
|[DDV_MinMaxLong](#ddv_minmaxlong)|指定されたコントロール値を超えていないことを確認、指定された**長い**範囲です。|  
|[DDV_MinMaxLongLong](#ddv_minmaxlonglong)|指定されたコントロール値を超えていないことを確認、指定された**LONGLONG**範囲です。|  
|[DDV_MinMaxMonth](#ddv_minmaxmonth)|指定されたコントロール値が指定した日付範囲を超えていないことを確認します。|  
|[DDV_MinMaxShort](#ddv_minmaxshort)|指定されたコントロール値を超えていないことを確認、指定された**短い**範囲です。|  
|[DDV_MinMaxSlider](#ddv_minmaxslider)|特定のスライダー コントロールの値が指定された範囲内にあることを確認します。|  
|[DDV_MinMaxUInt](#ddv_minmaxuint)|指定されたコントロール値を超えていないことを確認、指定された**UINT**範囲です。|  
|[DDV_MinMaxULongLong](#ddv_minmaxulonglong)|指定されたコントロール値を超えていないことを確認、指定された**使い**範囲です。|  
  

  
##  <a name="a-nameddvmaxcharsa--ddvmaxchars"></a><a name="ddv_maxchars"></a>DDV_MaxChars  
 呼び出す`DDV_MaxChars`コントロール内の文字の量に関連付けられていることを確認する*値*を超えない*文字数*します。  
  
```   
void AFXAPI DDV_MaxChars(
    CDataExchange* pDX,  
    CString const& value,  
    int nChars); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *value*  
 ダイアログ ボックス、フォーム ビュー、またはデータを検証するオブジェクトのメンバー変数への参照。  
  
 `nChars`  
 使用できる文字の最大数。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddvminmaxbytea--ddvminmaxbyte"></a><a name="ddv_minmaxbyte"></a>DDV_MinMaxByte  
 呼び出す`DDV_MinMaxByte`コントロールの値に関連付けられていることを確認する*値*間`minVal`と`maxVal`です。  
  
```   
void AFXAPI DDV_MinMaxByte(
    CDataExchange* pDX,  
    BYTE value,  
    BYTE minVal,  
    BYTE maxVal); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *value*  
 ダイアログ ボックス、フォーム ビュー、またはデータを検証するオブジェクトのメンバー変数への参照。  
  
 `minVal`  
 最小値 (型の**バイト**) 許可します。  
  
 `maxVal`  
 最大値 (型の**バイト**) 許可します。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddvminmaxdatetimea--ddvminmaxdatetime"></a><a name="ddv_minmaxdatetime"></a>DDV_MinMaxDateTime  
 呼び出す`DDV_MinMaxDateTime`、日付と時刻の選択で日付/時刻値を制御することを確認する ( [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)) に関連付けられている*refValue*間`refMinRange`と`refMaxRange`です。  
  
```   
void AFXAPI DDV_MinMaxDateTime(
    CDataExchange* pDX,  
    CTime& refValue,  
    const CTime* refMinRange,  
    const CTime* refMaxRange);

void AFXAPI DDV_MinMaxDateTime(
    CDataExchange* pDX,  
    COleDateTime& refValue,  
    const COleDateTime* refMinRange,  
    const COleDateTime* refMaxRange); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。 このオブジェクトを削除する必要はありません。  
  
 *refValue*  
 参照、 [CTime](../../atl-mfc-shared/reference/ctime-class.md)または[時刻](../../atl-mfc-shared/reference/coledatetime-class.md) ダイアログ ボックス、フォーム ビュー、またはオブジェクトのメンバー変数に関連付けられているオブジェクト。 このオブジェクトには、検証するデータが含まれています。  
  
 `refMinRange`  
 最小許容される値の日付/時刻です。  
  
 `refMaxRange`  
 許容される最大の日付/時刻値。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddvminmaxdoublea--ddvminmaxdouble"></a><a name="ddv_minmaxdouble"></a>DDV_MinMaxDouble  
 呼び出す`DDV_MinMaxDouble`コントロールの値に関連付けられていることを確認する*値*間`minVal`と`maxVal`です。  
  
```   
void AFXAPI DDV_MinMaxDouble(
    CDataExchange* pDX,  
    double const& value,  
    double minVal,  
    double maxVal); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *value*  
 ダイアログ ボックス、フォーム ビュー、またはデータを検証するオブジェクトのメンバー変数への参照。  
  
 `minVal`  
 最小値 (型の**二重**) 許可します。  
  
 `maxVal`  
 最大値 (型の**二重**) 許可します。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddvminmaxdworda--ddvminmaxdword"></a><a name="ddv_minmaxdword"></a>DDV_MinMaxDWord  
 呼び出す`DDV_MinMaxDWord`コントロールの値に関連付けられていることを確認する*値*間`minVal`と`maxVal`です。  
  
```   
void AFXAPI DDV_MinMaxDWord(
    CDataExchange* pDX,  
    DWORD const& value,  
    DWORD minVal,  
    DWORD maxVal); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *value*  
 ダイアログ ボックス、フォーム ビュー、またはデータを検証するオブジェクトのメンバー変数への参照。  
  
 `minVal`  
 最小値 (型の`DWORD`) 許可します。  
  
 `maxVal`  
 最大値 (型の`DWORD`) 許可します。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddvminmaxfloata--ddvminmaxfloat"></a><a name="ddv_minmaxfloat"></a>DDV_MinMaxFloat  
 呼び出す`DDV_MinMaxFloat`コントロールの値に関連付けられていることを確認する*値*間`minVal`と`maxVal`です。  
  
```   
void AFXAPI DDV_MinMaxFloat(
    CDataExchange* pDX,  
    float value,  
    float minVal,  
    float maxVal); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *value*  
 ダイアログ ボックス、フォーム ビュー、またはデータを検証するオブジェクトのメンバー変数への参照。  
  
 `minVal`  
 最小値 (型の**float**) 許可します。  
  
 `maxVal`  
 最大値 (型の**float**) 許可します。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddvminmaxinta--ddvminmaxint"></a><a name="ddv_minmaxint"></a>DDV_MinMaxInt  
 呼び出す`DDV_MinMaxInt`コントロールの値に関連付けられていることを確認する*値*間`minVal`と`maxVal`です。  
  
```   
void AFXAPI DDV_MinMaxInt(
    CDataExchange* pDX,  
    int value,  
    int minVal,  
    int maxVal); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *value*  
 ダイアログ ボックス、フォーム ビュー、またはデータを検証するオブジェクトのメンバー変数への参照。  
  
 `minVal`  
 最小値 (型の`int`) 許可します。  
  
 `maxVal`  
 最大値 (型の`int`) 許可します。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddvminmaxlonga--ddvminmaxlong"></a><a name="ddv_minmaxlong"></a>DDV_MinMaxLong  
 呼び出す`DDV_MinMaxLong`コントロールの値に関連付けられていることを確認する*値*間`minVal`と`maxVal`です。  
  
```   
void AFXAPI DDV_MinMaxLong(
    CDataExchange* pDX,  
    long value,  
    long minVal,  
    long maxVal); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *value*  
 ダイアログ ボックス、フォーム ビュー、またはデータを検証するオブジェクトのメンバー変数への参照。  
  
 `minVal`  
 最小値 (型の**長い**) 許可します。  
  
 `maxVal`  
 最大値 (型の**長い**) 許可します。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddvminmaxlonglonga--ddvminmaxlonglong"></a><a name="ddv_minmaxlonglong"></a>DDV_MinMaxLongLong  
 呼び出す`DDV_MinMaxLongLong`コントロールの値に関連付けられていることを確認する*値*間`minVal`と`maxVal`です。  
  
```   
void AFXAPI DDV_MinMaxLongLong(
    CDataExchange* pDX,  
    LONGLONG value,  
    LONGLONG minVal,  
    LONGLONG maxVal); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *value*  
 ダイアログ ボックス、フォーム ビュー、またはデータを検証するオブジェクトのメンバー変数への参照。  
  
 `minVal`  
 最小値 (型の**LONGLONG**) 許可します。  
  
 `maxVal`  
 最大値 (型の**LONGLONG**) 許可します。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddvminmaxmontha--ddvminmaxmonth"></a><a name="ddv_minmaxmonth"></a>DDV_MinMaxMonth  
 呼び出す`DDV_MinMaxMonth`か月の暦の日付/時刻値を制御することを確認する ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)) に関連付けられている*refValue*間`refMinRange`と`refMaxRange`です。  
  
```   
void AFXAPI DDV_MinMaxMonth(
    CDataExchange* pDX,  
    CTime& refValue,  
    const CTime* refMinRange,  
    const CTime* refMaxRange);

void AFXAPI DDV_MinMaxMonth(
    CDataExchange* pDX,  
    COleDateTime& refValue,  
    const COleDateTime* refMinRange,  
    const COleDateTime* refMaxRange); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *refValue*  
 型のオブジェクトへの参照を`CTime`または`COleDateTime` ダイアログ ボックスのメンバー変数に関連付けられている、フォーム ビュー、またはオブジェクトの表示を制御します。 このオブジェクトには、検証するデータが含まれています。 この参照の場合に MFC パス`DDV_MinMaxMonth`が呼び出されます。  
  
 `refMinRange`  
 最小許容される値の日付/時刻です。  
  
 `refMaxRange`  
 許容される最大の日付/時刻値。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddvminmaxshorta--ddvminmaxshort"></a><a name="ddv_minmaxshort"></a>DDV_MinMaxShort  
 呼び出す`DDV_MinMaxShort`コントロールの値に関連付けられていることを確認する*値*間`minVal`と`maxVal`です。  
  
```   
void AFXAPI DDV_MinMaxShort(
    CDataExchange* pDX,  
    short value,  
    short minVal,  
    short maxVal); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *value*  
 ダイアログ ボックス、フォーム ビュー、またはデータを検証するオブジェクトのメンバー変数への参照。  
  
 `minVal`  
 最小値 (型の**短い**) 許可します。  
  
 `maxVal`  
 最大値 (型の**短い**) 許可します。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddvminmaxslidera--ddvminmaxslider"></a><a name="ddv_minmaxslider"></a>DDV_MinMaxSlider  
 呼び出す`DDV_MinMaxSlider`コントロールの値に関連付けられていることを確認する*値*間`minVal`と`maxVal`です。  
  
```   
void AFXAPI DDV_MinMaxSlider(
    CDataExchange* pDX,  
    DWORD value,  
    DWORD minVal,  
    DWORD maxVal); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 ポインター、 [CDataExchange](../../mfc/reference/cdataexchange-class.md)オブジェクトです。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *value*  
 検証する値への参照。 このパラメーターは、スライダー コントロールのつまみの現在の位置を設定または保持します。  
  
 `minVal`  
 許容される最小値。  
  
 `maxVal`  
 許容される最大値。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。 スライダー コントロールの概要については、次を参照してください。[を使用して CSliderCtrl](../../mfc/using-csliderctrl.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddvminmaxuinta--ddvminmaxuint"></a><a name="ddv_minmaxuint"></a>DDV_MinMaxUInt  
 呼び出す`DDV_MinMaxUInt`コントロールの値に関連付けられていることを確認する*値*間`minVal`と`maxVal`です。  
  
```   
void AFXAPI DDV_MinMaxUInt(
    CDataExchange* pDX,  
    UINT value,  
    UINT minVal,  
    UINT maxVal); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *value*  
 ダイアログ ボックス、フォーム ビュー、またはデータを検証するオブジェクトのメンバー変数への参照。  
  
 `minVal`  
 最小値 (型の**UINT**) 許可します。  
  
 `maxVal`  
 最大値 (型の**UINT**) 許可します。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
  
##  <a name="a-nameddvminmaxulonglonga--ddvminmaxulonglong"></a><a name="ddv_minmaxulonglong"></a>DDV_MinMaxULongLong  
 呼び出す`DDV_MinMaxULongLong`コントロールの値に関連付けられていることを確認する*値*間`minVal`と`maxVal`です。  
  
```   
void AFXAPI DDV_MinMaxULongLong(
    CDataExchange* pDX,  
    ULONGLONG value,  
    ULONGLONG  minVal ,  
    ULONGLONG  maxVal); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDX`  
 `CDataExchange` オブジェクトへのポインター。 フレームワークは、データ交換のコンテキスト (交換方向を含みます) を確定するためにこのオブジェクトを提供します。  
  
 *value*  
 ダイアログ ボックス、フォーム ビュー、またはデータを検証するオブジェクトのメンバー変数への参照。  
  
 `minVal`  
 最小値 (型の**使い**) 許可します。  
  
 `maxVal`  
 最大値 (型の**使い**) 許可します。  
  
### <a name="remarks"></a>コメント  
 DDV の詳細については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)します。  

### <a name="requirements"></a>要件  
  **ヘッダー** afxdd_.h  
    
## <a name="see-also"></a>関連項目  
 [標準的なダイアログ データ エクス チェンジ ルーチン](../../mfc/reference/standard-dialog-data-exchange-routines.md)   
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

