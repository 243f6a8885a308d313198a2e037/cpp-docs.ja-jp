---
title: "ライセンス供与 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.licensed
dev_langs:
- C++
helpviewer_keywords:
- licensed attribute
ms.assetid: 09cf3b4a-d3f2-43e3-9180-d420333b23bf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8d33e51cf938642f2ff54c48e1ecd22c3f48b71f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="licensed"></a>licensed
適用すると、COM オブジェクトはライセンスされていることを示しますを使用してインスタンス化する必要があります**IClassFactory2**です。  
  
## <a name="syntax"></a>構文  
  
```  
  
[licensed]  
  
```  
  
## <a name="remarks"></a>コメント  
 **ライセンス**C++ 属性と同じ機能を持つ、[ライセンス](http://msdn.microsoft.com/library/windows/desktop/aa367070)MIDL 属性。  
  
## <a name="example"></a>例  
  
```  
// cpp_attr_ref_licensed.cpp  
// compile with: /LD  
#include "unknwn.h"  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI : IUnknown {  
   HRESULT f();  
};  
  
[coclass, version("2.1"), uuid(12345678-1111-2222-3333-123456789012),   
licensed, threading(free), progid(some.name)]  
class CSample : public IMyI {  
public:  
   int nSize;  
};  
  
[module(name="MyLibrary", version="1.0", helpstring="My Library Block")];  
```  
  
## <a name="requirements"></a>必要条件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**class**、 `struct`|  
|**反復可能**|×|  
|**必要な属性**|**coclass**|  
|**無効な属性**|なし|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [IDL 属性](../windows/idl-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
