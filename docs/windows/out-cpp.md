---
title: "out (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.out
dev_langs:
- C++
helpviewer_keywords:
- out attribute
ms.assetid: 5051b1bf-4949-4bf1-b82f-35e14f0f244b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ee63988571f7db0a872bf0286dae952f3066f0e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="out-c"></a>out (C++)
呼び出されたプロシージャから呼び出したプロシージャ (サーバーからクライアント) に返されるポインター パラメーターを示します。  
  
## <a name="syntax"></a>構文  
  
```  
  
[out]  
  
```  
  
## <a name="remarks"></a>コメント  
 **out** C++ 属性には、 [propput](http://msdn.microsoft.com/library/windows/desktop/aa367136) MIDL 属性と同じ機能があります。  
  
## <a name="example"></a>例  
 [out](../windows/bindable.md) の使用サンプルについては、「 **bindable**」の例を参照してください。  
  
## <a name="requirements"></a>必要条件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|インターフェイス パラメーター|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [IDL 属性](../windows/idl-attributes.md)   
 [パラメーター属性](../windows/parameter-attributes.md)   
 [defaultvalue](../windows/defaultvalue.md)   
 [ID](../windows/id.md)   
