---
title: "CAnimationTimerEventHandler クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnPostUpdate
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnPreUpdate
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnRenderingTooSlow
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::SetAnimationController
dev_langs:
- C++
helpviewer_keywords:
- CAnimationTimerEventHandler [MFC], CreateInstance
- CAnimationTimerEventHandler [MFC], OnPostUpdate
- CAnimationTimerEventHandler [MFC], OnPreUpdate
- CAnimationTimerEventHandler [MFC], OnRenderingTooSlow
- CAnimationTimerEventHandler [MFC], SetAnimationController
ms.assetid: 188dea3b-4b5e-4f6b-8df9-09d993a21619
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: dc2dd4ddc96ab589d88b34d3d31fb131ab49fbc2
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="canimationtimereventhandler-class"></a>CAnimationTimerEventHandler クラス
タイミング イベントの発生時に Animation API によって呼び出されるコールバックを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CAnimationTimerEventHandler : public CUIAnimationTimerEventHandlerBase<CAnimationTimerEventHandler>;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationTimerEventHandler::CreateInstance](#createinstance)|インスタンスを作成`CAnimationTimerEventHandler`コールバック。|  
|[CAnimationTimerEventHandler::OnPostUpdate](#onpostupdate)|アニメーションの更新プログラムの完了後に発生するイベントを処理します。 (`CUIAnimationTimerEventHandlerBase::OnPostUpdate` をオーバーライドします)。|  
|[CAnimationTimerEventHandler::OnPreUpdate](#onpreupdate)|アニメーションの更新プログラムの開始前に発生するイベントを処理します。 (`CUIAnimationTimerEventHandlerBase::OnPreUpdate` をオーバーライドします)。|  
|[CAnimationTimerEventHandler::OnRenderingTooSlow](#onrenderingtooslow)|アニメーションのレンダリングのフレーム レートが、最低限の適切なフレーム レートを下回った場合に発生するイベントを処理します。 (`CUIAnimationTimerEventHandlerBase::OnRenderingTooSlow` をオーバーライドします)。|  
|[CAnimationTimerEventHandler::SetAnimationController](#setanimationcontroller)|イベントをルーティングする、アニメーション コント ローラーへのポインターを格納します。|  
  
## <a name="remarks"></a>コメント  
 このイベント ハンドラーが作成され、CAnimationController::EnableAnimationTimerEventHandler を呼び出すときに、IUIAnimationTimer::SetTimerEventHandler に渡されます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationTimerEventHandlerBase`  
  
 `CAnimationTimerEventHandler`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="createinstance"></a>CAnimationTimerEventHandler::CreateInstance  
 CAnimationTimerEventHandler コールバックのインスタンスを作成します。  
  
```  
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,  
    IUIAnimationTimerEventHandler** ppTimerEventHandler);
```  
  
### <a name="parameters"></a>パラメーター  
 `pAnimationController`  
 イベントを受信するアニメーション コント ローラーへのポインター。  
  
 `ppTimerEventHandler`  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
##  <a name="onpostupdate"></a>CAnimationTimerEventHandler::OnPostUpdate  
 アニメーションの更新プログラムの完了後に発生するイベントを処理します。  
  
```  
IFACEMETHOD(OnPostUpdate)();
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK、それ以外の場合 E_FAIL です。  
  
##  <a name="onpreupdate"></a>CAnimationTimerEventHandler::OnPreUpdate  
 アニメーションの更新プログラムの開始前に発生するイベントを処理します。  
  
```  
IFACEMETHOD(OnPreUpdate)();
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK、それ以外の場合 E_FAIL です。  
  
##  <a name="onrenderingtooslow"></a>CAnimationTimerEventHandler::OnRenderingTooSlow  
 アニメーションのレンダリングのフレーム レートが、最低限の適切なフレーム レートを下回った場合に発生するイベントを処理します。  
  
```  
IFACEMETHOD(OnRenderingTooSlow)(UINT32 fps);
```  
  
### <a name="parameters"></a>パラメーター  
 `fps`  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK、それ以外の場合 E_FAIL です。  
  
##  <a name="setanimationcontroller"></a>CAnimationTimerEventHandler::SetAnimationController  
 イベントをルーティングする、アニメーション コント ローラーへのポインターを格納します。  
  
```  
void SetAnimationController(CAnimationController* pAnimationController);
```  
  
### <a name="parameters"></a>パラメーター  
 `pAnimationController`  
 イベントを受信するアニメーション コント ローラーへのポインター。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

