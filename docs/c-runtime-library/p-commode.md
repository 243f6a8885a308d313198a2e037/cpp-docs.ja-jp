---
title: __p__commode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __p__commode
apilocation:
- msvcr110.dll
- msvcrt.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __p__commode
dev_langs:
- C++
helpviewer_keywords:
- __p__commode
ms.assetid: 4380acb8-e3e4-409c-a60f-6205ac5189ce
caps.latest.revision: 2
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 1ae9ef3c73cb3b88eb33869fbbfac090acac1921
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="pcommode"></a>__p__commode
ファイルの入出力操作に対して既定の*ファイル コミット モード*を指定する `_commode` グローバル変数を指し示します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
int * __p__commode(  
   );  
```  
  
## <a name="return-value"></a>戻り値  
 `_commode` グローバル変数へのポインター。  
  
## <a name="remarks"></a>コメント  
 `__p__commode` 関数は内部使用専用であり、ユーザー コードから呼び出すことはできません。  
  
 ファイル コミット モードは重要なデータがディスクに書き込まれるタイミングを指定します。 詳細については、「[fflush](../c-runtime-library/reference/fflush.md)」をご覧ください。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|__p\__commode|internal.h|