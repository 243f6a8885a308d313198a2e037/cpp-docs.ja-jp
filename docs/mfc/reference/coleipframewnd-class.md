---
title: "COleIPFrameWnd クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleIPFrameWnd
- AFXOLE/COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::OnCreateControlBars
- AFXOLE/COleIPFrameWnd::RepositionFrame
dev_langs:
- C++
helpviewer_keywords:
- COleIPFrameWnd [MFC], COleIPFrameWnd
- COleIPFrameWnd [MFC], OnCreateControlBars
- COleIPFrameWnd [MFC], RepositionFrame
ms.assetid: 24abb2cb-826c-4dda-a287-d8a8900a5763
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f1833cbbbfb6706cffe73770bcd9b61ff755a645
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="coleipframewnd-class"></a>COleIPFrameWnd クラス
アプリケーションの埋め込み先編集ウィンドウの基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class COleIPFrameWnd : public CFrameWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleIPFrameWnd::COleIPFrameWnd](#coleipframewnd)|`COleIPFrameWnd` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleIPFrameWnd::OnCreateControlBars](#oncreatecontrolbars)|埋め込み先編集のため、アイテムがアクティブになったときに、フレームワークによって呼び出されます。|  
|[COleIPFrameWnd::RepositionFrame](#repositionframe)|埋め込み先編集ウィンドウの位置を変更するためにフレームワークによって呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 このクラスを作成し、コントロール コンテナー アプリケーションのドキュメント ウィンドウ内でバーの位置。 また、埋め込みで生成された通知を処理[COleResizeBar](../../mfc/reference/coleresizebar-class.md)ユーザー インプレース編集ウィンドウのサイズ変更されるとします。  
  
 使用する方法についての`COleIPFrameWnd`、記事を参照して[アクティブ化](../../mfc/activation-cpp.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `COleIPFrameWnd`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxole.h  
  
##  <a name="coleipframewnd"></a>COleIPFrameWnd::COleIPFrameWnd  
 構築、`COleIPFrameWnd`オブジェクトし、型の構造体に格納されているが、インプレース状態情報を初期化します**受け取る**です。  
  
```  
COleIPFrameWnd();
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[受け取る](http://msdn.microsoft.com/library/windows/desktop/ms693737)Windows SDK に含まれています。  
  
##  <a name="oncreatecontrolbars"></a>COleIPFrameWnd::OnCreateControlBars  
 フレームワークによって、`OnCreateControlBars`で埋め込み先編集の項目がアクティブになったときに機能します。  
  
```  
virtual BOOL OnCreateControlBars(
    CWnd* pWndFrame,  
    CWnd* pWndDoc);

 
virtual BOOL OnCreateControlBars(
    CFrameWnd* pWndFrame,  
    CFrameWnd* pWndDoc);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWndFrame*  
 コンテナー アプリケーションのフレーム ウィンドウへのポインター。  
  
 *pWndDoc*  
 コンテナーのドキュメント レベルのウィンドウへのポインター。 指定できます**NULL**コンテナーが SDI アプリケーションの場合。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外の値それ以外の場合、0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、何も行われません。 コントロール バーが作成されたときに必要な特別な処理を実行するには、この関数をオーバーライドします。  
  
##  <a name="repositionframe"></a>COleIPFrameWnd::RepositionFrame  
 フレームワークによって、`RepositionFrame`コントロール バー レイアウトし、そのすべてが表示されるよう、埋め込み先編集ウィンドウの位置を指定するメンバー関数。  
  
```  
virtual void RepositionFrame(
    LPCRECT lpPosRect,  
    LPCRECT lpClipRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPosRect`  
 ポインター、`RECT`構造体、または`CRect`オブジェクトを含む、その場でのフレーム ウィンドウの現在の位置座標をクライアント領域と相対的です。  
  
 `lpClipRect`  
 ポインター、`RECT`構造体、または`CRect`オブジェクトを含む、その場でフレーム ウィンドウの現在クリッピング四角形の座標を (クライアント領域と相対的のピクセル単位)。  
  
### <a name="remarks"></a>コメント  
 コンテナー ウィンドウのコントロール バーのレイアウトが異なる非 OLE フレーム ウィンドウで実行します。 非 OLE フレーム ウィンドウ、コントロール バーやその他のオブジェクトへの呼び出しと同様に、特定のフレーム ウィンドウのサイズからの位置を計算する[表示](../../mfc/reference/cframewnd-class.md#recalclayout)です。 クライアント領域は、残りのコントロール バーおよびその他のオブジェクト用の領域を減算します。 A`COleIPFrameWnd`ウィンドウは、特定のクライアント領域に従ってツールバーを配置する一方で、します。 つまり、`CFrameWnd::RecalcLayout`一方で、外部"から"動作`COleIPFrameWnd::RepositionFrame`"から、inside out 』 です"。  
  
## <a name="see-also"></a>参照  
 [MFC サンプル HIERSVR](../../visual-cpp-samples.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)
