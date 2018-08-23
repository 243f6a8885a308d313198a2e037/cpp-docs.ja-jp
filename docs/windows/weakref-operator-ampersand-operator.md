---
title: Weakref::operator&amp;演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::operator&
dev_langs:
- C++
helpviewer_keywords:
- operator& operator
ms.assetid: 900afb73-3801-4d08-9b41-2e6a62011ccd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f8bb81ca1591fc398b1d0814fca918309169e82c
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600985"
---
# <a name="weakrefoperatoramp-operator"></a>Weakref::operator&amp;演算子

返します、`ComPtrRef`現在を表すオブジェクトを**WeakRef**オブジェクト。

## <a name="syntax"></a>構文

```cpp
Details::ComPtrRef<WeakRef> operator&() throw()  
```

## <a name="return-value"></a>戻り値

A`ComPtrRef`現在を表すオブジェクトを**WeakRef**オブジェクト。

## <a name="remarks"></a>Remarks

これは、内部ヘルパー演算子が、コードで使用されるものではありません。

## <a name="requirements"></a>要件

**ヘッダー:** client.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[WeakRef クラス](../windows/weakref-class.md)