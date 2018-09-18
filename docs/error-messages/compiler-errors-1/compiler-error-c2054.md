---
title: コンパイラ エラー C2054 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2054
dev_langs:
- C++
helpviewer_keywords:
- C2054
ms.assetid: 37f7c612-0d7d-4728-9e67-ac4160555f48
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5fc936bf6c42144a55bc6d84a8434959383e7e9f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46071433"
---
# <a name="compiler-error-c2054"></a>コンパイラ エラー C2054

予想 ' (' 'identifier' を実行するには

関数識別子は、末尾のかっこを必要とするコンテキストで使用されます。

このエラーは、複雑な初期化の等号 (=) を省略することで発生することができます。

次の例では、C2054 が生成されます。

```
// C2054.c
int array1[] { 1, 2, 3 };   // C2054, missing =
```

考えられる解決方法:

```
// C2054b.c
int main() {
   int array2[] = { 1, 2, 3 };
}
```