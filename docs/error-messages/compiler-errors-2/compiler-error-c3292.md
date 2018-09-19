---
title: コンパイラ エラー C3292 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3292
dev_langs:
- C++
helpviewer_keywords:
- C3292
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8fc5f89978a7ecaff526fa05ca7a47494aada987
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112461"
---
# <a name="compiler-error-c3292"></a>コンパイラ エラー C3292

cli 名前空間はを再度開くことはできません

コード内で cli 名前空間を宣言することはできません。  詳細については、次を参照してください。[プラットフォーム、既定では、および cli 名前空間](../../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では C3292 が生成されます。

```
// C3292.cpp
// compile with: /clr /c
namespace cli {};   // C3292
```