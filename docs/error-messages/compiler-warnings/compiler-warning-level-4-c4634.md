---
title: コンパイラの警告 (レベル 4) C4634
ms.date: 11/04/2016
f1_keywords:
- C4634
helpviewer_keywords:
- C4634
ms.assetid: 3e3496ce-2ac7-43d0-a48a-f514c950e81d
ms.openlocfilehash: a26356dd32f1513eadf4ef2b82175cf71aed13a4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536670"
---
# <a name="compiler-warning-level-4-c4634"></a>コンパイラの警告 (レベル 4) C4634

XML ドキュメント コメント: 適用できません: 理由

XML ドキュメントのタグは、すべての C++ コンストラクトに適用できません。  たとえば、名前空間またはテンプレートにドキュメント コメントを追加できません。

詳細については、「 [XML Documentation](../../ide/xml-documentation-visual-cpp.md)」を参照してください。

## <a name="example"></a>例

次の例では C4634 警告が生成されます。

```
// C4634.cpp
// compile with: /W4 /doc /c
/// This is a namespace.   // C4634
namespace hello {
   class MyClass  {};
};
```

## <a name="example"></a>例

次の例では C4634 警告が生成されます。

```
// C4634_b.cpp
// compile with: /W4 /doc /c
/// This is a template.   // C4634
template <class T>
class MyClass  {};
```