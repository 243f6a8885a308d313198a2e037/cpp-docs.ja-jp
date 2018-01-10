---
title: "signal のアクション定数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SIG_IGN
- SIG_DFL
dev_langs: C++
helpviewer_keywords:
- signal action constants
- SIG_IGN constant
- SIG_DFL constant
ms.assetid: c3cb4f15-d39e-4d9d-84f9-0d33e3eb5993
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 256f11d3f8daa8a00e70e24aa19c31b71413c13c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="signal-action-constants"></a>signal のアクション定数
割り込みシグナルを受信したときに実行されるアクションは、`func` の値によって異なります。  
  
## <a name="syntax"></a>構文  
  
```  
#include <signal.h>  
```  
  
## <a name="remarks"></a>コメント  
 `func` 引数は、関数のアドレス、または SIGNAL.H に定義されている以下のマニフェスト定数のいずれかにする必要があります。  
  
 `SIG_DFL`  
 システム既定の応答を使用します。 呼び出し元のプログラムがストリーム I/O を使用している場合、ランタイム ライブラリによって作成されるバッファーはフラッシュされません。  
  
 `SIG_IGN`  
 割り込みシグナルを無視します。 プロセスの浮動小数点状態が未定義のままになるため、この値を `SIGFPE` に指定しないでください。  
  
 `SIG_SGE`  
 シグナルでエラーが発生したことを示します。  
  
 `SIG_ACK`  
 受信確認を受け取ったことを示します。  
  
 `SIG_ERR`  
 エラーが発生したことを示すシグナルからの戻り値の型。  
  
## <a name="see-also"></a>参照  
 [signal](../c-runtime-library/reference/signal.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)