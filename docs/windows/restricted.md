---
title: "制限付き |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.restricted
dev_langs:
- C++
helpviewer_keywords:
- restricted attribute
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 569d57da691f40857f54dcae1c383ff7758564f4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="restricted"></a>restricted
モジュール、インターフェイス、またはディスパッチ インターフェイスのメンバーを任意に呼び出すことができませんを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ restricted(  
   interfaces  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 `interfaces`  
 呼び出すことはできません任意に COM オブジェクトで 1 つまたは複数のインターフェイス。 このパラメーターは、クラスに適用する場合に有効ではのみです。  
  
## <a name="remarks"></a>コメント  
 **制限**C++ 属性と同じ機能を持つ、[制限](http://msdn.microsoft.com/library/windows/desktop/aa367157)MIDL 属性。  
  
## <a name="example"></a>例  
 次のコードを使用する方法を示しています、**制限**属性。  
  
```  
// cpp_attr_ref_restricted.cpp  
// compile with: /LD  
#include "windows.h"  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface a  
{  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000002")]  
__interface b  
{  
};  
  
[coclass, restricted(a,b), uuid("00000000-0000-0000-0000-000000000003")]  
class c : public a, public b  
{  
};  
```  
  
## <a name="requirements"></a>必要条件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|インターフェイス メソッド、 `interface`、**クラス**、`struct`|  
|**反復可能**|×|  
|**必要な属性**|**coclass** ( **class** または `struct`に適用される場合)|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [IDL 属性](../windows/idl-attributes.md)   
 [インターフェイス属性](../windows/interface-attributes.md)   
 [メソッド属性](../windows/method-attributes.md)   
