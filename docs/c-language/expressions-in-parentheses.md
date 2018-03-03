---
title: "かっこで囲んだ式 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- parentheses
- expression evaluation, evaluation order
- expressions [C++], evaluating
- parentheses, expressions
ms.assetid: b8636147-6982-408c-9e64-29e40678ee43
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c09209a323a06f883a54e7ecaec17c55a3bc6205
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="expressions-in-parentheses"></a>かっこで囲んだ式
オペランドはかっこで囲むことができ、囲まれた式の型と値は変わりません。 たとえば、次の式では、  
  
```  
( 10 + 5 ) / 5  
```  
  
 `10 + 5` を囲むかっこは、`10 + 5` の値を最初に評価し、それが除算 (**/**) 演算子の左側のオペランドになることを意味します。 `( 10 + 5 ) / 5` の結果は 3 です。 かっこがない場合、`10 + 5 / 5` は 11 に評価されます。  
  
 かっこはオペランドが式内でグループ化される方法に影響を与えますが、すべての場合に特定の評価の順序を保証できません。 たとえば次の式では、かっこによっても、左から右へのグループ化によっても、`i` の値が部分式のどちらに含まれるかは保証されません。  
  
```  
( i++ +1 ) * ( 2 + i )  
```  
  
 コンパイラは、乗算の 2 つの辺を任意の順序で自由に評価します。 `i` の初期値がゼロの場合、式全体が次の 2 つのステートメントのどちらかとして評価されます。  
  
```  
( 0 + 1 + 1 ) * ( 2 + 1 )   
( 0 + 1 + 1 ) * ( 2 + 0 )  
```  
  
 副作用の結果として発生する例外については、「[副作用](../c-language/side-effects.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [C 一次式](../c-language/c-primary-expressions.md)