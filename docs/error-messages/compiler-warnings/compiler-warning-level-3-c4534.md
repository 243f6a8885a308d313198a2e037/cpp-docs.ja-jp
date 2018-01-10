---
title: "コンパイラの警告 (レベル 3) C4534 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: c4534
dev_langs: C++
helpviewer_keywords: C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6d9ea2cc6fb15edf61610e96a728e985b78be468
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4534"></a>コンパイラの警告 (レベル 3) C4534
'constructor' には、クラス 'class'、既定の引数のための既定のコンス トラクターはできません。  
  
 アンマネージ クラスは、既定値を持つパラメーターを持つコンス トラクターを持つことができ、コンパイラはこれを既定のコンス トラクターとして使用されます。 マークされたクラス、`value`キーワードは、コンス トラクターは使用既定値でそのパラメーターの既定のコンス トラクターとして。  
  
 詳細については、次を参照してください。[クラスと構造体](../../windows/classes-and-structs-cpp-component-extensions.md)です。  
  
 次の例では、C4534 が生成されます。  
  
```  
// C4534.cpp  
// compile with: /W3 /clr /WX  
value class MyClass {  
public:  
   int ii;  
   MyClass(int i = 9) {   // C4534, will not be the default constructor  
      i++;  
   }  
};  
  
int main() {  
   MyClass ^ xx = gcnew MyClass;  
   xx->ii = 0;  
}  
```