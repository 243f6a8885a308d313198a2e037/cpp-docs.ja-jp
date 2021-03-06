---
title: CComboBoxEx クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CComboBoxEx
- AFXCMN/CComboBoxEx
- AFXCMN/CComboBoxEx::CComboBoxEx
- AFXCMN/CComboBoxEx::Create
- AFXCMN/CComboBoxEx::CreateEx
- AFXCMN/CComboBoxEx::DeleteItem
- AFXCMN/CComboBoxEx::GetComboBoxCtrl
- AFXCMN/CComboBoxEx::GetEditCtrl
- AFXCMN/CComboBoxEx::GetExtendedStyle
- AFXCMN/CComboBoxEx::GetImageList
- AFXCMN/CComboBoxEx::GetItem
- AFXCMN/CComboBoxEx::HasEditChanged
- AFXCMN/CComboBoxEx::InsertItem
- AFXCMN/CComboBoxEx::SetExtendedStyle
- AFXCMN/CComboBoxEx::SetImageList
- AFXCMN/CComboBoxEx::SetItem
- AFXCMN/CComboBoxEx::SetWindowTheme
dev_langs:
- C++
helpviewer_keywords:
- CComboBoxEx [MFC], CComboBoxEx
- CComboBoxEx [MFC], Create
- CComboBoxEx [MFC], CreateEx
- CComboBoxEx [MFC], DeleteItem
- CComboBoxEx [MFC], GetComboBoxCtrl
- CComboBoxEx [MFC], GetEditCtrl
- CComboBoxEx [MFC], GetExtendedStyle
- CComboBoxEx [MFC], GetImageList
- CComboBoxEx [MFC], GetItem
- CComboBoxEx [MFC], HasEditChanged
- CComboBoxEx [MFC], InsertItem
- CComboBoxEx [MFC], SetExtendedStyle
- CComboBoxEx [MFC], SetImageList
- CComboBoxEx [MFC], SetItem
- CComboBoxEx [MFC], SetWindowTheme
ms.assetid: 33ca960a-2409-478c-84a4-a2ee8ecfe8f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ca12ba74df7099aa137e5e7dc9c1b8b75131ab66
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336619"
---
# <a name="ccomboboxex-class"></a>CComboBoxEx クラス
イメージ リストをサポートすることにより、コンボ ボックス コントロールを拡張します。  
  
## <a name="syntax"></a>構文  
  
