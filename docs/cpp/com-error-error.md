---
title: _com_error::Error |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::Error
- Error
dev_langs:
- C++
helpviewer_keywords:
- Error method [C++]
ms.assetid: b53a15fd-198e-4276-afcd-13439c4807f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6a7ddaefcf3bd46bf40b03c03d2d1fb00cf8fbbb
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408428"
---
# <a name="comerrorerror"></a>_com_error::Error
**Microsoft 固有の仕様**  
  
 コンス トラクターに渡された HRESULT を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT Error( ) const throw( );  
```  
  
## <a name="return-value"></a>戻り値  
 生の HRESULT 項目は、コンス トラクターに渡されます。  
  
## <a name="remarks"></a>Remarks  
 カプセル化された HRESULT 項目を取得、`_com_error`オブジェクト。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_error クラス](../cpp/com-error-class.md)