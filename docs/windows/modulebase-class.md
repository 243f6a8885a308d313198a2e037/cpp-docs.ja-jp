---
title: ModuleBase クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase
dev_langs:
- C++
helpviewer_keywords:
- ModuleBase class
ms.assetid: edce7591-6893-46f7-94a7-382827775548
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8ff7fb86b7b39e283c27ee78611444b78bc53c5b
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020279"
---
# <a name="modulebase-class"></a>ModuleBase クラス
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```cpp  
class ModuleBase;  
```  
  
## <a name="remarks"></a>Remarks  
 基本クラスを表します、[モジュール](../windows/module-class.md)クラス。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[ModuleBase::ModuleBase コンストラクター](../windows/modulebase-modulebase-constructor.md)|
          `Module` クラスのインスタンスを初期化します。|  
|[ModuleBase::~ModuleBase デストラクター](../windows/modulebase-tilde-modulebase-destructor.md)|現在のインスタンスの初期化を解除、`Module`クラス。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ModuleBase::DecrementObjectCount メソッド](../windows/modulebase-decrementobjectcount-method.md)|実装された場合、デクリメント オブジェクトの数によって追跡モジュール。|  
|[ModuleBase::IncrementObjectCount メソッド](../windows/modulebase-incrementobjectcount-method.md)|実装された場合、モジュールによって追跡されるオブジェクトの数をインクリメントします。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ModuleBase`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)