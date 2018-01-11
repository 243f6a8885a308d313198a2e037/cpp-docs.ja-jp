---
title: "wire_marshal |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.wire_marshal
dev_langs: C++
helpviewer_keywords: wire_marshal attribute
ms.assetid: 244f9d72-776d-4ebd-b60a-cee600a126b5
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a5f61e753e6b87f2dbdbd5fcfe7052ddf8e00724
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="wiremarshal"></a>wire_marshal
送信アプリケーションに固有のデータ型の代わりに使用されるデータ型を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
[wire_marshal]  
  
```  
  
## <a name="remarks"></a>コメント  
 **Wire_marshal** C++ 属性と同じ機能を持つ、 [wire_marshal](http://msdn.microsoft.com/library/windows/desktop/aa367309) MIDL 属性。  
  
## <a name="example"></a>例  
 次のコードは、の使い方を示しています**wire_marshal**:。  
  
```  
// cpp_attr_ref_wire_marshal.cpp  
// compile with: /LD  
#include "windows.h"  
[module(name="MyLibrary")];  
  
[export, public] typedef unsigned long _FOUR_BYTE_DATA;  
  
[export] typedef struct _TWO_X_TWO_BYTE_DATA {  
   unsigned short low;  
   unsigned short high;  
} TWO_X_TWO_BYTE_DATA ;  
  
[export, wire_marshal(TWO_X_TWO_BYTE_DATA)] typedef _FOUR_BYTE_DATA FOUR_BYTE_DATA;  
```  
  
## <a name="requirements"></a>必要条件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|`typedef`|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [IDL 属性](../windows/idl-attributes.md)   
 [Typedef、Enum、Union、および Struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
