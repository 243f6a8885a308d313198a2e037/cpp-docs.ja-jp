---
title: コンパイラの警告 (レベル 1) C4348 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4348
dev_langs:
- C++
helpviewer_keywords:
- C4348
ms.assetid: 816010eb-6079-48d5-a41b-0fc4d67cfe4c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 86367be7e44e0e50a7c1f8fa309dec50a8399313
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33272456"
---
# <a name="compiler-warning-level-1-c4348"></a>コンパイラの警告 (レベル 1) C4348
'type': 既定のパラメーターの再定義: パラメーター番号  
  
 テンプレート パラメーターは、再定義されました。  
  
 次の例では、C4348 が生成されます。  
  
```  
// C4348.cpp  
// compile with: /LD /W1  
template <class T=int> struct A;   // forward declaration  
  
template <class T=int> struct A { };   
// C4348, redefinition of default parameter  
// try the following line instead  
// template <class T> struct A { };  
```