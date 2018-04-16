---
title: "exp2、exp2f、exp2l | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- exp2
- exp2f
- exp2l
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- exp2
- math/exp2
- exp2f
- math/exp2f
- exp2l
- math/exp2l
dev_langs:
- C++
helpviewer_keywords:
- exp2 function
- exp2f function
- exp2l function
ms.assetid: 526e3e10-201a-4610-a886-533f44ece344
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8bf1eca51bbe7d5db5044e0c863f30a5af63f77d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="exp2-exp2f-exp2l"></a>exp2、exp2f、exp2l
2 の指定した値を計算します。  
  
## <a name="syntax"></a>構文  
  
```  
double exp2(  
   double x  
);  
  
float exp2(  
   float x  
);  // C++ only  
  
long double exp2(  
   long double x  
); // C++ only  
  
float exp2f(  
   float x  
);  
  
long double exp2l(  
   long double x  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `x`  
 指数部の値です。  
  
## <a name="return-value"></a>戻り値  
 成功した場合の 2 を底と指数を返します`x`、つまり、2<sup>x</sup>です。 それ以外の場合、次の値のいずれかを返します。  
  
|懸案事項|Return|  
|-----------|------------|  
|`x` = ±0|1|  
|`x` = -INFINITY|+0|  
|`x` = +INFINITY|+INFINITY|  
|`x` = NaN|NaN|  
|オーバーフロー範囲エラー|+HUGE_VAL、+HUGE_VALF、または +HUGE_VALL|  
|アンダーフロー範囲エラー|丸め処理の後に、正しい結果|  
  
 エラーは、[_matherr](../../c-runtime-library/reference/matherr.md) で指定されたとおりに報告されます。  
  
## <a name="remarks"></a>コメント  
 C++ では、オーバー ロードできるよう、ためのオーバー ロードを呼び出すことができます`exp2`を受け取り、返します**float**と**long double**型です。 C プログラムでは、`exp2`常に受け取りを返す、**二重**です。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|C ヘッダー|C++ ヘッダー|  
|-------------|--------------|------------------|  
|`exp`、`expf`、`expl`|\<math.h>|\<cmath>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [関数リファレンス (アルファベット順)](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [exp, expf, expl](../../c-runtime-library/reference/exp-expf.md)   
 [log2、log2f、log2l](../../c-runtime-library/reference/log2-log2f-log2l.md)