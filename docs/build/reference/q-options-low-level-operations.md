---
title: "-Q オプション (低水準の操作) |Microsoft ドキュメント"
ms.custom: 
ms.date: 1/23/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /q
dev_langs:
- C++
helpviewer_keywords:
- Q compiler option [C++]
- -Q compiler option [C++]
- /Q compiler option [C++]
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7636b042669c7f7b04d2bc662bcaa2fbe4bdc82a
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2018
---
# <a name="q-options-low-level-operations"></a>/Q オプション (低水準の操作)

使用することができます、 **/Q**次の低水準のコンパイラ操作を行うためにコンパイラ オプション。

- [/Qfast_transcendentals (超越関数高速)](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md): 高速超越関数を生成します。

- [/Qifist (_ftol を抑制する呼び出しません)](../../build/reference/qifist-suppress-ftol.md): 抑制`_ftol`浮動小数点型から整数型への変換が必要な (x86 のみ) の場合。

- [/Qimprecise_fwaits (Try ブロック内部の fwaits の削除)](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): 削除`fwait`内コマンド`try`ブロックします。

- [/Qpar (自動並行化)](../../build/reference/qpar-auto-parallelizer.md): とマークされているループの自動並列化を有効、 [#pragma loop()](../../preprocessor/loop.md)ディレクティブです。

- [/Qpar-report (自動並行化レポート作成レベル)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md): 自動並列化のレベルのレポートを有効にします。

- [/Qsafe_fp_loads](../../build/reference/qsafe-fp-loads.md): 浮動小数点レジスタの読み込みし、メモリと MMX 間を移動登録用に最適化を抑制します。

- [/Qspectre](../../build/reference/qspectre.md): Spectre セキュリティの脆弱性を軽減するために命令を生成します。

- [/Qvec-report (自動ベクター化レポート作成レベル)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md): 自動ベクター化のレベルのレポートを有効にします。

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)  
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)  
