---
title: コンパイラの警告 (レベル 1) C4086 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4086
dev_langs:
- C++
helpviewer_keywords:
- C4086
ms.assetid: 9248831b-22bf-47af-8684-bfadb17e94fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 541543cde39821a938290d1a8f5ce2063c8fc997
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275211"
---
# <a name="compiler-warning-level-1-c4086"></a>コンパイラの警告 (レベル 1) C4086
プラグマに '1'、'2'、'4'、'8'、'16' のいずれかのパラメーターが必要です。  
  
 プラグマのパラメーターに必要な値 (1、2、4、8、または 16) がありません。  
  
## <a name="example"></a>例  
  
```  
// C4086.cpp  
// compile with: /W1 /LD  
#pragma pack( 3 ) // C4086  
```