---
title: "pointer_traits 構造体 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- memory/std::pointer_traits::element_type
- memory/std::pointer_traits::pointer
- memory/std::pointer_traits
- memory/std::pointer_traits::difference_type
- memory/std::pointer_traits::rebind
- xmemory0/std::pointer_traits::element_type
- xmemory0/std::pointer_traits::pointer
- xmemory0/std::pointer_traits
- xmemory0/std::pointer_traits::difference_type
- xmemory0/std::pointer_traits::rebind
- memory/std::pointer_traits::pointer_to
dev_langs: C++
ms.assetid: 545aecf1-3561-4859-8b34-603c079fe1b3
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b82970336c11e8060b01b9c78b48b21accdc67db
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="pointertraits-struct"></a>pointer_traits 構造体
`allocator_traits` テンプレート クラスのオブジェクトが、ポインター型 `Ptr` を持つアロケーターを記述するために必要とする情報を提供します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template <class Ptr>
struct pointer_traits;
```  
  
## <a name="remarks"></a>コメント  
 Ptr には `Ty *` 型の生のポインターまたは次のプロパティを持つクラスを指定できます。  
```  
struct Ptr
   { // describes a pointer type usable by allocators
   typedef Ptr pointer;
   typedef T1 element_type; // optional
   typedef T2 difference_type; // optional
   template <class Other>
   using rebind = typename Ptr<Other, Rest...>; // optional
   static pointer pointer_to(element_type& obj);
   // optional
   };  
```
### <a name="typedefs"></a>Typedefs  
  
|名前|説明|  
|----------|-----------------|  
|`typedef T2 difference_type`|`T2` 型は、その型が存在する場合は `Ptr::difference_type`、それ以外の場合は `ptrdiff_t` です。 `Ptr` が生のポインターの場合、型は `ptrdiff_t` です。|  
|`typedef T1 element_type`|`T1` 型は、その型が存在する場合は `Ptr::element_type`、それ以外の場合は `Ty` です。 `Ptr` が生のポインターの場合、型は `Ty` です。|  
|`typedef Ptr pointer`|型は `Ptr` です。|  
  
### <a name="structs"></a>構造体  
  
|name|説明|  
|----------|-----------------|  
|`pointer_traits::rebind`|基になるポインター型を指定された型に変換しようとします。|  
  
### <a name="methods"></a>メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[pointer_to](#pointer_to)|任意の参照をクラス `Ptr` のオブジェクトに変換します。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<memory>  
  
 **名前空間:** std  
  
##  <a name="pointer_to"></a>  pointer_to  
 その関数が存在する場合に `Ptr::pointer_to(obj)` を返す静的メソッド。 それ以外の場合は、任意の参照をクラス `Ptr` のオブジェクトに変換できません。 `Ptr` が生のポインターの場合、このメソッドは `addressof(obj)` を返します。  
  
```cpp  
static pointer pointer_to(element_type& obj);
```  
  
## <a name="see-also"></a>参照  
 [\<memory>](../standard-library/memory.md)   
 [allocator_traits クラス](../standard-library/allocator-traits-class.md)

