---
title: コンパイラの警告 (レベル 4) C4339 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4339
dev_langs:
- C++
helpviewer_keywords:
- C4339
ms.assetid: 5b83353d-7777-4afb-8476-3c368349028c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b94d6a059c1c04eeae04bf917a84836c0354197e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33295796"
---
# <a name="compiler-warning-level-4-c4339"></a>コンパイラの警告 (レベル 4) C4339
'type': 未定義の型の使用が WinRT または CLR meta-data で検出されました。この型を使用するとランタイム例外が起きる可能性があります。  
  
 Windows ランタイムまたは共通言語ランタイム用にコンパイルされたコードで、型が定義されていませんでした。 ランタイム例外の可能性を回避するために、型を定義します。  
  
 既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。  
  
 次の例では C4339 が生成され、その修正方法が示されています。  
  
```  
// C4339.cpp  
// compile with: /W4 /clr /c  
// C4339 expected  
#pragma warning(default : 4339)  
  
// Delete the following line to resolve.  
class A;  
  
// Uncomment the following line to resolve.  
// class A{};  
  
class X {  
public:  
   X() {}  
  
   virtual A *mf() {  
      return 0;  
   }  
};  
  
X * f() {  
   return new X();  
}  
```