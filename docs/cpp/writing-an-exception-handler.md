---
title: 例外ハンドラーの記述 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- structured exception handling [C++], exception handlers
- exception handling [C++], exception handlers
ms.assetid: 71473fee-f773-4a34-bf12-82a3af79579c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d8956bb673c756224a886dede90cf23d84c3f20c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050971"
---
# <a name="writing-an-exception-handler"></a>例外ハンドラーの記述

特定のエラーに応答するために例外ハンドラーがよく使用されます。 例外処理構文を使用して、処理する方法が不明な例外をすべて除外できます。 他の例外は、それらの特定の例外を検索するように記述された他のハンドラー (ランタイム ライブラリまたはオペレーティング システム内にあると考えられます) に渡される必要があります。

例外ハンドラーは try-except ステートメントを使用します。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [Try-ステートメントを除く](../cpp/try-except-statement.md)

- [例外フィルターの記述](../cpp/writing-an-exception-filter.md)

- [ソフトウェア例外の発生](../cpp/raising-software-exceptions.md)

- [ハードウェア例外](../cpp/hardware-exceptions.md)

- [例外ハンドラーに関する制約](../cpp/restrictions-on-exception-handlers.md)

## <a name="see-also"></a>関連項目

[構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)