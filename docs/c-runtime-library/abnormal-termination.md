---
title: _abnormal_termination | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _abnormal_termination
apilocation:
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _abnormal_termination
dev_langs:
- C++
helpviewer_keywords:
- _abnormal_termination
ms.assetid: 952970a4-9586-4c3d-807a-db729448c91c
caps.latest.revision: 2
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 17dbe8079972626439f2706061258265303f5226
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="abnormaltermination"></a>_abnormal_termination
システムが終了ハンドラーの内部リストの実行中に、[try-finally ステートメント](../cpp/try-finally-statement.md)の `__finally` ブロックが入力されているかどうかを示します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
int   _abnormal_termination(  
   );  
```  
  
## <a name="return-value"></a>戻り値  
 システムがスタックを*アンワインド*する場合は `true`、それ以外は `false` です。  
  
## <a name="remarks"></a>コメント  
 これは、アンワインドの例外を管理するために使用される内部関数で、ユーザー コードから呼び出されるものではありません。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|_abnormal_termination|excpt.h|  
  
## <a name="see-also"></a>関連項目  
 [try-finally ステートメント](../cpp/try-finally-statement.md)
