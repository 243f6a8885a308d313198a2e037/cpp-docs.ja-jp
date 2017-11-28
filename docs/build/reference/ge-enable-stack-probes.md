---
title: "-Ge (スタック プローブの有効化) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /ge
dev_langs: C++
helpviewer_keywords:
- -Ge compiler option [C++]
- enable stack probes
- /Ge compiler option [C++]
- stack, stack probes
- stack probes
- stack checking calls
- Ge compiler option [C++]
ms.assetid: 4b54deae-4e3c-4bfa-95f3-ba23590f7258
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9c826b2f1d77e71d768ec73fb110f115bf7d0cfa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ge-enable-stack-probes"></a>/Ge (スタック プローブの有効化)
ローカル変数のストレージを必要とされるすべての関数呼び出しに対して、スタック プローブをアクティブにします。  
  
## <a name="syntax"></a>構文  
  
```  
/Ge  
```  
  
## <a name="remarks"></a>コメント  
 このメカニズムは、スタック プローブの機能を書き直してください場合に便利です。 使用することをお勧め[/Gh (有効にする _penter フック関数)](../../build/reference/gh-enable-penter-hook-function.md)スタック プローブの代わりにします。  
  
 [/Gs (コントロール スタック チェック呼び出し)](../../build/reference/gs-control-stack-checking-calls.md)同じ効果があります。  
  
 **/Ge**は非推奨です。 以降、Visual Studio 2005 では、コンパイラを自動的に生成スタック チェックします。 非推奨のコンパイラ オプションの一覧は、次を参照してください。**廃止予定とコンパイラ オプションの削除**で[コンパイラ オプションの一覧をカテゴリ別](../../build/reference/compiler-options-listed-by-category.md)です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  **[コマンド ライン]** プロパティ ページをクリックします。  
  
4.  **[追加のオプション]** ボックスにコンパイラ オプションを入力します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)