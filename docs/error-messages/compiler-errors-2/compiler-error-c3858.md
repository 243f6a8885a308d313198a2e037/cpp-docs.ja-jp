---
title: コンパイラ エラー C3858 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3858
dev_langs:
- C++
helpviewer_keywords:
- C3858
ms.assetid: 46e178d5-a55f-4ac6-a9dc-561fbcba5c1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19895f08f06dbbce998350c89a7accb9251b9588
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33268945"
---
# <a name="compiler-error-c3858"></a>コンパイラ エラー C3858
'type': 現在のスコープでは再宣言することはできません  
  
 型は、同じスコープで 2 回宣言することはできません。  
  
 次の例では、C3858 が生成されます。  
  
```  
// C3858.cpp  
// compile with: /LD  
template <class T>  
struct Outer  
{  
   struct Inner;  
};  
  
template <class T>  
struct Outer<T>::Inner;   // C3858  
// try the following line instead  
// struct Outer<T>::Inner{};  
```