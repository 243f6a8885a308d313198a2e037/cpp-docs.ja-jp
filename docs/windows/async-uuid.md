---
title: "async_uuid |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.async_uuid
dev_langs:
- C++
helpviewer_keywords:
- async_uuid attribute
ms.assetid: 235cb0d7-be58-4dd9-983c-e2a21bbc42c6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9c3d9fc9afb7a6f65be8ace5fec085db9bd92191
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="asyncuuid"></a>async_uuid
COM インターフェイスの同期および非同期の両方のバージョンを定義する MIDL コンパイラに指示する UUID を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [async_uuid (  
   uuid  
)]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *uuid*  
 インターフェイスのバージョンを識別するための UUID。  
  
## <a name="remarks"></a>コメント  
 **Async_uuid** C++ 属性と同じ機能を持つ、 [async_uuid](http://msdn.microsoft.com/library/windows/desktop/aa366735) MIDL 属性。  
  
## <a name="example"></a>例  
  
```  
// cpp_attr_ref_async_uuid.cpp  
// compile with: /LD  
#include <Windows.h>  
[module(name="Test")];  
[object, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb"),   
async_uuid("e8583106-38fd-487e-912e-4fc8645c677e")]  
__interface ICustom {  
   HRESULT Custom([in] long l, [out, retval] long *pLong);  
};  
```  
  
## <a name="requirements"></a>必要条件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|`interface`|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|**デュアル**、**ディスパッチ インターフェイス**|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [IDL 属性](../windows/idl-attributes.md)   
 [インターフェイス属性](../windows/interface-attributes.md)   
