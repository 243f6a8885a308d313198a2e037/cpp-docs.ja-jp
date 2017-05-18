---
title: "CHotKeyCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHotKeyCtrl
- AFXCMN/CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::Create
- AFXCMN/CHotKeyCtrl::CreateEx
- AFXCMN/CHotKeyCtrl::GetHotKey
- AFXCMN/CHotKeyCtrl::GetHotKeyName
- AFXCMN/CHotKeyCtrl::GetKeyName
- AFXCMN/CHotKeyCtrl::SetHotKey
- AFXCMN/CHotKeyCtrl::SetRules
dev_langs:
- C++
helpviewer_keywords:
- hot key controls
- CHotKeyCtrl class
- Windows common controls [C++], CHotKeyCtrl
ms.assetid: 896f9766-0718-4f58-aab2-20325e118ca6
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: cbcc720d2b934cde9f8beb9bb95499d9cc569413
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="chotkeyctrl-class"></a>CHotKeyCtrl クラス
Windows コモン ホット キー コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CHotKeyCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CHotKeyCtrl::CHotKeyCtrl](#chotkeyctrl)|`CHotKeyCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CHotKeyCtrl::Create](#create)|ホット キー コントロールを作成し、それをアタッチ、`CHotKeyCtrl`オブジェクトです。|  
|[CHotKeyCtrl::CreateEx](#createex)|指定した Windows 拡張スタイルを使用してホット キー コントロールを作成し、それにアタッチ、`CHotKeyCtrl`オブジェクトです。|  
|[CHotKeyCtrl::GetHotKey](#gethotkey)|ホット キー コントロールからホット キーの仮想キー コードと修飾子フラグを取得します。|  
|[CHotKeyCtrl::GetHotKeyName](#gethotkeyname)|ホット キーに割り当てられている、ローカル文字セット内のキー名を取得します。|  
|[CHotKeyCtrl::GetKeyName](#getkeyname)|キー名を指定した仮想キー コードに割り当てられている、ローカル文字セットを取得します。|  
|[CHotKeyCtrl::SetHotKey](#sethotkey)|ホット キー コントロールのホット キーの組み合わせを設定します。|  
|[CHotKeyCtrl::SetRules](#setrules)|無効な組み合わせとホット キー コントロールの既定の修飾子の組み合わせを定義します。|  
  
## <a name="remarks"></a>コメント  
 「ホット キー コントロール」は、ユーザーがホット キーを作成できるウィンドウです。 「ホット キー」は、アクションをすばやく実行するユーザーがキーを押してキーの組み合わせです。 (たとえば、ユーザー作成できますホット キーを Z オーダーの先頭に取り入れられ、特定のウィンドウがアクティブになります)。ホット キー コントロールは、ユーザーの選択項目を表示し、ユーザーが有効なキーの組み合わせを選択することを確認します。  
  
 このコントロール (つまり、`CHotKeyCtrl`クラス) は以降、Windows 95/98 および Windows NT version 3.51 で実行するプログラムにのみ使用できます。  
  
 ユーザーがキーの組み合わせを選択すると、ときに、アプリケーションがコントロールから、指定したキーの組み合わせを取得しを使用して、 **WM_SETHOTKEY**システムのホット キーを設定するメッセージ。 指定するウィンドウ押されたときに、ホット キー、その後、システムの任意の部分から、 **WM_SETHOTKEY**メッセージを受け取る、`WM_SYSCOMMAND`メッセージを指定する**SC_HOTKEY**します。 このメッセージには、それを受信するウィンドウがアクティブになります。 呼び出したアプリケーションまで、ホット キーが有効な**WM_SETHOTKEY**を終了します。  
  
 このメカニズムは、ホット キーのサポートに依存するいるとは異なる、 **WM_HOTKEY**メッセージと、Windows [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309)と[UnregisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646327)関数です。  
  
 使用する方法について`CHotKeyCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CHotKeyCtrl](../../mfc/using-chotkeyctrl.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHotKeyCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="chotkeyctrl"></a>CHotKeyCtrl::CHotKeyCtrl  
 `CHotKeyCtrl` オブジェクトを構築します。  
  
```  
CHotKeyCtrl();
```  
  
##  <a name="create"></a>CHotKeyCtrl::Create  
 ホット キー コントロールを作成し、それをアタッチ、`CHotKeyCtrl`オブジェクトです。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 ホット キー コントロールのスタイルを指定します。 コントロールのスタイルの任意の組み合わせを適用します。 参照してください[コモン コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775498)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細。  
  
 `rect`  
 ホット キー コントロールのサイズと位置を指定します。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT 構造体](../../mfc/reference/rect-structure1.md)します。  
  
 `pParentWnd`  
 通常、ホット キー コントロールの親ウィンドウを指定する[CDialog](../../mfc/reference/cdialog-class.md)します。 ことはできません**NULL**します。  
  
 `nID`  
 ホット キー コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 初期化が成功した場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 構築する、 `CHotKeyCtrl`&2; つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出すし、まず**作成**、ホット キー コントロールの作成し、それにアタッチ、`CHotKeyCtrl`オブジェクトです。  
  
 コントロールで拡張ウィンドウ スタイルを使用する場合は、呼び出す[CreateEx](#createex)の代わりに**作成**します。  
  
##  <a name="createex"></a>CHotKeyCtrl::CreateEx  
 コントロール (子ウィンドウ) を作成し、関連付けることは、この関数を呼び出して、`CHotKeyCtrl`オブジェクトです。  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwExStyle`  
 作成されるコントロールの拡張スタイルを指定します。 拡張ウィンドウ スタイルの一覧は、次を参照してください。、`dwExStyle`パラメーター [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `dwStyle`  
 ホット キー コントロールのスタイルを指定します。 コントロールのスタイルの任意の組み合わせを適用します。 詳細については、次を参照してください。[コモン コントロール スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775498)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `rect`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体のサイズとのクライアント座標で、作成するウィンドウの位置を表す`pParentWnd`します。  
  
 `pParentWnd`  
 コントロールの親ウィンドウへのポインター。  
  
 `nID`  
 コントロールの子ウィンドウの id。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用`CreateEx`の代わりに[作成](#create)、Windows 拡張スタイルの先頭で指定された、Windows の拡張スタイルを適用する**WS_EX**します。  
  
##  <a name="gethotkey"></a>CHotKeyCtrl::GetHotKey  
 ホット キー コントロールのキーボード ショートカットの仮想キー コードと修飾子フラグを取得します。  
  
```  
DWORD GetHotKey() const;  
  
void GetHotKey(
    WORD& wVirtualKeyCode,  
    WORD& wModifiers) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `wVirtualKeyCode`  
 キーボード ショートカットの仮想キー コード。 標準の仮想キー コードの一覧は、Winuser.h を参照してください。  
  
 [出力] `wModifiers`  
 キーボード ショートカット キーの修飾子キーを示すフラグのビットごとの組み合わせ (OR)。  
  
 修飾フラグは次のとおりです。  
  
|フラグ|対応するキー|  
|----------|-----------------------|  
|`HOTKEYF_ALT`|ALT キー|  
|`HOTKEYF_CONTROL`|CTRL キー|  
|`HOTKEYF_EXT`|拡張キー|  
|`HOTKEYF_SHIFT`|Shift キー|  
  
### <a name="return-value"></a>戻り値  
 最初のメソッドをオーバー ロード、`DWORD`仮想キー コードと修飾子のフラグを格納しています。 下位ワードの下位バイトが仮想キー コードを含む、下位ワードの高位バイトには、修飾フラグが含まれています。 および上位ワードにはゼロです。  
  
### <a name="remarks"></a>コメント  
 仮想キー コードと修飾子キーを同時に、キーボード ショートカットを定義します。  
  
##  <a name="gethotkeyname"></a>CHotKeyCtrl::GetHotKeyName  
 ホット キーのローカライズされた名前を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetHotKeyName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在選択されているホット キーのローカライズされた名前。 選択したホット キーが存在しない場合`GetHotKeyName`空の文字列を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数が返す名前キーボード ドライバーに由来します。 キーボードのローカライズされていないドライバーをインストールするにはローカライズされたバージョンの Windows、およびその逆です。  
  
##  <a name="getkeyname"></a>CHotKeyCtrl::GetKeyName  
 指定した仮想キー コードに割り当てられているキーのローカライズされた名前を取得するには、このメンバー関数を呼び出します。  
  
```  
static CString GetKeyName(
    UINT vk,  
    BOOL fExtended);
```  
  
### <a name="parameters"></a>パラメーター  
 `vk`  
 仮想キー コード。  
  
 *fExtended*  
 仮想キー コードが、拡張キー場合**TRUE**以外の場合**FALSE**します。  
  
### <a name="return-value"></a>戻り値  
 指定されたキーのローカライズされた名前、`vk`パラメーター。 キーがマップされた名前を持たない場合`GetKeyName`空の文字列を返します。  
  
### <a name="remarks"></a>コメント  
 ローカライズされたバージョンの Windows でローカライズされていないキーボード ドライバーをインストールするために、この関数が返すキーの名前がキーボード ドライバーから得またはその逆です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog #&69;](../../mfc/codesnippet/cpp/chotkeyctrl-class_1.cpp)]  
  
##  <a name="sethotkey"></a>CHotKeyCtrl::SetHotKey  
 ホット キー コントロールのキーボード ショートカットを設定します。  
  
```  
void SetHotKey(
    WORD wVirtualKeyCode,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `wVirtualKeyCode`  
 キーボード ショートカットの仮想キー コード。 標準の仮想キー コードの一覧は、Winuser.h を参照してください。  
  
 [入力] `wModifiers`  
 キーボード ショートカット キーの修飾子キーを示すフラグのビットごとの組み合わせ (OR)。  
  
 修飾フラグは次のとおりです。  
  
|フラグ|対応するキー|  
|----------|-----------------------|  
|`HOTKEYF_ALT`|ALT キー|  
|`HOTKEYF_CONTROL`|CTRL キー|  
|`HOTKEYF_EXT`|拡張キー|  
|`HOTKEYF_SHIFT`|Shift キー|  
  
### <a name="remarks"></a>コメント  
 仮想キー コードと修飾子キーを同時に、キーボード ショートカットを定義します。  
  
##  <a name="setrules"></a>CHotKeyCtrl::SetRules  
 無効な組み合わせとホット キー コントロールの既定の修飾子の組み合わせを定義するには、この関数を呼び出します。  
  
```  
void SetRules(
    WORD wInvalidComb,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>パラメーター  
 `wInvalidComb`  
 無効なキーの組み合わせを指定するフラグの配列。 次の値の組み合わせを指定できます。  
  
- `HKCOMB_A`ALT キー  
  
- `HKCOMB_C`CTRL キーを  
  
- `HKCOMB_CA`CTRL + ALT +  
  
- `HKCOMB_NONE`変更されていないキー  
  
- `HKCOMB_S`SHIFT キー  
  
- `HKCOMB_SA`SHIFT キーを押しながら ALT キー  
  
- `HKCOMB_SC`CTRL + SHIFT キー  
  
- `HKCOMB_SCA`CTRL + ALT + SHIFT +  
  
 `wModifiers`  
 ユーザーが無効な組み合わせを入力するときに使用するキーの組み合わせを指定するフラグの配列。 修飾フラグの詳細については、次を参照してください。 [GetHotKey](#gethotkey)します。  
  
### <a name="remarks"></a>コメント  
 ユーザーが無効なキーの組み合わせに入ったときに指定されたフラグによって定義された`wInvalidComb`、システムでは、OR 演算子を使用して、指定したフラグと、ユーザーが入力したキーの組み合わせ`wModifiers`します。 結果として得られるキーの組み合わせは文字列に変換され、ホット キー コントロールに表示されます。  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)




