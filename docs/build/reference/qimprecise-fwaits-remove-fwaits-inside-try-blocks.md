---
title: "-Qimprecise_fwaits (Try ブロック内部の fwaits の削除) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /Qimprecise_fwaits
dev_langs:
- C++
helpviewer_keywords:
- -Qimprecise_fwaits compiler option (C++)
- /Qimprecise_fwaits compiler option (C++)
ms.assetid: b1501f21-7e08-4fea-95e8-176ec03a635b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 06c93e60530d870b05c601be4980308feb627b46
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="qimprecisefwaits-remove-fwaits-inside-try-blocks"></a>/Qimprecise_fwaits (try ブロック内部の fwaits を削除する)
削除、`fwait`コマンドの内部`try`を使用するときにブロック、 [/fp: を除く](../../build/reference/fp-specify-floating-point-behavior.md)コンパイラ オプション。  
  
## <a name="syntax"></a>構文  
  
```  
/Qimprecise_fwaits  
```  
  
## <a name="remarks"></a>コメント  
 このオプションには効果がない場合は**/fp: を除く**も指定されていません。 指定する場合、 **/fp: を除く**オプション、コンパイラが挿入されます、`fwait`コマンド内のコードの各行の周り、`try`ブロックします。 これにより、コンパイラは、特定の例外が発生したコード行を識別できます。 **/Qimprecise_fwaits**削除内部`fwait`手順については、周囲の待機時間だけを残して、`try`ブロックします。 これにより、パフォーマンスが向上が、コンパイラはこれを言うをできる`try`ブロックが発生した例外、どの行です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  **[コマンド ライン]** プロパティ ページをクリックします。  
  
4.  **[追加のオプション]** ボックスにコンパイラ オプションを入力します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [/Q オプション (低水準の操作)](../../build/reference/q-options-low-level-operations.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)