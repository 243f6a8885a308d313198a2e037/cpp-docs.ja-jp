---
title: "CHeapPtrList クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList::CHeapPtrList
dev_langs:
- C++
helpviewer_keywords:
- CHeapPtrList class
ms.assetid: cc70e585-362a-4007-81db-c705eb181226
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bda8c44142425e93792648cbbf07f5dd5e0bdb47
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cheapptrlist-class"></a>CHeapPtrList クラス
このクラスは、ヒープのポインターのリストを構築するときに役立つメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<typename E, class Allocator = ATL::CCRTAllocator>  
class CHeapPtrList 
   : public CAtlList<ATL::CHeapPtr<E, Allocator>,
                     CHeapPtrElementTraits<E, Allocator>>
```  
  
#### <a name="parameters"></a>パラメーター  
 `E`  
 コレクション クラスに格納されるオブジェクトの型。  
  
 `Allocator`  
 メモリの割り当ては、使用するクラス。 既定値は[CCRTAllocator](../../atl/reference/ccrtallocator-class.md)です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CHeapPtrList::CHeapPtrList](#cheapptrlist)|コンストラクターです。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、コンス トラクターを提供し、メソッドからの派生[CAtlList](../../atl/reference/catllist-class.md)と[CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md)ヒープ ポインターを格納するコレクション クラスのオブジェクトの作成を支援するためにします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CHeapPtrList`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="cheapptrlist"></a>CHeapPtrList::CHeapPtrList  
 コンストラクターです。  
  
```
CHeapPtrList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nBlockSize`  
 ブロック サイズ。  
  
### <a name="remarks"></a>コメント  
 ブロック サイズは、新しい要素が必要な場合に割り当てられたメモリの量の測定です。 ブロック サイズを大きくはメモリ割り当てルーチンに呼び出しを減らすことより多くのリソースを使用します。  
  
## <a name="see-also"></a>参照  
 [CAtlList クラス](../../atl/reference/catllist-class.md)   
 [CHeapPtr クラス](../../atl/reference/cheapptr-class.md)   
 [CHeapPtrElementTraits クラス](../../atl/reference/cheapptrelementtraits-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
