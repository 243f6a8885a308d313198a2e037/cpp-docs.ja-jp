---
title: コンパイラの警告 (レベル 1) C4085 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4085
dev_langs:
- C++
helpviewer_keywords:
- C4085
ms.assetid: 2bc6eb25-058f-4597-b351-fd69587b5170
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f9b8f1cfdb1cb8cc699b71a08afc417d2d1bd87f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33271829"
---
# <a name="compiler-warning-level-1-c4085"></a>コンパイラの警告 (レベル 1) C4085
プラグマに、'on' か 'off' のパラメーターが必要です。  
  
 プラグマには、 **on** または **off** パラメーターが必要です。 このプラグマは無視されます。  
  
 次の例では C4085 が生成されます。  
  
```  
// C4085.cpp  
// compile with: /W1 /LD  
#pragma optimize( "t", maybe )  // C4085  
```