---
title: Activationfactory::getruntimeclassname メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory::GetRuntimeClassName
dev_langs:
- C++
helpviewer_keywords:
- GetRuntimeClassName method
ms.assetid: 74e34f0a-9c51-4b40-89f5-45c6c5886ece
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: edc4658ebf0519ef9d1792d62b303f423e658835
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643070"
---
# <a name="activationfactorygetruntimeclassname-method"></a>ActivationFactory::GetRuntimeClassName メソッド
オブジェクトのランタイム クラス名を取得、現在**ActivationFactory**をインスタンス化します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
STDMETHOD(  
   GetRuntimeClassName  
)(_Out_ HSTRING* runtimeName);  
```  
  
### <a name="parameters"></a>パラメーター  
 *runtimeName*  
 ときにこの操作が完了すると、オブジェクトのランタイム クラス名を含む文字列を識別するハンドルを現在**ActivationFactory**をインスタンス化します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ActivationFactory クラス](../windows/activationfactory-class.md)