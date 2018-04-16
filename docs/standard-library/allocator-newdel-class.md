---
title: "allocator_newdel クラス |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- allocators/stdext::allocators::allocator_newdel
- allocators/stdext::allocator_newdel
- stdext::allocators::allocator_newdel
dev_langs:
- C++
helpviewer_keywords:
- stdext::allocators [C++], allocator_newdel
- stdext::allocator_newdel
ms.assetid: 62666cd2-3afe-49f7-9dd1-9bbbb154da98
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dab9a7b0d6cf424dcc361b8cc28cab0bdb7992ef
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="allocatornewdel-class"></a>allocator_newdel クラス
`operator delete` を使用してメモリ ブロックの割り当てを解除し、`operator new` を使用してメモリ ブロックを割り当てるアロケーターを実装します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Type>  
class allocator_newdel;
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`Type`|アロケーターによって割り当てられた要素の型。|  
  
## <a name="remarks"></a>コメント  
 [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) マクロは、このクラスを次のステートメント内の `name` パラメーターとして渡します: `ALLOCATOR_DECL(CACHE_FREELIST stdext::allocators::max_none), SYNC_DEFAULT, allocator_newdel);`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<allocators>  
  
 **名前空間:** stdext  
  
## <a name="see-also"></a>参照  
 [\<allocators>](../standard-library/allocators-header.md)



