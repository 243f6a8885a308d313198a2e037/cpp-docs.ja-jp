---
title: Comptr::operator:details::booltype 演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: cfba6521-fb30-4fb8-afb2-cfab1cb5e0b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb5735eeb9cd4048596588765468fbb9c5e07496
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652602"
---
# <a name="comptroperator-microsoftwrldetailsbooltype-operator"></a>ComPtr::operator Microsoft::WRL::Details::BoolType 演算子
示すかどうかを**ComPtr**インターフェイスのオブジェクトの有効期間を管理します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;  
```  
  
## <a name="return-value"></a>戻り値  
 インターフェイスに関連付けられている場合**ComPtr**のアドレス、 [boolstruct::member](../windows/boolstruct-member-data-member.md)データ メンバー、それ以外の**nullptr**します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ComPtr クラス](../windows/comptr-class.md)   
 [ComPtr::Get メソッド](../windows/comptr-get-method.md)