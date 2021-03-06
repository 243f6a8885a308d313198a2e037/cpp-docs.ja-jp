---
title: Module::genericreleasenotifier クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GenericReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- GenericReleaseNotifier class
ms.assetid: 244a8fbe-f89b-409b-aa65-db3e37f9b125
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ba92e459ffb26ffc1bbb9239a843d628e7041d6d
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40013520"
---
# <a name="modulegenericreleasenotifier-class"></a>Module::GenericReleaseNotifier クラス
現在のモジュールの最後のオブジェクトがリリースされたときに、イベント ハンドラーを呼び出します。 イベント ハンドラーは、ラムダをファンクター、または関数へのポインターによって指定されます。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template<typename T>  
class GenericReleaseNotifier : public ReleaseNotifier;  
```  
  
### <a name="parameters"></a>パラメーター  
 *T*  
 イベント ハンドラーの場所を含むデータ メンバーの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier::GenericReleaseNotifier コンストラクター](../windows/module-genericreleasenotifier-genericreleasenotifier-constructor.md)|新しいインスタンスを初期化、 **module::genericreleasenotifier**クラス。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier::Invoke メソッド](../windows/module-genericreleasenotifier-invoke-method.md)|現在関連付けられているイベント ハンドラーを呼び出す**module::genericreleasenotifier**オブジェクト。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier::callback_ データ メンバー](../windows/module-genericreleasenotifier-callback-data-member.md)|ラムダ、ファンクター、または現在に関連付けられている関数へのポインター イベント ハンドラーを保持**module::genericreleasenotifier**オブジェクト。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ReleaseNotifier`  
  
 `GenericReleaseNotifier`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>関連項目
 [Module クラス](../windows/module-class.md)