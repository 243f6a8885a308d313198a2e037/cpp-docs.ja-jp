---
title: Classfactory::addref メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory::AddRef
dev_langs:
- C++
helpviewer_keywords:
- AddRef method
ms.assetid: 5b091785-dea4-42b6-a502-0db5fc7a5a2e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 276024be7b3d75edf308e43a08e4d2cbe9901c1e
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652056"
---
# <a name="classfactoryaddref-method"></a>ClassFactory::AddRef メソッド
現在の参照カウントをインクリメント**ClassFactory**オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp  
STDMETHOD_(  
   ULONG,  
   AddRef  
)();  
```  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ClassFactory クラス](../windows/classfactory-class.md)