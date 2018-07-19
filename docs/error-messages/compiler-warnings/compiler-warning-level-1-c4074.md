---
title: コンパイラの警告 (レベル 1) C4074 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4074
dev_langs:
- C++
helpviewer_keywords:
- C4074
ms.assetid: cd510e66-c338-4a86-a4d7-bfa1df9b16c3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9072728660ca78097a1e36e492670a614bb2b2f8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33274704"
---
# <a name="compiler-warning-level-1-c4074"></a>コンパイラの警告 (レベル 1) C4074
初期化子がコンパイラの予約初期化領域に  
  
 指定されているコンパイラ初期化領域[#pragma init_seg](../../preprocessor/init-seg.md)、Microsoft によって予約されています。 この領域内のコードは、C ランタイム ライブラリの初期化の前に実行できます。  
  
 次の例では、C4074 が生成されます。  
  
```  
// C4074.cpp  
// compile with: /W1  
#pragma init_seg( compiler )   // C4074  
  
// try this line to resolve the warning  
// #pragma init_seg(user)  
  
int main() {  
}  
```