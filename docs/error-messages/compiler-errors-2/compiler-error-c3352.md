---
title: コンパイラ エラー C3352 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3352
dev_langs:
- C++
helpviewer_keywords:
- C3352
ms.assetid: f233bed7-474e-425f-aad2-7801578169d4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c045df51271c761ab61a3d5ec7d97634858909a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093847"
---
# <a name="compiler-error-c3352"></a>コンパイラ エラー C3352

'function': 指定された関数がデリゲート型 'type' と一致しません

パラメーターのリストが`function`とデリゲートが一致していません。

詳細については、次を参照してください。[デリゲート (C++ コンポーネント拡張)](../../windows/delegate-cpp-component-extensions.md)します。

次の例では、C3352 が生成されます。

```
// C3352.cpp
// compile with: /clr
delegate int D( int, int );
ref class C {
public:
   int mf( int ) {
      return 1;
   }

   // Uncomment the following line to resolve.
   // int mf(int, int) { return 1; }
};

int main() {
   C^ pC = gcnew C;
   System::Delegate^ pD = gcnew D( pC, &C::mf );   // C3352
}
```
