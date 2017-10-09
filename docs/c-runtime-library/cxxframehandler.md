---
title: __CxxFrameHandler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __CxxFrameHandler
apilocation:
- msvcr110.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- __CxxFrameHandler
dev_langs:
- C++
helpviewer_keywords:
- __CxxFrameHandler
ms.assetid: b79ac97f-425a-42ae-9b91-8beaef935333
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 75f900560f226557bc160bdf74df4467b0c7aa32
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="cxxframehandler"></a>__CxxFrameHandler
内部 CRT 関数。 構造化例外フレームを処理するために CRT によって使用されます。  
  
## <a name="syntax"></a>構文  
  
```cpp  
EXCEPTION_DISPOSITION __CxxFrameHandler(  
      EHExceptionRecord  *pExcept,  
      EHRegistrationNode *pRN,  
      void               *pContext,   
      DispatcherContext  *pDC  
   )  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pExcept`  
 使用可能な `catch` ステートメントに渡される例外レコード。  
  
 `pRN`  
 例外を処理するために使用されるスタック フレームに関する動的な情報。 詳細については、「ehdata.h」を参照してください。  
  
 `pContext`  
 コンテキスト。 (Intel プロセッサでは使用されません)。  
  
 `pDC`  
 関数の開始とスタック フレームに関する追加情報。  
  
## <a name="return-value"></a>戻り値  
 [try-except ステートメント](../cpp/try-except-statement.md)によって使用される*フィルター式*の値のいずれか。  
  
## <a name="remarks"></a>コメント  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|__CxxFrameHandler|excpt.h、ehdata.h|
