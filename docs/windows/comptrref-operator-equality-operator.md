---
title: Comptrref::operator = 演算子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::operator==
dev_langs:
- C++
ms.assetid: 95fcf781-b473-4317-88cd-e938778d3c3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a36e3068bd5211f37e6fe1f0f2a82c923b4511a6
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650704"
---
# <a name="comptrrefoperator-operator"></a>ComPtrRef::operator== 演算子
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```cpp  
bool operator==(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   const Details::ComPtrRef<ComPtr<U>>& b  
);  
  
bool operator==(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   decltype(__nullptr)  
);  
  
bool operator==(  
   decltype(__nullptr),  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
  
bool operator==(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   void* b  
);  
  
bool operator==(  
   void* b,  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 *a*  
 参照を**ComPtrRef**オブジェクト。  
  
 *b*  
 別の参照**ComPtrRef**オブジェクト、または匿名型へのポインター (`void*`)。  
  
## <a name="return-value"></a>戻り値  
 最初の演算子と**true**場合オブジェクト *、* がオブジェクトと等しい*b*、それ以外の**false**します。  
  
 2 番目と 3 番目の演算子を生成**true**場合オブジェクト *、* と等しい**nullptr**、それ以外の**false**します。  
  
 4 番目と 5 番目の演算子を生成**true**場合オブジェクト *、* がオブジェクトと等しい*b*、それ以外の**false**します。  
  
## <a name="remarks"></a>Remarks  
 示す 2 つかどうか**ComPtrRef**オブジェクトが等しい。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtrRef クラス](../windows/comptrref-class.md)