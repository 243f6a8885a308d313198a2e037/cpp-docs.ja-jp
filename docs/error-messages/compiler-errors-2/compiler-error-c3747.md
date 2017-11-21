---
title: "コンパイラ エラー C3747 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3747
dev_langs: C++
helpviewer_keywords: C3747
ms.assetid: a9a4be67-5d9c-4dcc-9ae9-baae46cbecde
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f68363a0d3a6c5b9354f89993fd658cf227edd0f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3747"></a>コンパイラ エラー C3747
既定値の型パラメーターがありません: パラメーター param  
  
 ジェネリックまたはテンプレート パラメーターに既定値をパラメーター リスト内後既定値がないパラメーターであることはできません。  
  
 次の例では、C3747 が生成されます。  
  
```  
// C3747.cpp  
template <class T1 = int, class T2>   // C3747  
struct MyStruct {};  
```  
  
 考えられる解決策:  
  
```  
// C3747b.cpp  
// compile with: /c  
template <class T1, class T2 = int>  
struct MyStruct {};  
```