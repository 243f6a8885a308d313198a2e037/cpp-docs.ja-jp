---
title: "CBitmapButton クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBitmapButton
- AFXEXT/CBitmapButton
- AFXEXT/CBitmapButton::CBitmapButton
- AFXEXT/CBitmapButton::AutoLoad
- AFXEXT/CBitmapButton::LoadBitmaps
- AFXEXT/CBitmapButton::SizeToContent
dev_langs: C++
helpviewer_keywords:
- CBitmapButton [MFC], CBitmapButton
- CBitmapButton [MFC], AutoLoad
- CBitmapButton [MFC], LoadBitmaps
- CBitmapButton [MFC], SizeToContent
ms.assetid: 9ad6cb45-c3c4-4fb1-96d3-1fe3df7bbcfc
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d926e538cf9f9f1cb4935a1d53ba6c1fd7f4696e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cbitmapbutton-class"></a>CBitmapButton クラス
ラベルがテキストではなくビットマップ イメージのプッシュ ボタン コントロールを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
class CBitmapButton : public CButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CBitmapButton::CBitmapButton](#cbitmapbutton)|`CBitmapButton` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CBitmapButton::AutoLoad](#autoload)|ダイアログ ボックスのボタンのオブジェクトに関連付け、`CBitmapButton`クラス、名前で、ビットマップをロードおよびビットマップに合わせてボタンのサイズを設定します。|  
|[CBitmapButton::LoadBitmaps](#loadbitmaps)|アプリケーションのリソース ファイルからの 1 つまたは複数の名前付きのビットマップ リソースの読み込みと、オブジェクトへのビットマップのアタッチによって、オブジェクトを初期化します。|  
|[CBitmapButton::SizeToContent](#sizetocontent)|ビットマップに合わせてボタンのサイズを設定します。|  
  
## <a name="remarks"></a>コメント  
 `CBitmapButton`オブジェクトに含める最大 4 つのビットマップは、ボタンのさまざまな状態の画像が含まれて: を (標準)、下 (または選択した)、中心し、無効になっています。 最初のビットマップのみが必要です。その他はオプションです。  
  
 ビットマップ ボタンのイメージには、そのイメージ自体と同様に、画像の周りの境界線が含まれます。 罫線は、通常、ボタンの状態の表示中に役割を果たします。 たとえば、フォーカスのある状態のビットマップと同様に、1 つの状態が、罫線または境界の実線シック (thick) から四角形の破線埋め込み通常です。 ビットマップ、無効な状態を通常のと似ていますが (淡色表示のメニュー選択) のようなコントラストがはっきりして最新の状態にします。  
  
 任意のサイズのこれらのビットマップを指定できますが、それらの状態を表すビットマップと同じサイズの場合と同様に扱われますすべて。  
  
 さまざまなアプリケーションでは、ビットマップ イメージのさまざまな組み合わせを要求します。  
  
|上へ|[下へ移動]|Focused|無効|アプリケーション|  
|--------|----------|-------------|--------------|-----------------|  
|×||||ビットマップ|  
|×|×|||ボタンをクリックしてせず**WS_TABSTOP**スタイル|  
|×|×|×|×|すべての状態を持つダイアログ ボタン|  
|×|×|×||ダイアログ ボタン**WS_TABSTOP**スタイル|  
  
 ビットマップ ボタン コントロールを作成するときの設定、 **BS_OWNERDRAW**  ボタンがオーナー描画を指定するスタイルです。 これが原因で送信する Windows、`WM_MEASUREITEM`と`WM_DRAWITEM`; ボタンのメッセージ フレームワークは、これらのメッセージを処理しするボタンの外観を管理します。  
  
### <a name="to-create-a-bitmap-button-control-in-a-windows-client-area"></a>ウィンドウのクライアント領域内のビットマップ ボタン コントロールを作成するには  
  
1.  ボタンの 1 ~ 4 個のビットマップ イメージを作成します。  
  
2.  構築、 [CBitmapButton](#cbitmapbutton)オブジェクト。  
  
3.  呼び出す、[作成](../../mfc/reference/cbutton-class.md#create)Windows ボタン コントロールを作成しをアタッチする関数、`CBitmapButton`オブジェクト。  
  
4.  呼び出す、 [LoadBitmaps](#loadbitmaps)ビットマップ ボタンを構築した後に、ビットマップ リソースを読み込むメンバー関数。  
  
### <a name="to-include-a-bitmap-button-control-in-a-dialog-box"></a>ダイアログ ボックスにビットマップ ボタン コントロールを含める  
  
1.  ボタンの 1 ~ 4 個のビットマップ イメージを作成します。  
  
2.  ビットマップのボタンを配置オーナー描画ボタンでダイアログ テンプレートを作成します。 テンプレート内のボタンのサイズを指定することはありません。  
  
3.  などの値に、ボタンのキャプションを設定" **MYIMAGE**"など、ボタンの記号の定義と**IDC_MYIMAGE**です。  
  
4.  スクリプトでは、アプリケーションのリソースには、"X"(については、下、重点を置いて、および無効になっている) のボタンのキャプションに使用される文字列に手順 3 またはの各ボタンの文字"U"、"D"、"F"のいずれかの操作を追加することによって構築された ID を作成したイメージを与えます。 ボタンのキャプションを" **MYIMAGE**、"など、Id になります" **MYIMAGEU**、"" **MYIMAGED**、"" **MYIMAGEF**、"と" **手順 3**"。 **必要があります**二重引用符で囲まれた、ビットマップの ID を指定します。 それ以外の場合、リソース エディターは、リソースに整数を割り当て、イメージを読み込むときに、MFC は失敗します。  
  
5.  アプリケーションのダイアログ クラスで (から派生した`CDialog`)、追加、`CBitmapButton`メンバー オブジェクトです。  
  
6.  `CDialog`オブジェクトの[OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog)ルーチンを呼び出し、`CBitmapButton`オブジェクトの[AutoLoad](#autoload)関数は、ボタンのコントロール ID をパラメーターとして使用して、`CDialog`オブジェクト**この**ポインター。  
  
 など、Windows の通知メッセージを処理するかどうかは**BN_CLICKED**ビットマップ ボタン コントロールをその親によって送信された、(通常から派生したクラス**CDialog)**への追加、 `CDialog`-派生各メッセージのメッセージ マップ エントリとメッセージ ハンドラー メンバー関数をオブジェクトです。 送信された通知、`CBitmapButton`オブジェクトは、によって送信されたものと同じ、 [CButton](../../mfc/reference/cbutton-class.md)オブジェクト。  
  
 クラス[CToolBar](../../mfc/reference/ctoolbar-class.md)ビットマップ ボタンへのさまざまなアプローチです。  
  
 詳細については`CBitmapButton`を参照してください[コントロール](../../mfc/controls-mfc.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CBitmapButton`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxext.h  
  
##  <a name="autoload"></a>CBitmapButton::AutoLoad  
 ダイアログ ボックスのボタンのオブジェクトに関連付け、`CBitmapButton`クラス、名前で、ビットマップをロードおよびビットマップに合わせてボタンのサイズを設定します。  
  
```  
BOOL AutoLoad(
    UINT nID,  
    CWnd* pParent);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 ボタンのコントロールの id。  
  
 `pParent`  
 ボタンを所有するオブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用して、`AutoLoad`ビットマップ ボタンとして ダイアログ ボックスのオーナー描画ボタンを初期化します。 この関数を使用する手順については、「解説」で、`CBitmapButton`クラスです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog#75](../../mfc/codesnippet/cpp/cbitmapbutton-class_1.cpp)]  
  
##  <a name="cbitmapbutton"></a>CBitmapButton::CBitmapButton  
 
          `CBitmapButton` オブジェクトを作成します。  
  
```  
CBitmapButton();
```  
  
### <a name="remarks"></a>コメント  
 C++ の作成後`CBitmapButton`オブジェクトを呼び出す[CButton::Create](../../mfc/reference/cbutton-class.md#create) Windows ボタン コントロールを作成しをアタッチする、`CBitmapButton`オブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog#57](../../mfc/codesnippet/cpp/cbitmapbutton-class_2.cpp)]  
  
##  <a name="loadbitmaps"></a>CBitmapButton::LoadBitmaps  
 識別されたリソース名または ID 番号を使用できない場合にビットマップ イメージを読み込む場合は、この関数を使用して、 `AutoLoad` 、たとえば、ダイアログ ボックスの一部ではないビットマップ ボタンを作成するために機能します。  
  
```  
BOOL LoadBitmaps(
    LPCTSTR lpszBitmapResource,  
    LPCTSTR lpszBitmapResourceSel = NULL,  
    LPCTSTR lpszBitmapResourceFocus = NULL,  
    LPCTSTR lpszBitmapResourceDisabled = NULL);

 
BOOL LoadBitmaps(
    UINT nIDBitmapResource,  
    UINT nIDBitmapResourceSel = 0,  
    UINT nIDBitmapResourceFocus = 0,  
    UINT nIDBitmapResourceDisabled = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszBitmapResource*  
 または「の状態を」ビットマップ ボタンの通常のビットマップの名前を表す null で終わる文字列へのポインター。 必須。  
  
 *lpszBitmapResourceSel*  
 「停止」状態またはビットマップ ボタンの選択のためのビットマップの名前を表す null で終わる文字列へのポインター。 あります**NULL**です。  
  
 *lpszBitmapResourceFocus*  
 ビットマップのビットマップ ボタンの名前を表す null で終わる文字列へのポインターには、状態がフォーカスしています。 あります**NULL**です。  
  
 *lpszBitmapResourceDisabled*  
 ビットマップのビットマップ ボタンの名前を表す null で終わる文字列へのポインターには、状態が無効になります。 あります**NULL**です。  
  
 *nIDBitmapResource*  
 ビットマップ リソースのビットマップ ボタンの通常の状態「を」リソースの ID 番号を指定します。 必須。  
  
 *nIDBitmapResourceSel*  
 ビットマップ ボタンの選択のため、または「停止」状態は、ビットマップ リソースのリソースの ID 番号を指定します。 0 にすることがあります。  
  
 *nIDBitmapResourceFocus*  
 ビットマップ ボタンのフォーカスのある状態のビットマップ リソースのリソースの ID 番号を指定します。 0 にすることがあります。  
  
 *nIDBitmapResourceDisabled*  
 ビットマップ ボタンの無効な状態のビットマップ リソースのリソースの ID 番号を指定します。 0 にすることがあります。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog#58](../../mfc/codesnippet/cpp/cbitmapbutton-class_3.cpp)]  
  
##  <a name="sizetocontent"></a>CBitmapButton::SizeToContent  
 ビットマップのサイズをビットマップ ボタンのサイズを変更するには、この関数を呼び出します。  
  
```  
void SizeToContent();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog#59](../../mfc/codesnippet/cpp/cbitmapbutton-class_4.cpp)]  
  
## <a name="see-also"></a>参照  
 [MFC サンプル CTRLTEST](../../visual-cpp-samples.md)   
 [CButton クラス](../../mfc/reference/cbutton-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)

