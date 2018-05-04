---
title: UWP アプリ、Windows ランタイム、および C ランタイム | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: 356d6d8d-76ee-4181-9ad0-6f24b2fede38
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e9e6053cdcd7797319379e1e5e7290bcff373b6f
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="uwp-apps-the-windows-runtime-and-the-c-run-time"></a>UWP アプリ、Windows ランタイム、および C ランタイム

ユニバーサル Windows プラットフォーム (UWP) アプリは、[!INCLUDE[win8](../build/reference/includes/win8_md.md)] の Windows ランタイムで実行されるプログラムです。 Windows ランタイムは、UWP アプリで使用できる関数、変数、リソースを制御する信頼できる環境です。 ただし、Windows ランタイムの仕様による制限のため、ほとんどの C ランタイム ライブラリ (CRT) 機能は UWP アプリでは使用できません。

Windows ランタイムは次の CRT 機能をサポートしていません。

- サポートされない機能に関連したほとんどの CRT 関数。

   たとえば、UWP アプリでは、**exec** および **spawn** ファミリのルーチンを使用してプロセスを作成することはできません。

   ある CRT 関数が UWP アプリでサポートされていない場合、そのことが参照資料に記載されています。

- ほとんどのマルチバイト文字関数およびマルチバイト文字列関数。

   ただし、Unicode と ANSI の両方のテキストはサポートされています。

- コンソール アプリとコマンド ライン引数。

   ただし、従来のデスクトップ アプリではコンソールとコマンド ライン引数がサポートされます。

- 環境変数。

- 現在の作業ディレクトリという概念。

- [/MT](../build/reference/md-mt-ld-use-run-time-library.md) または `/MTd` コンパイラ オプションを使用して CRT に静的にリンクされて作成された UWP アプリおよび DLL。

   マルチスレッドおよび静的バージョンの CRT を使用するアプリがこれに当たります。

- [/MDd](../build/reference/md-mt-ld-use-run-time-library.md) コンパイラ オプションを使用して作成されたアプリ。

   デバッグ、マルチスレッド、および DLL 対応バージョンの CRT を使用するアプリがこれに当たります。 このようなアプリは Windows ランタイムではサポートされません。

UWP アプリで使用できない CRT 関数と使用できる代替関数の詳細な一覧については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="see-also"></a>参照

[互換性](../c-runtime-library/compatibility.md)<br/>
[Windows ランタイムのサポートされていない CRT 関数](../c-runtime-library/windows-runtime-unsupported-crt-functions.md)<br/>
[カテゴリ別ユニバーサル C ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)<br/>
