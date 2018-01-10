---
title: "入力したコネクション クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl
- ATLCOM/ATL::IConnectionPointContainerImpl::EnumConnectionPoints
- ATLCOM/ATL::IConnectionPointContainerImpl::FindConnectionPoint
dev_langs: C++
helpviewer_keywords:
- connectable objects
- connection points [C++], container
- IConnectionPointContainerImpl class
ms.assetid: 10db5a8d-8be9-4d9d-8a82-8ab9ffe3e9d6
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9f5e3a6ee6790c4fa0e93fe312d6a6b840b754a4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="iconnectionpointcontainerimpl-class"></a>入力したコネクション クラス
このクラスは実装のコレクションを管理するための接続ポイント コンテナー [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class ATL_NO_VTABLE IConnectionPointContainerImpl 
   : public IConnectionPointContainer
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`IConnectionPointContainerImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IConnectionPointContainerImpl::EnumConnectionPoints](#enumconnectionpoints)|接続可能なオブジェクトでサポートされている接続ポイントを反復処理する列挙子を作成します。|  
|[IConnectionPointContainerImpl::FindConnectionPoint](#findconnectionpoint)|指定の IID をサポートする接続ポイントへのインターフェイス ポインターを取得します。|  
  
## <a name="remarks"></a>コメント  
 `IConnectionPointContainerImpl`コレクションを管理するための接続ポイント コンテナーを実装する[IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)オブジェクト。 `IConnectionPointContainerImpl`詳細については、接続可能なオブジェクトを取得するクライアントが呼び出すことができる 2 つの方法があります。  
  
- `EnumConnectionPoints`クライアントは、オブジェクトでサポートされる出力方向のどのインターフェイスを決定できます。  
  
- `FindConnectionPoint`クライアントは、オブジェクトが特定の発信インターフェイスをサポートしているかどうかを決定できます。  
  
 ATL での接続ポイントの使用方法の詳細については、記事を参照してください。[コネクション ポイント](../../atl/atl-connection-points.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IConnectionPointContainer`  
  
 `IConnectionPointContainerImpl`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcom.h  
  
##  <a name="enumconnectionpoints"></a>IConnectionPointContainerImpl::EnumConnectionPoints  
 接続可能なオブジェクトでサポートされている接続ポイントを反復処理する列挙子を作成します。  
  
```
STDMETHOD(EnumConnectionPoints)(IEnumConnectionPoints** ppEnum);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IConnectionPointContainer::EnumConnectionPoints](http://msdn.microsoft.com/library/windows/desktop/ms682460) Windows SDK にします。  
  
##  <a name="findconnectionpoint"></a>IConnectionPointContainerImpl::FindConnectionPoint  
 指定の IID をサポートする接続ポイントへのインターフェイス ポインターを取得します。  
  
```
STDMETHOD(FindConnectionPoint)(REFIID riid, IConnectionPoint** ppCP);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IConnectionPointContainer::FindConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms692476) Windows SDK にします。  
  
## <a name="see-also"></a>参照  
 [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)   
 [クラスの概要](../../atl/atl-class-overview.md)
