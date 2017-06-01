---
title: "CMFCAutoHideBar クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AddAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AllowShowOnPaneMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CalcFixedLayout
- AFXAUTOHIDEBAR/CMFCAutoHideBar::Create
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetFirstAHWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetVisibleCount
- AFXAUTOHIDEBAR/CMFCAutoHideBar::OnShowControlBarMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::RemoveAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetActiveInGroup
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetRecentVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::ShowAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::StretchPane
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UnSetAutoHideMode
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UpdateVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::m_nShowAHWndDelay
dev_langs:
- C++
helpviewer_keywords:
- CMFCAutoHideToolBar class
ms.assetid: 54c8d84f-de64-4efd-8a47-3ea0ade40a70
caps.latest.revision: 35
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
ms.openlocfilehash: db15fc9fa3925230e372b6e13368f455dcfbb1a9
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcautohidebar-class"></a>CMFCAutoHideBar クラス
`CMFCAutoHideBar` クラスは、自動非表示機能を実装している、特殊なツール バー クラスです。  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]    
## <a name="syntax"></a>構文  
  
```  
class CMFCAutoHideBar : public CPane  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCAutoHideBar::CMFCAutoHideBar](#cmfcautohidebar)||  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCAutoHideBar::AddAutoHideWindow](#addautohidewindow)||  
|[CMFCAutoHideBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(`CPane::AllowShowOnPaneMenu` をオーバーライドします)。|  
|[CMFCAutoHideBar::CalcFixedLayout](#calcfixedlayout)|(上書き[CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout))。|  
|[CMFCAutoHideBar::Create](#create)|コントロール バーを作成し、それをアタッチ、 [CPane](../../mfc/reference/cpane-class.md)オブジェクトです。 (上書き[CPane::Create](../../mfc/reference/cpane-class.md#create))。|  
|[CMFCAutoHideBar::GetFirstAHWindow](#getfirstahwindow)||  
|[CMFCAutoHideBar::GetVisibleCount](#getvisiblecount)||  
|[CMFCAutoHideBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|特殊ウィンドウ メニューが表示されるときにフレームワークによって呼び出されます。 (上書き[CPane::OnShowControlBarMenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu))。|  
|[CMFCAutoHideBar::RemoveAutoHideWindow](#removeautohidewindow)||  
|[CMFCAutoHideBar::SetActiveInGroup](#setactiveingroup)|(上書き[CPane::SetActiveInGroup](../../mfc/reference/cpane-class.md#setactiveingroup))。|  
|[CMFCAutoHideBar::SetRecentVisibleState](#setrecentvisiblestate)||  
|[CMFCAutoHideBar::ShowAutoHideWindow](#showautohidewindow)||  
|[CMFCAutoHideBar::StretchPane](#stretchpane)|垂直または水平方向にウィンドウを拡大します。 (上書き[CBasePane::StretchPane](../../mfc/reference/cbasepane-class.md#stretchpane))。|  
|[CMFCAutoHideBar::UnSetAutoHideMode](#unsetautohidemode)||  
|[CMFCAutoHideBar::UpdateVisibleState](#updatevisiblestate)||  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCAutoHideBar::m_nShowAHWndDelay](#m_nshowahwnddelay)|ユーザーが上にマウス カーソルを置いたときに、その時点までの時間、 [CMFCAutoHideButton クラス](../../mfc/reference/cmfcautohidebutton-class.md)から、フレームワークが関連付けられているウィンドウを示しています。|  
  
## <a name="remarks"></a>コメント  
 ユーザーがドック ウィンドウを自動非表示モードに切り替えると、フレームワークは自動的に `CMFCAutoHideBar` オブジェクトを作成します。 また、必要に応じて、作成[CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md)と[CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md)オブジェクトです。 各 `CAutoHideDockSite` オブジェクトは、個別の `CMFCAutoHideButton` に関連付けられます。  
  
 `CMFCAutoHideBar` クラスは、ユーザーのマウスが `CMFCAutoHideButton` の上に移動したときの `CAutoHideDockSite` の表示を実装しています。 ツール バーが WM_MOUSEMOVE メッセージを受信すると、`CMFCAutoHideBar` がタイマーを開始します。 タイマーが終了したら、ツール バーに WM_TIMER イベント通知を送信します。 ツール バーは、タイマーが開始したときにマウス ポインターが位置していた自動非表示ボタン上にまだマウス ポインターがあるかどうかをチェックして、このイベントを処理します。 ある場合は、アタッチされている `CAutoHideDockSite` が表示されます。  
  
 タイマーの遅延の長さを制御するには、`m_nShowAHWndDelay` を設定します。 既定値は 400 ミリ秒です。  
  
## <a name="example"></a>例  
 `CMFCAutoHideBar` オブジェクトを構築して、その `GetDockSiteRow` メソッドを使用する方法を、次の例に示します。  
  
 [!code-cpp[NVC_MFC_RibbonApp #&26;](../../mfc/reference/codesnippet/cpp/cmfcautohidebar-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxautohidebar.h  
  
##  <a name="addautohidewindow"></a>CMFCAutoHideBar::AddAutoHideWindow  
 自動的に隠す機能を `CDockablePane` ウィンドウに追加します。  
  
```  
CMFCAutoHideButton* AddAutoHideWindow(
    CDockablePane* pAutoHideWnd,  
    DWORD dwAlignment);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pAutoHideWnd`  
 隠すウィンドウ。  
  
 [入力] `dwAlignment`  
 アプリケーション ウィンドウを使用して [自動的に隠す] ボタンの配置を指定する値。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 `dwAlignment` パラメーターは、[自動的に隠す] ボタンのアプリケーション内の位置を示します。 このパラメーターは次のいずれかの値に設定できます。  
  
- `CBRS_ALIGN_LEFT`  
  
- `CBRS_ALIGN_RIGHT`  
  
- `CBRS_ALIGN_TOP`  
  
- `CBRS_ALIGN_BOTTOM`  
  
##  <a name="allowshowonpanemenu"></a>CMFCAutoHideBar::AllowShowOnPaneMenu  

  
```  
virtual BOOL AllowShowOnPaneMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="calcfixedlayout"></a>CMFCAutoHideBar::CalcFixedLayout  

  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bStretch`  
 [入力] `bHorz`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="cmfcautohidebar"></a>CMFCAutoHideBar::CMFCAutoHideBar  
 CMFCAutoHideBar オブジェクトを構築します。  
  
```  
CMFCAutoHideBar();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="create"></a>CMFCAutoHideBar::Create  

  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    DWORD dwControlBarStyle = AFX_DEFAULT_PANE_STYLE,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszClassName`  
 [入力] `dwStyle`  
 [入力] `rect`  
 [入力] `pParentWnd`  
 [入力] `nID`  
 [入力] `dwControlBarStyle`  
 [入力] `pContext`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getfirstahwindow"></a>CMFCAutoHideBar::GetFirstAHWindow  
 アプリケーションの最初の自動非表示ウィンドウへのポインターを返します。  
  
```  
CDockablePane* GetFirstAHWindow();
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーションの最初の自動非表示ウィンドウ、または NULL (ウィンドウがない場合)。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getvisiblecount"></a>CMFCAutoHideBar::GetVisibleCount  
 自動的に隠すボタンのうち、表示されているものの数を取得します。  
  
