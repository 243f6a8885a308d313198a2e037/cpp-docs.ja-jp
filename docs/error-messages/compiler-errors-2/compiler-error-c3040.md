---
title: コンパイラ エラー C3040
ms.date: 11/04/2016
f1_keywords:
- C3040
helpviewer_keywords:
- C3040
ms.assetid: 29e857ac-74f0-4ec6-becf-9026e38c160e
ms.openlocfilehash: b0bc4956cfc08ae50026827d78136a70b82d568e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474491"
---
# <a name="compiler-error-c3040"></a>コンパイラ エラー C3040

'var': 'reduction' 句の変数の型は、減少演算子 'operator' と互換性がありません

[reduction](../../parallel/openmp/reference/reduction.md) 句内の変数は、減少演算子では使用できません。

次の例では C3040 が生成されます。

```
// C3040.cpp
// compile with: /openmp /c
#include "omp.h"
double d;

int main() {
   #pragma omp parallel reduction(&:d)   // C3040
      ;

   #pragma omp parallel reduction(-:d)  // OK
      ;
}
```