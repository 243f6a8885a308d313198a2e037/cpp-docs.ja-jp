---
title: コンパイラ エラー C2694 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2694
dev_langs:
- C++
helpviewer_keywords:
- C2694
ms.assetid: 8dc2cec2-67ae-4e16-8c0c-374425aca8bc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1578b6d7c55272c4b798d0222a1da37f5a749ecc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33234123"
---
# <a name="compiler-error-c2694"></a>コンパイラ エラー C2694
'override': 基底クラスよりも制限の緩い例外の指定に仮想メンバー関数 'base' を持つ仮想関数をオーバーライドします。  
  
 仮想関数がオーバーライドされるが[/Za](../../build/reference/za-ze-disable-language-extensions.md)、制限の緩い関数をオーバーライドする必要がある[例外の指定](../../cpp/exception-specifications-throw-cpp.md)です。  
  
 次の例では、C2694 が生成されます。  
  
```  
// C2694.cpp  
// compile with: /Za /c  
class MyBase {  
public:  
   virtual void f(void) throw(int) {  
   }  
};  
  
class Derived : public MyBase {  
public:  
   void f(void) throw(...) {}   // C2694  
   void f2(void) throw(int) {}   // OK  
};  
```