---
title: "CSplitterWndEx クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx::OnDrawSplitter
dev_langs: C++
helpviewer_keywords: CSplitterWndEx [MFC], OnDrawSplitter
ms.assetid: 33e5eef3-05e1-4a07-a968-bf9207ce8598
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 94ec633718dda81a5183a59eb46387b361d0f004
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="csplitterwndex-class"></a>CSplitterWndEx クラス



カスタマイズされた分割ウィンドウを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CSplitterWndEx : public CSplitterWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CSplitterWndEx::CSplitterWndEx`|既定のコンストラクター|  
|`CSplitterWndEx::~CSplitterWndEx`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSplitterWndEx::OnDrawSplitter](#ondrawsplitter)|分割ウィンドウを描画するためにフレームワークによって呼び出されます。 (上書き[CSplitterWnd::OnDrawSplitter](csplitterwnd-class.md#ondrawsplitter))。|  
  
## <a name="remarks"></a>コメント  
 上書き、`OnDrawSplitter`分割ウィンドウのグラフィック要素の外観をカスタマイズする方法です。  
  
 `CSplitterWndEx`と共にクラスを使用する、 [OnDrawSplitterBorder](cmfcvisualmanager-class.md#ondrawsplitterborder)、 [OnDrawSplitterBox](cmfcvisualmanager-class.md#ondrawsplitterbox)、および[OnFillSplitterBackground](cmfcvisualmanager-class.md#onfillsplitterbackground)メソッドビジュアル マネージャーによって実装されます。 アプリケーションで分割ウィンドウを描画するビジュアル マネージャーの宣言を置き換える、`CSplitterWnd`クラス、`CSplitterWndEx`クラスです。 フレーム ウィンドウのアプリケーションでは、分割ウィンドウ クラスを mainfrm.h に配置されている CMainFrame クラスで宣言されます。 例については、次を参照してください。、`OutlookDemo`サンプル Samples ディレクトリにします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](cobject-class.md)  
  
 [CCmdTarget](ccmdtarget-class.md)  
  
 [CWnd](cwnd-class.md)  
  
 [CSplitterWnd](csplitterwnd-class.md)  
   
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxsplitterwndex.h  
  
##  <a name="ondrawsplitter"></a>CSplitterWndEx::OnDrawSplitter  
 分割ウィンドウを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDrawSplitter(  
   CDC* pDC,  
   ESplitType nType,  
   const CRect& rect   
);  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。 このパラメーターが場合`NULL`フレームワークには、アクティブなウィンドウが再描画します。  
  
 [入力] `nType`  
 1 つ、`CSplitterWnd::ESplitType`を描画する分割ウィンドウ要素を指定する列挙値。 有効な値は`splitBox`、 `splitBar`、 `splitIntersection`、および`splitBorder`です。  
  
 [入力] `rect`  
 ディメンションと、指定された分割ウィンドウ要素を描画する場所を指定する外接する四角形。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>参照  
 [階層図](../hierarchy-chart.md)   
 [クラス](mfc-classes.md)   
 [CSplitterWnd クラス](csplitterwnd-class.md)   
 [CMFCVisualManager クラス](cmfcvisualmanager-class.md)