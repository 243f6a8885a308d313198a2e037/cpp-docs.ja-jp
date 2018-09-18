---
title: コンパイラ エラー C2850 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2850
dev_langs:
- C++
helpviewer_keywords:
- C2850
ms.assetid: f3efe86c-4168-4e76-a133-3f8314c69f51
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 89e3cc7065ed5a0a91ad77ea5a6c44b38622b8e3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057887"
---
# <a name="compiler-error-c2850"></a>コンパイラ エラー C2850

'construct': ファイルのスコープにのみ使用できます入れ子になったコンストラクトではありません。

一部のプラグマなどの構造は、グローバル スコープでのみ表示できます。

次の例では、C2850 が生成されます。

```
// C2850.cpp
// compile with: /c /Yc
// try the following line instead
// #pragma hdrstop
namespace X {
   #pragma hdrstop   // C2850
};
```