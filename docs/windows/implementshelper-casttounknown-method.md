---
title: Implementshelper::casttounknown メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper::CastToUnknown
dev_langs:
- C++
helpviewer_keywords:
- CastToUnknown method
ms.assetid: 5bcfcbaf-c75f-4d43-87b3-0d6838c838d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 99430222c0df705297f013381b4497730c7c9fa5
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016237"
---
# <a name="implementshelpercasttounknown-method"></a>ImplementsHelper::CastToUnknown メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```cpp  
IUnknown* CastToUnknown();  
```  
  
## <a name="return-value"></a>戻り値  
 基になるポインター`IUnknown`インターフェイス。  
  
## <a name="remarks"></a>Remarks  
 基になるポインターを取得します。 `IUnknown` 、現在のインターフェイス`Implements`構造体。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [ImplementsHelper 構造体](../windows/implementshelper-structure.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)