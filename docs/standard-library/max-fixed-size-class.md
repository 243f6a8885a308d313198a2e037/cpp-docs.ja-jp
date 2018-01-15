---
title: "max_fixed_size クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::max_fixed_size
- allocators/stdext::max_fixed_size::allocated
- allocators/stdext::max_fixed_size::deallocated
- allocators/stdext::max_fixed_size::full
- allocators/stdext::max_fixed_size::released
- allocators/stdext::max_fixed_size::saved
dev_langs: C++
helpviewer_keywords:
- stdext::max_fixed_size
- stdext::max_fixed_size [C++], allocated
- stdext::max_fixed_size [C++], deallocated
- stdext::max_fixed_size [C++], full
- stdext::max_fixed_size [C++], released
- stdext::max_fixed_size [C++], saved
ms.assetid: 8c8f4588-37e9-4579-8168-ba3553800914
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a853e417ad79ed27f7579ce50186974abfe21c3e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="maxfixedsize-class"></a>max_fixed_size クラス
[freelist](../standard-library/freelist-class.md) オブジェクトを固定の最長値までに制限する[最大クラス](../standard-library/allocators-header.md) オブジェクトを記述します。  
  
## <a name="syntax"></a>構文  
  
```
template <std::size_t Max>  
class max_fixed_size
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`Max`|`freelist` に格納する要素の最大数を決定する、最大クラス。|  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[max_fixed_size](#max_fixed_size)|`max_fixed_size` 型のオブジェクトを構築します。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[allocated](#allocated)|割り当てられたメモリ ブロックの数を増やします。|  
|[deallocated](#deallocated)|割り当てられたメモリ ブロックの数を減らします。|  
|[full](#full)|フリー リストにメモリ ブロックを追加する必要があるかどうかを示す値を返します。|  
|[released](#released)|フリー リスト上のメモリ ブロックの数を減らします。|  
|[saved](#saved)|フリー リスト上のメモリ ブロックの数を減らします。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<allocators>  
  
 **名前空間:** stdext  
  
##  <a name="allocated"></a>  max_fixed_size::allocated  
 割り当てられたメモリ ブロックの数を増やします。  
  
```
void allocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`_Nx`|増分値。|  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は何も処理を行いません。 このメンバー関数は、`cache_freelist::allocate` による演算子 `new` への呼び出しが成功するたび、その後に呼び出されます。 引数 `_Nx` は、演算子 `new` によって割り当てられたチャンク内のメモリ ブロックの数です。  
  
##  <a name="deallocated"></a>  max_fixed_size::deallocated  
 割り当てられたメモリ ブロックの数を減らします。  
  
```
void deallocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`_Nx`|増分値。|  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は何も処理を行いません。 このメンバー関数は、`cache_freelist::deallocate` による演算子 `delete` への呼び出しがあるたび、その後に呼び出されます。 引数 `_Nx` は、演算子 `delete` によって割り当て解除されたチャンク内のメモリ ブロックの数です。  
  
##  <a name="full"></a>  max_fixed_size::full  
 フリー リストにメモリ ブロックを追加する必要があるかどうかを示す値を返します。  
  
```
bool full();
```  
  
### <a name="return-value"></a>戻り値  
 `Max <= _Nblocks` の場合は `true`。それ以外の場合は `false`。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は `cache_freelist::deallocate` によって呼び出されます。 呼び出しが `true` を返すと、`deallocate` はメモリ ブロックをフリー リストに置きます。false を返す場合は、`deallocate` は演算子 `delete` を呼び出してブロックの割り当てを解除します。  
  
##  <a name="max_fixed_size"></a>  max_fixed_size::max_fixed_size  
 `max_fixed_size` 型のオブジェクトを構築します。  
  
```
max_fixed_size();
```  
  
### <a name="remarks"></a>コメント  
 このコンストラクターは、格納された値 `_Nblocks` をゼロに初期化します。  
  
##  <a name="released"></a>  max_fixed_size::released  
 フリー リスト上のメモリ ブロックの数を減らします。  
  
```
void released();
```  
  
### <a name="remarks"></a>コメント  
 格納された `_Nblocks`を減らします。 現在の[最大クラス](../standard-library/allocators-header.md)の`released` メンバー関数は、`cache_freelist::allocate` によって、フリー リストからメモリ ブロックが削除されるたびに、呼び出されます。  
  
##  <a name="saved"></a>  max_fixed_size::saved  
 フリー リスト上のメモリ ブロックの数を減らします。  
  
```
void saved();
```  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、格納された値 `_Nblocks` を増やします。 このメンバー関数は、`cache_freelist::deallocate` によって、フリー リストにメモリ ブロックが置かれるたびに、呼び出されます。  
  
## <a name="see-also"></a>参照  
 [\<allocators>](../standard-library/allocators-header.md)



