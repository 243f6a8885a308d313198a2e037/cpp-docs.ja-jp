---
title: C++ 例外処理
ms.date: 11/04/2016
helpviewer_keywords:
- C++ exception handling
- Visual C++, exception handling
ms.assetid: 65f80b44-9d0f-4d17-b910-07205a5c5c40
ms.openlocfilehash: b4eaab7d5bb352cccc612dd950572464b82b67e8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614748"
---
# <a name="c-exception-handling"></a>C++ 例外処理

C++ 言語は、例外のスローおよびキャッチに関する組み込みサポートを提供します。 C++ でプログラミングするときは、通常、このセクションで説明するように、組み込みの C++ 例外サポートを使用する必要があります。

コードの C++ 例外処理を有効にするには、 [/EHsc](../build/reference/eh-exception-handling-model.md)します。

## <a name="in-this-section"></a>このセクションの内容

C++ 例外処理についてのこの説明には、次の事項が含まれます。

- [Try、catch、および throw ステートメント](../cpp/try-throw-and-catch-statements-cpp.md)

- [catch ブロックの評価方法](../cpp/how-catch-blocks-are-evaluated-cpp.md)

- [例外とスタック アンワインド](../cpp/exceptions-and-stack-unwinding-in-cpp.md)

- [例外の指定](../cpp/exception-specifications-throw-cpp.md)

- [noexcept](../cpp/noexcept-cpp.md)

- [未処理の C++ 例外](../cpp/unhandled-cpp-exceptions.md)

- [C (構造化) と C++ の混合例外](../cpp/mixing-c-structured-and-cpp-exceptions.md)

## <a name="support-for-earlier-mfc-exceptions"></a>MFC の以前のバージョンの例外のサポート

バージョン 4.0 の時点で、MFC は C++ 例外処理メカニズムの使用を開始しました。 新しいコードで C++ 例外処理を使用するように推奨されますが、古いコードが壊れないように、MFC のバージョン 4.0 以降では MFC の以前のバージョンのマクロを保持します。 マクロと新しいメカニズムも組み合わせることができます。 マクロと C++ 例外処理および新しいメカニズムを使用して古いコードを変換する方法の詳細については、記事を参照してください[例外: を使用して MFC マクロと C++ 例外](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)と[例外: MFC からの変換。例外処理マクロ](../mfc/exceptions-converting-from-mfc-exception-macros.md)します。 以前の MFC 例外マクロを使用している場合、これは C++ の例外のキーワードに評価されます。 参照してください[例外: Version 3.0 での例外処理マクロを変更](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)します。

## <a name="see-also"></a>関連項目

[例外処理](../cpp/exception-handling-in-visual-cpp.md)