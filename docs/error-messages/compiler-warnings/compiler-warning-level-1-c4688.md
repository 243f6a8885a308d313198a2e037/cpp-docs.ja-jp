---
title: "コンパイラの警告 (レベル 1) C4688 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4688
dev_langs:
- C++
helpviewer_keywords:
- C4688
ms.assetid: a027df3c-b2b8-4c49-8539-c2bc42db74e8
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: b8ab911eb5adb28d1fb31db58931ee8449645dba
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4688"></a>コンパイラの警告 (レベル 1) C4688
'constraint': 制約リストはアセンブリ プライベート型 'type' を含んでいます  
  
 制約リストにアセンブリ プライベート型があります。つまり、型にアセンブリの外部からアクセスする場合は、このリストを使用できません。 詳細については、「[ジェネリック](../../windows/generics-cpp-component-extensions.md)」を参照してください。  
  
## <a name="example"></a>例  
 次の例では C4688 警告が生成されます。  
  
```  
// C4688.cpp  
// compile with: /clr /c /W1  
ref struct A {};   // private type  
public ref struct B {};  
  
// Delete the following 3 lines to resolve.  
generic <class T>   
where T : A   // C4688  
public ref struct M {};  
  
generic <class T>   
where T : B  
public ref struct N {};  
```
