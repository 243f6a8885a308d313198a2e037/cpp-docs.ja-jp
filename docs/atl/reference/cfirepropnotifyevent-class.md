---
title: "CFirePropNotifyEvent クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnChanged
- ATLCTL/ATL::CFirePropNotifyEvent::FireOnRequestEdit
dev_langs:
- C++
helpviewer_keywords:
- sinks, notifying of ATL events
- CFirePropNotifyEvent class
- connection points [C++], notifying of events
ms.assetid: eb7a563e-6bce-4cdf-8d20-8c6a5307781b
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 1511a9e9ba287d12aade7c393887c6b5f8880b96
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cfirepropnotifyevent-class"></a>CFirePropNotifyEvent クラス
このクラスは、コントロール プロパティの変更についてコンテナーのシンクに通知するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CFirePropNotifyEvent
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFirePropNotifyEvent::FireOnChanged](#fireonchanged)|(静的)コントロールのプロパティが変更されたコンテナーのシンクに通知します。|  
|[CFirePropNotifyEvent::FireOnRequestEdit](#fireonrequestedit)|(静的)コントロールのプロパティが変更しようとは、コンテナーのシンクに通知します。|  
  
## <a name="remarks"></a>コメント  
 `CFirePropNotifyEvent`コントロールのプロパティが変更されたかを変更するには、コンテナーのシンクに通知する&2; つのメソッドがあります。  
  
 場合は、制御を実装するクラスから派生`IPropertyNotifySink`、`CFirePropNotifyEvent`メソッドを呼び出すときに呼び出す`FireOnRequestEdit`または`FireOnChanged`です。 コントロール クラスを派生していない場合`IPropertyNotifySink`、これらの関数の呼び出しを返す`S_OK`します。  
  
 コントロールの作成方法の詳細については、次を参照してください。、 [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="fireonchanged"></a>CFirePropNotifyEvent::FireOnChanged  
 通知すべて接続されている[IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)インターフェイス (オブジェクトのすべての接続ポイント) 上に、指定したオブジェクトのプロパティが変更されたことです。  
  
```
static HRESULT FireOnChanged(IUnknown* pUnk, DISPID dispID);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 [in]ポインター、 **IUnknown**の通知を送信するオブジェクト。  
  
 *dispID*  
 [in]変更されたプロパティの識別子。  
  
### <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
### <a name="remarks"></a>コメント  
 この関数は、コントロールはコネクション ポイントをサポートしていない場合でもを呼び出しても安全です。  
  
##  <a name="fireonrequestedit"></a>CFirePropNotifyEvent::FireOnRequestEdit  
 通知すべて接続されている[IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)指定したオブジェクトのプロパティが変更されようとしています (オブジェクトのコネクション ポイントがすべて) 上のインターフェイスです。  
  
```
static HRESULT FireOnRequestEdit(IUnknown* pUnk, DISPID dispID);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnk*  
 [in]ポインター、 **IUnknown**の通知を送信するオブジェクト。  
  
 *dispID*  
 [in]変更するプロパティの識別子。  
  
### <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
### <a name="remarks"></a>コメント  
 この関数は、コントロールはコネクション ポイントをサポートしていない場合でもを呼び出しても安全です。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
