---
title: "___mb_cur_max_func、___mb_cur_max_l_func、__p___mb_cur_max、__mb_cur_max | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- ___mb_cur_max_l_func
- __p___mb_cur_max
- ___mb_cur_max_func
- __mb_cur_max
apilocation:
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
- msvcr100.dll
- msvcrt.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- ___mb_cur_max_func
- ___mb_cur_max_l_func
- __p___mb_cur_max
- __mb_cur_max
dev_langs:
- C++
helpviewer_keywords:
- __mb_cur_max
- ___mb_cur_max_func
- ___mb_cur_max_l_func
- __p___mb_cur_max
ms.assetid: 60d36108-1ca7-45a6-8ce7-68a91f13e3a1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a9acb5dccac11d132eae74eb89a4b2e4a6bf8fab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="mbcurmaxfunc-mbcurmaxlfunc-pmbcurmax-mbcurmax"></a>___mb_cur_max_func、___mb_cur_max_l_func、__p___mb_cur_max、__mb_cur_max
内部 CRT 関数。 現在または指定されたロケールのマルチバイト文字の最大バイト数を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
int ___mb_cur_max_func(void);  
int ___mb_cur_max_l_func(_locale_t locale);  
int * __p___mb_cur_max(void);  
#define __mb_cur_max (___mb_cur_max_func())  
```  
  
#### <a name="parameters"></a>パラメーター  
 ロケール  
 結果の取得元のロケール構造。 この値が null の場合は、現在のスレッド ロケールが使用されます。  
  
## <a name="return-value"></a>戻り値  
 現在のスレッド ロケールまたは指定されたロケールのマルチバイト文字の最大バイト数。  
  
## <a name="remarks"></a>コメント  
 これは、スレッド ローカル ストレージから [MB_CUR_MAX](../c-runtime-library/mb-cur-max.md) マクロの現在の値を取得するために CRT で使用される内部関数です。 移植性を考慮して、コードでは `MB_CUR_MAX` マクロを使用することをお勧めします。  
  
 `__mb_cur_max` マクロは、`___mb_cur_max_func()` 関数を呼び出す便利な方法です。 `__p___mb_cur_max` 関数は、Visual C++ 5.0 以前のバージョンとの互換性のために定義されています。  
  
 内部 CRT 関数は実装固有であり、各リリースでの変更の対象です。 コード内では使用しないことをお勧めします。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`___mb_cur_max_func`、`___mb_cur_max_l_func`、`__p___mb_cur_max`|\<ctype.h>、\<stdlib.h>|  
  
## <a name="see-also"></a>参照  
 [MB_CUR_MAX](../c-runtime-library/mb-cur-max.md)