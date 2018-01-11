---
title: "CriticalSection クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::CriticalSection
dev_langs: C++
helpviewer_keywords: CriticalSection class
ms.assetid: f2e0a024-71a3-4f6b-99ea-d93a4a608ac4
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e2bf6e4728bac6622f9872ab939e084b14f49ae8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="criticalsection-class"></a>CriticalSection クラス
クリティカル セクション オブジェクトを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CriticalSection;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="constructor"></a>コンストラクター  
  
|name|説明|  
|----------|-----------------|  
|[CriticalSection::CriticalSection コンストラクター](../windows/criticalsection-criticalsection-constructor.md)|ミュー テックス オブジェクトに似ていますが、1 つのプロセスのスレッドのみで使用できる同期オブジェクトを初期化します。|  
|[CriticalSection::~CriticalSection デストラクター](../windows/criticalsection-tilde-criticalsection-destructor.md)|初期化を解除し、現在の CriticalSection オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CriticalSection::TryLock メソッド](../windows/criticalsection-trylock-method.md)|ブロックすることがなく、クリティカル セクションを入力しようとしています。 呼び出しが成功した場合、呼び出し元スレッドは、クリティカル セクションの所有権を取得します。|  
|[CriticalSection::Lock メソッド](../windows/criticalsection-lock-method.md)|指定されたクリティカル セクション オブジェクトの所有権を待機します。 この関数は、呼び出し元のスレッドには、所有権が付与されるを返します。|  
|[CriticalSection::IsValid メソッド](../windows/criticalsection-isvalid-method.md)|現在の重要なセクションが有効かどうかを示します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CriticalSection::cs_ データ メンバー](../windows/criticalsection-cs-data-member.md)|クリティカル セクションのデータ メンバーを宣言します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CriticalSection`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>参照  
 [Microsoft::WRL::Wrappers 名前空間](../windows/microsoft-wrl-wrappers-namespace.md)