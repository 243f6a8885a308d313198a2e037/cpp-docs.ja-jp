---
title: コンパイラの警告 (レベル 3) C4023 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4023
dev_langs:
- C++
helpviewer_keywords:
- C4023
ms.assetid: 615d5374-d7c1-42eb-acfd-917c053270c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 213d72e39575b447787c3e0ead7910baedc8e815
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33289998"
---
# <a name="compiler-warning-level-3-c4023"></a>コンパイラの警告 (レベル 3) C4023
'symbol' : _based ポインターがプロトタイプ宣言されていない関数へ渡されます : パラメーター番号  
  
 プロトタイプ宣言されていない関数に _based ポインターを渡すと、ポインターが正規化され、予期しない結果になります。  
  
 _based ポインターを渡されるプロトタイプ関数を使用すると、この警告が解決することがあります。