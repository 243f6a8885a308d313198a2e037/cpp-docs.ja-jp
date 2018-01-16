---
title: "-bigobj (内のセクションの増加数です。Obj ファイル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /bigobj
dev_langs: C++
helpviewer_keywords:
- -bigobj compiler option [C++]
- /bigobj compiler option [C++]
- bigobj compiler option [C++]
ms.assetid: ba94d602-4015-4a8d-86ec-49241ab74c12
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 384ec0de9e5cb1b3172b980bf7f412abe759ff91
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="bigobj-increase-number-of-sections-in-obj-file"></a>/bigobj (.obj ファイル内のセクションの数を増やす)
**/bigobj**オブジェクト ファイルが含まれているセクションの数を増やします。  
  
## <a name="syntax"></a>構文  
  
```  
/bigobj  
```  
  
## <a name="remarks"></a>コメント  
 既定では、オブジェクト ファイルはアドレス指定可能なセクションを最大 65,536 (2^16) 保持できます。 これは、どのターゲット プラットフォームを指定したかにかかわらない場合です。 **/bigobj** 4,294,967,296 するアドレスの量が増加 (2 ^32)。  
  
 ほとんどのモジュールでは、65,536 を超えるセクションを格納する .obj ファイルを生成することはありません。 しかし、マシンによって生成されるコード、またはテンプレート ライブラリを多用するコードでは、より多くのセクションを保持できる .obj ファイルを必要とする可能性があります。 **/bigobj**コンピューターによって生成された XAML コードに多数のヘッダーが含まれているために、Windows ストア プロジェクトでは既定で有効にします。 Windows ストア アプリのプロジェクトでこのオプションを無効にすると、コンパイラ エラー C1128 が発生する可能性が高くなります。  
  
 Visual C 2005 より前に付属していたリンカーを使って生成された .obj ファイルを読み取ることができません**/bigobj**です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  **[コマンド ライン]** プロパティ ページをクリックします。  
  
4.  **[追加のオプション]** ボックスにコンパイラ オプションを入力します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)