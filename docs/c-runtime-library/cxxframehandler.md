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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 9798d46172aac730abaebe8ee2a9c4015422655c
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

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
