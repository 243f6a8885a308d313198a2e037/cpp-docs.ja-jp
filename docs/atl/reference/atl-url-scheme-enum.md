---
title: ATL_URL_SCHEME 列挙型 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ATLUTIL/ATL::ATL_URL_SCHEME
ms.assetid: f4131046-8ba0-4ec1-8209-84203f05d20e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ee13d34bcea1e7ce2e53b0659739ee730152f287
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755412"
---
# <a name="atlurlscheme"></a>ATL_URL_SCHEME  

この列挙体のメンバーで認識されるスキーマの定数を提供する[CUrl](curl-class.md)します。

## <a name="syntax"></a>構文

```

      enum ATL_URL_SCHEME{  
   ATL_URL_SCHEME_UNKNOWN = -1,  
   ATL_URL_SCHEME_FTP     = 0,  
   ATL_URL_SCHEME_GOPHER  = 1,  
   ATL_URL_SCHEME_HTTP    = 2,  
   ATL_URL_SCHEME_HTTPS   = 3,  
   ATL_URL_SCHEME_FILE    = 4,  
   ATL_URL_SCHEME_NEWS    = 5,  
   ATL_URL_SCHEME_MAILTO  = 6,  
   ATL_URL_SCHEME_SOCKS   = 7  
};  
```

## <a name="requirements"></a>要件

**ヘッダー:** atlutil.h

## <a name="see-also"></a>関連項目

[概念](../active-template-library-atl-concepts.md)   
[CUrl::SetScheme](curl-class.md#setscheme)   
[CUrl::GetScheme](curl-class.md#getscheme)