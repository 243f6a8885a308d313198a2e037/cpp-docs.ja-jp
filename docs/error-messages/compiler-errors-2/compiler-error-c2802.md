---
title: "コンパイラ エラー C2802 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2802
dev_langs: C++
helpviewer_keywords: C2802
ms.assetid: 08b68c0e-9382-40ac-8949-39a7a2749e05
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4aa5d59b7a301efea16589f4561d812545d531bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2802"></a>コンパイラ エラー C2802
静的メンバー 'operator 演算子' は仮パラメーターがありません。  
  
 によって演算子が宣言されている、`static`メンバー関数は、少なくとも 1 つのパラメーターが必要です。  
  
 次の例では、C2802 が生成されます。  
  
```  
// C2802.cpp  
// compile with: /clr /c  
ref class A {  
   static operator+ ();   // C2802  
   static operator+ (A^, A^);   // OK  
};  
```