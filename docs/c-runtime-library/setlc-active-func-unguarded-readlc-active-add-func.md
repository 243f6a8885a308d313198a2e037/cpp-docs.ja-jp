---
title: "___setlc_active_func、___unguarded_readlc_active_add_func | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
apilocation:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- ___unguarded_readlc_active_add_func
- ___setlc_active_func
dev_langs: C++
helpviewer_keywords:
- ___setlc_active_func
- ___unguarded_readlc_active_add_func
ms.assetid: 605ec4e3-81e5-4ece-935a-f434768cc702
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0a1ecc14403a7a08fed73fb10f15dd25051b0a28
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="setlcactivefunc-unguardedreadlcactiveaddfunc"></a>___setlc_active_func、___unguarded_readlc_active_add_func
互換性のために残されています。 バイナリの互換性を維持するためにのみ、これらの内部関数は CRT によってエクスポートされます。  
  
## <a name="syntax"></a>構文  
  
```cpp  
int ___setlc_active_func(void);  
int * ___unguarded_readlc_active_add_func(void);  
```  
  
## <a name="return-value"></a>戻り値  
 戻される値は重要ではありません。  
  
## <a name="remarks"></a>コメント  
 内部 CRT 関数 `___setlc_active_func` および `___unguarded_readlc_active_add_func` は互換性のために残されており、使用されなくなりましたが、バイナリの互換性を維持するために CRT ライブラリによってエクスポートされます。 `___setlc_active_func` の本来の目的は、`setlocale` 関数の現在アクティブな呼び出しの数を返すことでした。 `___unguarded_readlc_active_add_func` の本来の目的は、ロケールをロックしないで参照した関数の数を返すことでした。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`___setlc_active_func`, `___unguarded_readlc_active_add_func`|none|  
  
## <a name="see-also"></a>参照  
 [setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)