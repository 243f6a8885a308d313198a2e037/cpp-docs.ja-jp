---
title: "spawn 定数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _P_NOWAIT
- _P_OVERLAY
- _P_WAIT
- _P_DETACH
- _P_NOWAITO
dev_langs:
- C++
helpviewer_keywords:
- _P_OVERLAY constant
- P_DETACH constant
- P_OVERLAY constant
- P_NOWAIT constant
- _P_DETACH constant
- _P_NOWAIT constant
- _P_NOWAITO constant
- P_NOWAITO constant
- spawn constants
- P_WAIT constant
- _P_WAIT constant
ms.assetid: e0533e88-d362-46fc-b53c-5f193226d879
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 891080cb7740285aba2ac7d9f2542b5604c210bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="spawn-constants"></a>spawn 定数
## <a name="syntax"></a>構文  
  
```  
#include <process.h>  
```  
  
## <a name="remarks"></a>コメント  
 `mode` 引数は、生成操作の前とその実行中に、呼び出し元のプロセスによって実行されるアクションを決定します。 `mode` に指定できる値は次のとおりです。  
  
|定数|説明|  
|--------------|-------------|  
|`_P_OVERLAY`|呼び出し元のプロセスを新しいプロセスでオーバーレイし、呼び出し元のプロセスを破棄します (`_exec` 呼び出しと同じ影響)。|  
|`_P_WAIT`|新しいプロセスの実行が完了するまで、呼び出し元のスレッドが中断されます (同期 `_spawn`)。|  
|`_P_NOWAIT`, `_P_NOWAITO`|新しいプロセスと同時に呼び出し元のプロセスを実行し続けます (非同期 `_spawn`)。|  
|`_P_DETACH`|呼び出し元のプロセスの実行を継続します。新しいプロセスは、コンソールまたはキーボードへのアクセスなしでバックグラウンドで実行されます。 新しいプロセスに対する `_cwait` 呼び出しは失敗します。 これは、非同期の `_spawn` です。|  
  
## <a name="see-also"></a>参照  
 [_spawn関数、_wspawn 関数](../c-runtime-library/spawn-wspawn-functions.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)