```  
int GetVisibleCount();
```  
  
### <a name="return-value"></a>戻り値  
 自動的に隠すボタンのうち、表示されているものの数を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="m_nshowahwnddelay"></a>CMFCAutoHideBar::m_nShowAHWndDelay  
 ユーザーが上にマウス カーソルを置いたときに、その時点までの時間、 [CMFCAutoHideButton クラス](../../mfc/reference/cmfcautohidebutton-class.md)から、フレームワークが関連付けられているウィンドウを示しています。  
  
```  
int CMFCAutoHideBar::m_nShowAHWndDelay = 400;  
```  
  
### <a name="remarks"></a>コメント  
 ユーザーが上にマウス カーソルを置いたときに、`CMFCAutoHideButton`フレームワークは、関連するウィンドウを表示する前にわずかな遅延があります。 このパラメーターは、その待機時間をミリ秒単位の長さを指定します。  
  
##  <a name="onshowcontrolbarmenu"></a>CMFCAutoHideBar::OnShowControlBarMenu  

  
```  
virtual BOOL OnShowControlBarMenu(CPoint);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `CPoint`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="removeautohidewindow"></a>CMFCAutoHideBar::RemoveAutoHideWindow  
 自動的に隠すウィンドウを削除して破棄します。  
  
```  
    BOOL RemoveAutoHideWindow(CDockablePane* pAutoHideWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 CDockablePane *`pAutoHideWnd`  
 削除する自動的に隠すウィンドウ。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は TRUE、それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setactiveingroup"></a>CMFCAutoHideBar::SetActiveInGroup  
 自動的に隠すバーにアクティブというフラグを付けます。  
  
```  
virtual void SetActiveInGroup(BOOL bActive);  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]BOOL`bActive`  
 アクティブに設定する場合は TRUE、それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 参照してください[CPane::SetActiveInGroup](../../mfc/reference/cpane-class.md#setactiveingroup)します。  
  
##  <a name="setrecentvisiblestate"></a>CMFCAutoHideBar::SetRecentVisibleState  

  
```  
void SetRecentVisibleState(BOOL bState);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bState`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="showautohidewindow"></a>CMFCAutoHideBar::ShowAutoHideWindow  
 自動的に隠すウィンドウを示します。  
  
```  
BOOL ShowAutoHideWindow(
        CDockablePane* pAutoHideWnd,  
        BOOL bShow,  
        BOOL bDelay);  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]CDockablePane *`pAutoHideWnd`  
 [in]BOOL`bShow`  
 ウィンドウを表示する場合は TRUE。  
  
 [in]BOOL`bDelay`  
 このパラメーターは無視されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は TRUE、それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="stretchpane"></a>CMFCAutoHideBar::StretchPane  
 折りたたまれた状態の自動的に隠すバーを `CMFCAutoHideButton` オブジェクトに合わせてサイズ変更します。  
  
