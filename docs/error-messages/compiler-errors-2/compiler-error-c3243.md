---
title: コンパイラ エラー C3243
ms.date: 11/04/2016
f1_keywords:
- C3243
helpviewer_keywords:
- C3243
ms.assetid: 35d8ad1a-377d-47df-be9d-c55eea23340f
ms.openlocfilehash: 1fd0cdf44cb820882cdcda3728b664321f730d5c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460038"
---
# <a name="compiler-error-c3243"></a>コンパイラ エラー C3243

どのオーバーロード関数も 'interface' によって導入されていません

指定されたインターフェイスにはないメンバーを [明示的にオーバーライド](../../cpp/explicit-overrides-cpp.md) しようとしました。

次の例では C3243 が生成されます。

```
// C3243.cpp
#pragma warning(disable:4199)
__interface IX14A {
   void g();
};

__interface IX14B {
   void f();
   void f(int);
};

class CX14 : public IX14A, public IX14B {
public:
   void IX14A::g();
   void IX14B::f();
   void IX14B::f(int);
};

void CX14::IX14A::f()   // C3243 occurs here
{
}
```