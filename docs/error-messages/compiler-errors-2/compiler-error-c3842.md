---
title: コンパイラ エラー C3842 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3842
dev_langs:
- C++
helpviewer_keywords:
- C3842
ms.assetid: 41a1a44a-c618-40a2-8d26-7da27d14095d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8db69ce3af28ed5878c43775b2c33542e5c817d6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055527"
---
# <a name="compiler-error-c3842"></a>コンパイラ エラー C3842

WinRT またはマネージド型のメンバー関数に対する 'function': 'const' および 'volatile' 修飾子はサポートされていません

[const](../../cpp/const-cpp.md)と[揮発性](../../cpp/volatile-cpp.md)は Windows ランタイムまたはマネージ型のメンバー関数ではサポートされていません。

次の例では C3842 が生成されます。

```
// C3842a.cpp
// compile with: /clr /c
public ref struct A {
   void f() const {}   // C3842
   void f() volatile {}   // C3842

   void f() {}
};
```