```  
virtual CSize StretchPane(
    int nLength,   
    BOOL bVert);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nLength`  
 この値は、基本実装では使用されません。 派生実装では、サイズを変更するウィンドウの長さを指定するためにこの値を使用します。  
  
 [入力] `bVert`  
 この値は、基本実装では使用されません。 派生実装で使用して`TRUE`バーの自動非表示が縦方向に折りたたまれている、ケースを処理して`FALSE`場合に、自動非表示バーが水平方向に折りたたまれて、します。  
  
### <a name="return-value"></a>戻り値  
 サイズを変更するウィンドウの結果のサイズ。  
  
### <a name="remarks"></a>コメント  
 派生クラスは、このメソッドをオーバーライドして動作をカスタマイズできます。  
  
##  <a name="unsetautohidemode"></a>CMFCAutoHideBar::UnSetAutoHideMode  
 自動的に隠すバーのグループの自動非表示モードを無効にします。  
  
```  
void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup)  
```  
  
### <a name="parameters"></a>パラメーター  
 [in] pFirstBarInGroup  
 グループ内で最初の自動的に隠すバーを指すポインター。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="updatevisiblestate"></a>CMFCAutoHideBar::UpdateVisibleState  
 自動的に隠すバーを再描画する必要がある場合に、フレームワークによって呼び出されます。  
  
```  
void UpdateVisibleState();
```  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CPane クラス](../../mfc/reference/cpane-class.md)   
 [CAutoHideDockSite クラス](../../mfc/reference/cautohidedocksite-class.md)   
 [CMFCAutoHideButton クラス](../../mfc/reference/cmfcautohidebutton-class.md)

