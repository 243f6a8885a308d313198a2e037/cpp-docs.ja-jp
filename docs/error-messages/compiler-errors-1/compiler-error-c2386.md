---
title: "コンパイラ エラー C2386 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2386
dev_langs: C++
helpviewer_keywords: C2386
ms.assetid: aaaa1284-34a0-4da2-8547-9fcbb559dae0
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a0a765e837e49207ee64762b890472f92f41e490
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2386"></a>コンパイラ エラー C2386
'symbol' : この名前のシンボルがカレント スコープ内に既に存在します。  
  
 名前空間エイリアスを作成しようとしましたが、選択んだ名前が既に存在します。  
  
 次の例では C2386 が生成されます。  
  
```  
// C2386.cpp  
namespace A {  
   int k;  
}  
  
int i;  
namespace i = A;   // C2386, i already exists  
```