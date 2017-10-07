---
title: "浮動小数点の制限 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- ranges, floating-point constants
- floating-point constants, limits
- FLOAT.H header file
- limits, floating-point constants
- floating-point numbers [C++]
- floating limits
ms.assetid: fc718652-1f4c-4ed8-af60-0e769637459c
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: a19ed24e7765c9b0042831fc2eda9df937be42b3
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="floating-limits"></a>浮動小数点の制限
**Microsoft 固有の仕様**  
  
 次の表に、浮動小数点定数の値に関する制限を示します。 また、これらの制限は、標準ヘッダー ファイル FLOAT.H で定義されます。  
  
### <a name="limits-on-floating-point-constants"></a>浮動小数点定数の制限  
  
|定数|説明|値|  
|--------------|-------------|-----------|  
|FLT_DIG DBL_DIG LDBL_DIG|q 桁の浮動小数点数を、精度を失わずに丸めて浮動小数点表現にしたり、戻したりできる桁数 q。|6 15 15|  
|FLT_EPSILON DBL_EPSILON LDBL_EPSILON|x + 1.0 が 1.0 に等しくならないような最小の正数 x。|1.192092896e-07F 2.2204460492503131e-016 2.2204460492503131e-016|  
|FLT_GUARD||0|  
|FLT_MANT_DIG DBL_MANT_DIG LDBL_MANT_DIG|浮動小数点の有効桁で FLT_RADIX により指定された基数の桁数。 基数は 2 です。そのためこれらの値は、ビットを指定します。|24 53 53|  
|FLT_MAX DBL_MAX LDBL_MAX|表現可能な最大浮動小数点数です。|3.402823466e+38F 1.7976931348623158e+308 1.7976931348623158e+308|  
|FLT_MAX_10_EXP DBL_MAX_10_EXP LDBL_MAX_10_EXP|最大の整数 10 した結果をその数値が表現可能な浮動小数点数です。|38 308 308|  
|FLT_MAX_EXP DBL_MAX_EXP LDBL_MAX_EXP|FLT_RADIX をその数値分累乗した結果が表現可能な浮動小数点数となる最大の整数。|128 1024 1024|  
|FLT_MIN DBL_MIN LDBL_MIN|正の最小数。|1.175494351e-38 f 2.2250738585072014e-308 2.2250738585072014e-308|  
|FLT_MIN_10_EXP DBL_MIN_10_EXP LDBL_MIN_10_EXP|負の値が最小の整数 10 をその数値分累乗した表現可能な浮動小数点数。|-37<br /><br /> -307<br /><br /> -307|  
|FLT_MIN_EXP DBL_MIN_EXP LDBL_MIN_EXP|FLT_RADIX をその数値分累乗した結果が表現可能な浮動小数点数となる最小の負の整数。|-125<br /><br /> -1021<br /><br /> -1021|  
|FLT_NORMALIZE||0|  
|FLT_RADIX _DBL_RADIX _LDBL_RADIX|指数表記の基数。|2 2 2|  
|FLT_ROUNDS _DBL_ROUNDS _LDBL_ROUNDS|浮動小数点加算の丸めモード。|1 (近く) 1 (近く) 1 (近く)|  
  
> [!NOTE]
>  この表の情報は、将来のバージョンの製品では異なる場合があります。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [整数の制限](../cpp/integer-limits.md)
