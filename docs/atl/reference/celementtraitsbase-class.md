---
title: "CElementTraitsBase クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase::INARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::OUTARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::CopyElements
- ATLCOLL/ATL::CElementTraitsBase::RelocateElements
dev_langs:
- C++
helpviewer_keywords:
- CElementTraitsBase class
ms.assetid: 75284caf-347e-4355-a7d8-efc708dd514a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c9bbea69d2265563a0da4fda8b45cc09234a7789
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="celementtraitsbase-class"></a>CElementTraitsBase クラス
このクラスは、既定のコピーを提供し、コレクション クラスのメソッドを移動します。  
  
## <a name="syntax"></a>構文  
  
```
template<typename T>  
class CElementTraitsBase
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CElementTraitsBase::INARGTYPE](#inargtype)|コレクション クラスのオブジェクトに要素を追加するために使用するデータ型。|  
|[CElementTraitsBase::OUTARGTYPE](#outargtype)|コレクション クラスのオブジェクトから要素を取得するのに使用するデータ型。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CElementTraitsBase::CopyElements](#copyelements)|コレクション クラスのオブジェクトに格納されている要素をコピーするには、このメソッドを呼び出します。|  
|[CElementTraitsBase::RelocateElements](#relocateelements)|コレクション クラスのオブジェクトに格納されている要素を再配置するには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>コメント  
 この基本クラスでは、コピーおよびコレクション クラス内の要素を再配置するためのメソッドを定義します。 クラスによって使用されて、 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)、 [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md)、および[CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)です。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="copyelements"></a>CElementTraitsBase::CopyElements  
 コレクション クラスのオブジェクトに格納されている要素をコピーするには、このメソッドを呼び出します。  
  
```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDest`  
 コピーしたデータを受信する最初の要素へのポインター。  
  
 `pSrc`  
 コピーする最初の要素へのポインター。  
  
 `nElements`  
 コピーする要素の数。  
  
### <a name="remarks"></a>コメント  
 ソースと移行先の要素が重ならないようにします。  
  
##  <a name="inargtype"></a>CElementTraitsBase::INARGTYPE  
 コレクションに要素を追加するのに使用するデータ型。  
  
```
typedef const T& INARGTYPE;
```  
  
##  <a name="outargtype"></a>CElementTraitsBase::OUTARGTYPE  
 コレクションから要素を取得するのに使用するデータ型。  
  
```
typedef T& OUTARGTYPE;
```  
  
##  <a name="relocateelements"></a>CElementTraitsBase::RelocateElements  
 コレクション クラスのオブジェクトに格納されている要素を再配置するには、このメソッドを呼び出します。  
  
```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDest`  
 再配置されたデータを受信する最初の要素へのポインター。  
  
 `pSrc`  
 再配置する最初の要素へのポインター。  
  
 `nElements`  
 再配置する要素の数。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出す[memmove](../../c-runtime-library/reference/memmove-wmemmove.md)、これは、ほとんどのデータ型。 オブジェクトの移動中に、独自のメンバーへのポインターが含まれている場合は、このメソッドをオーバーライドする必要があります。  
  
## <a name="see-also"></a>参照  
 [クラスの概要](../../atl/atl-class-overview.md)
