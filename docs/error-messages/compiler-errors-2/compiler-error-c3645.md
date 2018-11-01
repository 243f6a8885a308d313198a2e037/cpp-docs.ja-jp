---
title: コンパイラ エラー C3645
ms.date: 11/04/2016
f1_keywords:
- C3645
helpviewer_keywords:
- C3645
ms.assetid: 346da528-ae86-4cd0-9654-f41bee26ac0d
ms.openlocfilehash: f733de6920e00f1f53c87884a7a334e575bceb06
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500335"
---
# <a name="compiler-error-c3645"></a>コンパイラ エラー C3645

'function': _ _clrcall は、ネイティブ コードにコンパイルされた関数では使用できません

関数内でいくつかのキーワードの存在をネイティブにコンパイルする関数となります。

## <a name="example"></a>例

次の例では、C3645 が生成されます。

```
// C3645.cpp
// compile with: /clr /c
#pragma unmanaged
int __clrcall dog() {}   // C3645
```