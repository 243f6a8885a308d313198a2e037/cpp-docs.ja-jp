---
title: 関数の移動 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::Move
dev_langs:
- C++
helpviewer_keywords:
- Move function
ms.assetid: c9525426-97e8-4d8c-9877-b689d8a0dc67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 018b5832b187223484013702a1b7d4871d0b1d44
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015717"
---
# <a name="move-function"></a>Move 関数
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template<class T>  
inline typename RemoveReference<T>::Type&& Move(  
   _Inout_ T&& arg  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 *T*  
 引数の型。  
  
 *arg*  
 移動する引数。  
  
## <a name="return-value"></a>戻り値  
 パラメーター *arg*参照または右辺値参照の特徴の後に存在する場合、削除されました。  
  
## <a name="remarks"></a>Remarks  
 指定した引数を 1 つの場所から移動します。  
  
 詳細については、次を参照してください。、**移動セマンティクス**の[右辺値参照宣言子: & &](../cpp/rvalue-reference-declarator-amp-amp.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** internal.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)