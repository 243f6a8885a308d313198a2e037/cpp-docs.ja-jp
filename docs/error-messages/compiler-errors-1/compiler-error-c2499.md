---
title: コンパイラ エラー C2499 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2499
dev_langs:
- C++
helpviewer_keywords:
- C2499
ms.assetid: b323ff4d-b3c1-4bfd-b052-ae7292d53222
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 27f10cc2f48a72222a6e9a2a7187ba9a1f6fb450
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043951"
---
# <a name="compiler-error-c2499"></a>コンパイラ エラー C2499

'class': クラスは、独自の基本クラスを指定することはできません

基底クラスとして定義するクラスを指定しようとしました。

次の例では、C2499 が生成されます。

```
// C2499.cpp
// compile with: /c
class CMyClass : public CMyClass {};   // C2499
class CMyClass{};   // OK
```