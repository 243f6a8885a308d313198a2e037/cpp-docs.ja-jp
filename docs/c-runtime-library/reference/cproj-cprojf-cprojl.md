---
title: cproj、cprojf、cprojl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- cproj
- cprojf
- cprojl
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
- cproj
- cprojf
- cprojl
- complex/cproj
- complex/cprojf
- complex/cprojl
dev_langs:
- C++
helpviewer_keywords:
- cproj function
- cprojf function
- cprojl function
ms.assetid: 32b49623-13bf-4cae-802e-7912d75030fe
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cb631eb7f5ce18b8ca824fc8a15e9dd5d6b584f1
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="cproj-cprojf-cprojl"></a>cproj、cprojf、cprojl

リーマン球面上への複素数の射影を取得します。

## <a name="syntax"></a>構文

```C
_Dcomplex cproj(
   _Dcomplex z
);
_Fcomplex cproj(
   _Fcomplex z
);  // C++ only
_Lcomplex cproj(
   _Lcomplex z
);  // C++ only
_Fcomplex cprojf(
   _Fcomplex z
);
_Lcomplex cprojl(
   _Lcomplex z
);
```

### <a name="parameters"></a>パラメーター

*z*<br/>
複素数。

## <a name="return-value"></a>戻り値

投影*z* Reimann 球のです。

## <a name="remarks"></a>コメント

C++ では、オーバー ロードできるよう、ためのオーバー ロードを呼び出すことができます**cproj**を受け取り、返します **_Fcomplex**と **_Lcomplex**値。 C プログラムでは、 **cproj**常に受け取りを返す、 **_Dcomplex**値。

## <a name="requirements"></a>要件

|ルーチン|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|**cproj**、 **cprojf**、 **cprojl**|\<complex.h>|\<ccomplex>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[norm、normf、norml](norm-normf-norml1.md)<br/>
[creal、crealf、creall](creal-crealf-creall.md)<br/>
[conj、conjf、conjl](conj-conjf-conjl.md)<br/>
[cimag、cimagf、cimagl](cimag-cimagf-cimagl.md)<br/>
[carg、cargf、cargl](carg-cargf-cargl.md)<br/>
[cabs、cabsf、cabsl](cabs-cabsf-cabsl.md)<br/>
