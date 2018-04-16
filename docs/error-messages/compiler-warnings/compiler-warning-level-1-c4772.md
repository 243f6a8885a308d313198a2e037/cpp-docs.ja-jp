---
title: "コンパイラの警告 (レベル 1) C4772 |Microsoft ドキュメント"
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: error-reference
f1_keywords:
- C4772
dev_langs:
- C++
helpviewer_keywords:
- C4772
ms.assetid: dafe6fd8-9faf-41f5-9d66-a55838742c14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 631cd4f872c7b8912b791417c04f6c6e9e056bdd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4772"></a>コンパイラの警告 (レベル 1) C4772

> \#インポートが不足しているタイプ ライブラリ以外から型を参照'*ありません型*' プレース ホルダーとして使用します。

タイプ ライブラリが参照された、 [#import](../../preprocessor/hash-import-directive-cpp.md)ディレクティブです。 ただし、タイプ ライブラリがで参照されていない別のタイプ ライブラリへの参照を含まれている`#import`です。 この他の .tlb ファイルは、コンパイラによって検出されませんでした。

コンパイラは見つかりませんタイプ ライブラリの異なるディレクトリで使用する場合に注意してください、 [/I (追加インクルード ディレクトリ)](../../build/reference/i-additional-include-directories.md)コンパイラ オプションをこれらのディレクトリを指定します。 コンパイラの異なるディレクトリでタイプ ライブラリを検索する場合は、これらのディレクトリを PATH 環境変数に追加します。

既定では、この警告はエラーとして発行されます。 /W0 で C4772 を抑制することはできません。

## <a name="example"></a>例

これは、C4772 の再現に必要な最初のタイプ ライブラリです。

```IDL
// c4772a.idl
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]
library C4772aLib
{
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c100")]
   enum E_C4772a
   {
      one, two, three
   };
};
```

これは、C4772 の再現に必要な 2 つ目のタイプ ライブラリです。

```IDL
// c4772b.idl
// post-build command: del /f C4772a.tlb
// C4772a.tlb is available when c4772b.tlb is built
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]
library C4772bLib
{
   importlib ("c4772a.tlb");
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]
   struct S_C4772b
   {
      enum E_C4772a e;
   };
};
```

次の例では、C4772 が生成されます。

```cpp
// C4772.cpp
// assumes that C4772a.tlb is not available to the compiler
// #import "C4772a.tlb"
#import "C4772b.tlb"   // C4772 uncomment previous line to resolve
                       // and make sure c4772a.tlb is on disk
```