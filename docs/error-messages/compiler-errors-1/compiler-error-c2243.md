---
title: "コンパイラ エラー C2243 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2243
dev_langs:
- C++
helpviewer_keywords:
- C2243
ms.assetid: b90065bb-d251-4ba9-8b4c-280ee13fa9c0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ae7349cce7e824af5621fba121e762aeccffa9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2243"></a>コンパイラ エラー C2243
'type1' から 'type2' の 'conversion type' 変換は存在しますが、アクセスできません。  
  
 アクセス保護 (`protected` または `private`) によって、派生クラスへのポインターから基底クラスへのポインターに変換できませんでした。  
  
 次の例では C2243 が生成されます。  
  
```  
// C2243.cpp  
// compile with: /c  
class B {};  
class D : private B {};  
class E : public B {};  
  
D d;  
B *p = &d;   // C2243  
  
E e;  
B *p2 = &e;  
```  
  
 `protected` または `private` アクセスの基底クラスは、派生クラスのクライアントからはアクセスできません。 これらのレベルのアクセス制御は、基底クラスが、クライアントに表示される必要がない実装の詳細であることを示すために使用されます。 派生クラスのクライアントが派生クラスのポインターから基底クラスへのポインターへの暗黙的な変換にアクセスする必要がある場合は、パブリック派生を使用します。