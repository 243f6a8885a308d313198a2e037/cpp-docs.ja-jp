---
title: コンパイラ エラー C2943 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2943
dev_langs:
- C++
helpviewer_keywords:
- C2943
ms.assetid: ede6565e-d892-44c0-8eee-c69545f3be2e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6009428a151ee9959766db6213d2447eaf836c2c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33242739"
---
# <a name="compiler-error-c2943"></a>コンパイラ エラー C2943
'class': type-class-id が、テンプレートの型引数として再定義されています  
  
 ジェネリック クラスまたはテンプレート クラスは、シンボルの代わりに、ジェネリック型またはテンプレート型の引数として使用できません。  
  
 次の例では C2943 が生成されます。  
  
```  
// C2943.cpp  
// compile with: /c  
template<class T>  
class List {};  
  
template<class List<int> > class MyList;   // C2943  
template<class T >  class MyList;  
```