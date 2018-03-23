---
title: SimpleActivationFactory クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- SimpleActivationFactory class
ms.assetid: aff768e0-0038-4fd7-95d2-ad7d308da41c
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0f6aabaae1e19fef3631e372391c81108f212c90
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2018
---
# <a name="simpleactivationfactory-class"></a>SimpleActivationFactory クラス
Windows ランタイムまたはクラシック COM の基底クラスを作成するための基本的なメカニズムを提供します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Base>  
class SimpleActivationFactory : public ActivationFactory<>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Base`  
 基本クラスです。  
  
## <a name="remarks"></a>コメント  
 基本クラスには、既定のコンス トラクターを提供する必要があります。  
  
 次のコード例で SimpleActivationFactory を使用する方法を示します、 [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md)マクロです。  
  
 `ActivatableClassWithFactoryEx(MyClass, SimpleActivationFactory, MyServerName);`  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[SimpleActivationFactory::ActivateInstance メソッド](../windows/simpleactivationfactory-activateinstance-method.md)|指定されたインターフェイスのインスタンスを作成します。|  
|[SimpleActivationFactory::GetRuntimeClassName メソッド](../windows/simpleactivationfactory-getruntimeclassname-method.md)|によって指定されたクラスのインスタンスのランタイム クラス名を取得、`Base`クラス テンプレート パラメーター。|  
|[SimpleActivationFactory::GetTrustLevel メソッド](../windows/simpleactivationfactory-gettrustlevel-method.md)|によって指定されたクラスのインスタンスの信頼レベルを取得、`Base`クラス テンプレート パラメーター。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `RuntimeClassBase`  
  
 `ImplementsHelper`  
  
 `DontUseNewUseMake`  
  
 `RuntimeClassFlags`  
  
 `RuntimeClassBaseT`  
  
 `RuntimeClass`  
  
 `ActivationFactory`  
  
 `SimpleActivationFactory`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)