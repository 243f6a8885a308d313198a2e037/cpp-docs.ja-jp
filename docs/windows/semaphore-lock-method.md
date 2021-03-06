---
title: Semaphore::lock メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 0eef6ede-dc7d-4f09-a6c8-2f7d39d65bfa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: be7a2b7bbac8affd0bc668113cac30f4bed96a6b
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017296"
---
# <a name="semaphorelock-method"></a>Semaphore::Lock メソッド
現在のオブジェクトまでの待機、または**セマフォ**オブジェクトに関連付けられている指定したハンドルがシグナル状態で、または指定されたタイムアウト期間が経過しました。  
  
## <a name="syntax"></a>構文  
  
```cpp  
SyncLock Lock(  
   DWORD milliseconds = INFINITE  
);  
  
static SyncLock Lock(  
   HANDLE h,  
   DWORD milliseconds = INFINITE  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 *(ミリ秒)*  
 タイムアウト間隔 (ミリ秒単位)。 既定値は、INFINITE で、無期限に待機します。  
  
 *h*  
 識別するハンドルを**セマフォ**オブジェクト。  
  
## <a name="return-value"></a>戻り値  
 `Details::SyncLockWithStatusT<HandleTraits::SemaphoreTraits>`。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [Semaphore クラス](../windows/semaphore-class.md)