```  
class CComboBoxEx : public CComboBox  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComboBoxEx::CComboBoxEx](#ccomboboxex)|`CComboBoxEx` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComboBoxEx::Create](#create)|コンボ ボックスを作成し、それにアタッチします、`CComboBoxEx`オブジェクト。|  
|[CComboBoxEx::CreateEx](#createex)|指定された Windows の拡張スタイルのコンボ ボックスを作成しにアタッチします、`ComboBoxEx`オブジェクト。|  
|[CComboBoxEx::DeleteItem](#deleteitem)|項目を削除する`ComboBoxEx`コントロール。|  
|[CComboBoxEx::GetComboBoxCtrl](#getcomboboxctrl)|子のコンボ ボックス コントロールへのポインターを取得します。|  
|[CComboBoxEx::GetEditCtrl](#geteditctrl)|編集コントロールの部分を識別するハンドルを取得、`ComboBoxEx`コントロール。|  
|[CComboBoxEx::GetExtendedStyle](#getextendedstyle)|使用されている拡張スタイルを取得、`ComboBoxEx`コントロール。|  
|[CComboBoxEx::GetImageList](#getimagelist)|割り当てられているイメージ リストへのポインターを取得、`ComboBoxEx`コントロール。|  
|[CComboBoxEx::GetItem](#getitem)|項目の情報の取得を指定した`ComboBoxEx`項目。|  
|[CComboBoxEx::HasEditChanged](#haseditchanged)|決定の内容をユーザーが変更されたかどうか、 `ComboBoxEx` 」と入力してコントロールを編集します。|  
|[CComboBoxEx::InsertItem](#insertitem)|新しい項目を挿入、`ComboBoxEx`コントロール。|  
|[CComboBoxEx::SetExtendedStyle](#setextendedstyle)|内の拡張スタイルを設定、`ComboBoxEx`コントロール。|  
|[CComboBoxEx::SetImageList](#setimagelist)|イメージ リストの設定、`ComboBoxEx`コントロール。|  
|[CComboBoxEx::SetItem](#setitem)|内の項目の属性を設定、`ComboBoxEx`コントロール。|  
|[CComboBoxEx::SetWindowTheme](#setwindowtheme)|Visual スタイル拡張コンボ ボックス コントロールを設定します。|  
  
## <a name="remarks"></a>Remarks  
 使用して`CComboBoxEx`コンボ ボックス コントロールを作成するが不要になった、独自のイメージが描画コードを実装します。 代わりに、`CComboBoxEx`イメージの一覧からイメージをアクセスします。  
  
## <a name="image-list-support"></a>イメージ リストのサポート  
 標準のコンボ ボックスでは、コンボ ボックスのオーナーが、オーナー描画コントロールとしてコンボ ボックスを作成して、イメージの描画を担当します。 使用すると`CComboBoxEx`は暗黙的に指定するために、CBS_OWNERDRAWFIXED と CBS_HASSTRINGS の描画スタイルを設定する必要はありません。 それ以外の場合、描画操作を実行するコードを記述する必要があります。 A`CComboBoxEx`コントロールは、項目ごとに最大 3 つのイメージをサポートしています: 非選択の状態とオーバーレイ画像の選択された状態のいずれか。  
  
## <a name="styles"></a>スタイル  
 `CComboBoxEx` CBS_SIMPLE、CBS_DROPDOWN、CBS_DROPDOWNLIST、および WS_CHILD スタイルをサポートしています。 ウィンドウを作成するときに渡されるその他のすべてのスタイルはコントロールによって無視されます。 ウィンドウを作成すると、後に行うことができます他のコンボ ボックス スタイルを呼び出して、`CComboBoxEx`メンバー関数は[SetExtendedStyle](#setextendedstyle)します。 これらのスタイルは、次のことができます。  
  
-   大文字小文字を区別する、一覧のセットの文字列を検索します。  
  
-   コンボ ボックス コントロールを作成 ('/')、スラッシュを円記号 ('\\')、および期間 ('. ') 文字の単語の区切り記号として。 これは、キーボード ショートカット CTRL + 方向キーを使用して word から word に移動するようにします。  
  
-   コンボ ボックス コントロールを表示または表示イメージのいずれかを設定します。 イメージが表示されない場合、コンボ ボックスはイメージに対応するテキストのインデントを削除できます。  
  
-   含まれているより多くのコンボ ボックスをクリップするためのサイズ変更など、狭いコンボ ボックス コントロールを作成します。  
  
 これらのスタイル フラグの詳細については[を使用して CComboBoxEx](../../mfc/using-ccomboboxex.md)します。  
  
## <a name="item-retention-and-callback-item-attributes"></a>アイテムの保持とコールバック項目属性  
 Win32 構造内の項目とイメージ、インデント、およびテキスト文字列のインデックスなどの項目の情報が格納されている[受け取る](http://msdn.microsoft.com/library/windows/desktop/bb775746)」の説明に従って、Windows SDK。 構造体には、コールバック フラグに対応するメンバーも含まれています。  
  
 詳細な概念については、次を参照してください。[を使用して CComboBoxEx](../../mfc/using-ccomboboxex.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 `CComboBoxEx`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="ccomboboxex"></a>  CComboBoxEx::CComboBoxEx  
 作成するには、このメンバー関数を呼び出す、`CComboBoxEx`オブジェクト。  
  
```  
CComboBoxEx();
```  
  
##  <a name="create"></a>  CComboBoxEx::Create  
 コンボ ボックスを作成し、それにアタッチします、`CComboBoxEx`オブジェクト。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwStyle*  
 コンボ ボックスに適用されるコンボ ボックス スタイルの組み合わせを指定します。 参照してください**解説**下スタイルの詳細についてはします。  
  
 *rect*  
 参照を[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)コンボ ボックスのサイズと位置である構造体。  
  
 *pParentWnd*  
 ポインターを[CWnd](../../mfc/reference/cwnd-class.md)コンボ ボックスの親ウィンドウは、オブジェクト (通常、 `CDialog`)。 NULL は指定できません。  
  
 *nID*  
 コンボ ボックスのコントロール ID を指定します  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが正常に作成された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 作成、 `CComboBoxEx` 2 つのステップ内のオブジェクト。  
  
1.  呼び出す[CComboBoxEx](#ccomboboxex)を構築する、`CComboBoxEx`オブジェクト。  
  
2.  拡張 Windows コンボ ボックスの作成およびにアタッチしますこのメンバー関数の呼び出し、`CComboBoxEx`オブジェクト。  
  
 呼び出すと`Create`、MFC コモン コントロールを初期化します。  
  
 コンボ ボックスを作成するときに、次のコンボ ボックス スタイルの一部またはすべてを指定できます。  
  
- CBS_SIMPLE  
  
- CBS_DROPDOWN  
  
- CBS_DROPDOWNLIST  
  
- CBS_AUTOHSCROLL  
  
- WS_CHILD  
  
 ウィンドウを作成するときに渡されるその他のすべてのスタイルは無視されます。 `ComboBoxEx`コントロールには、追加の機能を提供する拡張スタイルもサポートしています。 これらのスタイルが記載されて[ComboBoxEx コントロールの拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775742)、Windows SDK に含まれています。 これらのスタイルを呼び出すことによって設定[SetExtendedStyle](#setextendedstyle)します。  
  
 コントロールで拡張ウィンドウ スタイルを使用する場合は、呼び出す[CreateEx](#createex)の代わりに`Create`します。  
  
##  <a name="createex"></a>  CComboBoxEx::CreateEx  
 拡張コンボ ボックス コントロール (子ウィンドウ) を作成し、それをするには、この関数を呼び出して、`CComboBoxEx`オブジェクト。  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwExStyle*  
 作成されるコントロールの拡張スタイルを指定します。 拡張 Windows スタイルの一覧は、次を参照してください。、 *dwExStyle*パラメーターを[CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Windows SDK に含まれています。  
  
 *dwStyle*  
 コンボ ボックス コントロールのスタイル。 参照してください[作成](#create)スタイルの一覧。  
  
 *rect*  
 参照を[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)のクライアント座標で、作成するには、ウィンドウの位置とサイズを記述する構造体*pParentWnd*します。  
  
 *pParentWnd*  
 コントロールの親であるウィンドウへのポインター。  
  
 *nID*  
 コントロールの子ウィンドウ ID  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 使用`CreateEx`の代わりに`Create`、Windows の拡張スタイルの先頭で指定された、Windows の拡張スタイルを適用する**WS_EX**します。  
  
 `CreateEx` 指定された拡張の Windows スタイルでコントロールを作成します。 *dwExStyle*します。 設定する拡張スタイル固有拡張コンボ ボックス コントロールを使用して、 [SetExtendedStyle](#setextendedstyle)します。 たとえば、使用して`CreateEx`WS_EX_CONTEXTHELP、としてこのようなスタイルの設定が使用する`SetExtendedStyle`CBES_EX_CASESENSITIVE としてこのようなスタイルを設定します。 詳細については、トピックで説明されているスタイルを参照してください。 [ComboBoxEx コントロールの拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775742)Windows SDK に含まれています。  
  
##  <a name="deleteitem"></a>  CComboBoxEx::DeleteItem  
 項目を削除する`ComboBoxEx`コントロール。  
  
```  
int DeleteItem(int iIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 *iIndex*  
 削除する項目の 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 コントロール内の残りの項目の数。 場合*iIndex*は、無効な CB_ERR は、関数に返されます。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、メッセージの機能を実装[CBEM_DELETEITEM](http://msdn.microsoft.com/library/windows/desktop/bb775768)」の説明に従って、Windows SDK。 DeleteItem を呼び出すときに、 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) CBEN_DELETEITEM 通知メッセージが親ウィンドウに送信されます。  
  
##  <a name="getcomboboxctrl"></a>  CComboBoxEx::GetComboBoxCtrl  
 内のコンボ ボックス コントロールへのポインターを取得するには、このメンバー関数を呼び出す、`CComboBoxEx`オブジェクト。  
  
```  
CComboBox* GetComboBoxCtrl();
```  
  
### <a name="return-value"></a>戻り値  
 ポインターを`CComboBox`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 `CComboBoxEx`カプセル化されている親ウィンドウのコントロールでは、`CComboBox`します。  
  
 `CComboBox`戻り値によってポイントされるオブジェクトは一時オブジェクトし、[次へ] のアイドル状態の処理時に破棄します。  
  
##  <a name="geteditctrl"></a>  CComboBoxEx::GetEditCtrl  
 コンボ ボックス編集コントロールにポインターを取得するには、このメンバー関数を呼び出します。  
  
```  
CEdit* GetEditCtrl();
```  
  
### <a name="return-value"></a>戻り値  
 ポインターを[CEdit](../../mfc/reference/cedit-class.md)オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 A `CComboBoxEx` CBS_DROPDOWN スタイルを使用して作成されたときに、コントロールが編集ボックスを使用します。  
  
 `CEdit`戻り値によってポイントされるオブジェクトは一時オブジェクトし、[次へ] のアイドル状態の処理時に破棄します。  
  
##  <a name="getextendedstyle"></a>  CComboBoxEx::GetExtendedStyle  
 使用される拡張スタイルを取得するには、このメンバー関数を呼び出す、`CComboBoxEx`コントロール。  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コンボ ボックス コントロールに使用される拡張スタイル DWORD の値です。  
  
### <a name="remarks"></a>Remarks  
 参照してください[ComboBoxEx コントロールの拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775742)これらのスタイルの詳細については、Windows SDK に含まれています。  
  
##  <a name="getimagelist"></a>  CComboBoxEx::GetImageList  
 によって使用されるイメージの一覧へのポインターを取得するには、このメンバー関数を呼び出し、`CComboBoxEx`コントロール。  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインターを[CImageList](../../mfc/reference/cimagelist-class.md)オブジェクト。 失敗した場合、このメンバー関数は NULL を返します。  
  
### <a name="remarks"></a>Remarks  
 `CImageList`戻り値によってポイントされるオブジェクトは一時オブジェクトし、[次へ] のアイドル状態の処理時に破棄します。  
  
##  <a name="getitem"></a>  CComboBoxEx::GetItem  
 項目の情報の取得を指定した`ComboBoxEx`項目。  
  
```  
BOOL GetItem(COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>パラメーター  
 *pCBItem*  
 ポインターを[受け取る](http://msdn.microsoft.com/library/windows/desktop/bb775746)項目の情報を受け取る構造体。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合、0 以外の場合それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、メッセージの機能を実装[CBEM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb775779)」の説明に従って、Windows SDK。  
  
##  <a name="haseditchanged"></a>  CComboBoxEx::HasEditChanged  
 決定の内容をユーザーが変更されたかどうか、 `ComboBoxEx` 」と入力してコントロールを編集します。  
  
```  
BOOL HasEditChanged();
```  
  
### <a name="return-value"></a>戻り値  
 コントロールのエディット ボックスで、ユーザーが入力した場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、メッセージの機能を実装[CBEM_HASEDITCHANGED](http://msdn.microsoft.com/library/windows/desktop/bb775782)」の説明に従って、Windows SDK。  
  
##  <a name="insertitem"></a>  CComboBoxEx::InsertItem  
 新しい項目を挿入、`ComboBoxEx`コントロール。  
  
```  
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>パラメーター  
 *pCBItem*  
 ポインターを[受け取る](http://msdn.microsoft.com/library/windows/desktop/bb775746)項目の情報を受け取る構造体。 この構造体には、項目のコールバック フラグの値が含まれています。  
  
### <a name="return-value"></a>戻り値  
 挿入先である新しい項目が成功した場合のインデックスそれ以外の場合は-1。  
  
### <a name="remarks"></a>Remarks  
 呼び出すと`InsertItem`、 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)メッセージである[CBEN_INSERTITEM](http://msdn.microsoft.com/library/windows/desktop/bb775764)を親ウィンドウに通知が送信されます。  
  
##  <a name="setextendedstyle"></a>  CComboBoxEx::SetExtendedStyle  
 コンボ ボックス コントロールを拡張するため、拡張スタイルを設定するには、このメンバー関数を呼び出します。  
  
```  
DWORD SetExtendedStyle(
    DWORD dwExMask,  
    DWORD dwExStyles);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwExMask*  
 スタイルを示す DWORD 値*dwExStyles*が影響を受けます。 拡張スタイルのみ*dwExMask*変更されます。 その他のすべてのスタイルは、現状維持されます。 このパラメーターが 0 の場合、すべてのスタイルの場合*dwExStyles*を受けます。  
  
 *dwExStyles*  
 拡張コントロールに対して設定するスタイル コンボ ボックス コントロールを含む DWORD 値。  
  
### <a name="return-value"></a>戻り値  
 コントロールの使用されていた拡張スタイルを含む DWORD 値を指定します。  
  
### <a name="remarks"></a>Remarks  
 参照してください[ComboBoxEx コントロールの拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775742)これらのスタイルの詳細については、Windows SDK に含まれています。  
  
 拡張ウィンドウ スタイルでコントロールを拡張コンボ ボックスを作成するには、使用[CreateEx](#createex)します。  
  
##  <a name="setimagelist"></a>  CComboBoxEx::SetImageList  
 イメージ リストの設定、`ComboBoxEx`コントロール。  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>パラメーター  
 *pImageList*  
 ポインターを`CImageList`オブジェクトで使用するイメージを含む、`CComboBoxEx`コントロール。  
  
### <a name="return-value"></a>戻り値  
 ポインターを[CImageList](../../mfc/reference/cimagelist-class.md)で以前に使用されるイメージを格納しているオブジェクト、`CComboBoxEx`コントロール。 以前にイメージの一覧が設定されていない場合は NULL です。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、メッセージの機能を実装[CBEM_SETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775787)」の説明に従って、Windows SDK。 既定の編集コントロールの高さを変更する場合は、Win32 関数を呼び出す[SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545)を呼び出した後、コントロールのサイズを変更する`SetImageList`、正しく表示されるか。  
  
 `CImageList`戻り値によってポイントされるオブジェクトは一時オブジェクトし、[次へ] のアイドル状態の処理時に破棄します。  
  
##  <a name="setitem"></a>  CComboBoxEx::SetItem  
 内の項目の属性を設定、`ComboBoxEx`コントロール。  
  
```  
BOOL SetItem(const COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>パラメーター  
 *pCBItem*  
 ポインターを[受け取る](http://msdn.microsoft.com/library/windows/desktop/bb775746)項目の情報を受け取る構造体。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合、0 以外の場合それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、メッセージの機能を実装[CBEM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb775788)」の説明に従って、Windows SDK。  
  
##  <a name="setwindowtheme"></a>  CComboBoxEx::SetWindowTheme  
 Visual スタイル拡張コンボ ボックス コントロールを設定します。  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>パラメーター  
 *pszSubAppName*  
 拡張コンボ ボックスの visual スタイルを設定を含む Unicode 文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 戻り値は使用されません。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数の機能をエミュレートする、 [CBEM_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb775790)メッセージ、Windows SDK で説明されているとします。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MFCIE](../../visual-cpp-samples.md)   
 [CComboBox クラス](../../mfc/reference/ccombobox-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CComboBox クラス](../../mfc/reference/ccombobox-class.md)
