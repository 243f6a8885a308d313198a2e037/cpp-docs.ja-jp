---
title: "コンパイラ エラー C3615 |Microsoft ドキュメント"
ms.date: 10/24/2017
ms.technology: cpp-tools
ms.topic: error-reference
f1_keywords: C3615
dev_langs: C++
helpviewer_keywords: C3615
ms.assetid: 5ce96ba9-3d31-49f3-9aa8-24e5cdf6dcfc
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9c2c527c4b32c8338212a703d80ecb38c00b0a9d
ms.sourcegitcommit: 69632887f7a85f4841c49b4c1353d3144927a52c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2017
---
# <a name="compiler-error-c3615"></a>コンパイラ エラー C3615

> constexpr 関数 '*関数*' 定数式で発生することはできません

関数は、*関数*として評価できませんでした`constexpr`コンパイル時にします。 ある`constexpr`、関数がだけ呼び出してその他の`constexpr`関数。

## <a name="example"></a>例

Visual Studio 2017 が正しく、演算の左オペランドを評価する条件付きで正しくないのときに、エラーが発生、`constexpr`コンテキスト。 次のコードは、Visual Studio 2015 ではなく Visual Studio 2017 をコンパイルします。

```cpp
// C3615.cpp
// Compile with: /c

template<int N>
struct myarray
{
    int size() const { return N; }
};

constexpr bool f(const myarray<1> &arr)
{
    return arr.size() == 10 || arr.size() == 11; // C3615 starting in Visual Studio 2017
}
```

この問題を解決するいずれかの宣言、`array::size()`として機能`constexpr`または削除、`constexpr`から修飾子`f`です。