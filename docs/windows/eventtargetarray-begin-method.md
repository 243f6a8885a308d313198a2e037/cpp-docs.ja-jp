---
title: Eventtargetarray::begin メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::Begin
dev_langs:
- C++
helpviewer_keywords:
- Begin method
ms.assetid: 1cc7fdfd-a2c4-4b28-93cf-1c82842294ba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b5dc081a24495fc8939f3069dc68bed4f75beaaf
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642826"
---
# <a name="eventtargetarraybegin-method"></a>EventTargetArray::Begin メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```cpp  
ComPtr<IUnknown>* Begin();  
```  
  
## <a name="return-value"></a>戻り値  
 イベント ハンドラーの内部配列の最初の要素のアドレス。  
  
## <a name="remarks"></a>Remarks  
 イベント ハンドラーの内部配列の最初の要素のアドレスを取得します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [EventTargetArray クラス](../windows/eventtargetarray-class.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)