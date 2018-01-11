---
title: "uuid (C++ 属性) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.uuid
dev_langs: C++
helpviewer_keywords: uuid attribute
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ba35dc89ae2567a499d4623f0c74293d2dbdcca2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="uuid-c-attributes"></a>uuid (C++ 属性)
クラスまたはインターフェイスの一意の ID を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ uuid(  
   "uuid"  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *uuid*  
 128 ビットの一意の識別子です。  
  
## <a name="remarks"></a>コメント  
 インターフェイスまたはクラスの定義を指定しないかどうか、 `uuid` C++ 属性、Visual C コンパイラはいずれかで提供されます。 指定すると、`uuid`引用符を含める必要があります。  
  
 指定しない場合`uuid`コンパイラが、コンピューター上の別の属性をプロジェクト内のインターフェイスまたは同じ名前のクラスは、同じ GUID を生成します。  
  
 Uuidgen.exe または Guidgen.exe を使用すると、独自の一意の Id を生成します。 (これらのツールのいずれかを実行する をクリックして**開始** をクリック**実行**メニュー。 Enter、必要なツールの名前です。)  
  
 ATL にも使用しないプロジェクトで使用されている場合を指定して、`uuid`属性を指定することと同じ、 [uuid](../cpp/uuid-cpp.md) _ _declspec 修飾子です。 取得する、`uuid`を使用できる、クラスの[_ _uuidof](../cpp/uuidof-operator.md)  
  
## <a name="example"></a>例  
 参照してください、[バインド可能な](../windows/bindable.md)のサンプルの使用例`uuid`です。  
  
## <a name="requirements"></a>必要条件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**クラス**、 `struct`、 `interface`、**共用体**、`enum`|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [IDL 属性](../windows/idl-attributes.md)   
 [インターフェイス属性](../windows/interface-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [uuid](http://msdn.microsoft.com/library/windows/desktop/aa367302)   
