---
title: Module::registerwinrtobject メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::RegisterWinRTObject
dev_langs:
- C++
helpviewer_keywords:
- RegisterWinRTObject method
ms.assetid: a2782c9c-b9c5-4e4b-9c8d-ef513aea20c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5b5605b68c569d4579324b51eaad42b1e9532011
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017416"
---
# <a name="moduleregisterwinrtobject-method"></a>Module::RegisterWinRTObject メソッド
他のアプリケーションがそれらに接続できるように、1 つまたは複数の Windows ランタイム オブジェクトを登録します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT RegisterWinRTObject(const wchar_t* serverName,  
   wchar_t** activatableClassIds,  
   WINRT_REGISTRATION_COOKIE* cookie,  
   unsigned int count)  
```  
  
### <a name="parameters"></a>パラメーター  
 *サーバー名*  
 この操作によって影響を受けるオブジェクトのサブセットを指定する名前。  
  
 *activatableClassIds*  
 登録のアクティブ化可能な Clsid の配列。  
  
 *Cookie*  
 登録済みのクラス オブジェクトを識別する値。 この値は、登録を取り消すに後で使用されます。  
  
 *count*  
 登録するオブジェクトの数。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は s_ok を返します。それ以外の場合、エラーの hresult 値理由を示す CO_E_OBJISREG など、操作に失敗しました。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>関連項目
 [Module クラス](../windows/module-class.md)