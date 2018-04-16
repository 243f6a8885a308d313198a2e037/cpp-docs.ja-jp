---
title: "-homeparams (レジスタ パラメーターへのコピー スタック) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /homeparams
dev_langs:
- C++
helpviewer_keywords:
- /homeparams compiler option [C++]
- -homeparams compiler option [C++]
ms.assetid: 51067de4-24f7-436b-b8d9-bc867a7d53aa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fff1b206620ef9efee3fc22c83c8d5317e99b607
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="homeparams-copy-register-parameters-to-stack"></a>/homeparams (レジスタ パラメーターのスタックへのコピー)
関数の実行に入ったときに、レジスタで渡されたパラメーターを、強制的にスタック内のその場所に書き込みます。  
  
## <a name="syntax"></a>構文  
  
```  
/homeparams  
```  
  
## <a name="remarks"></a>コメント  
 これは、 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] コンパイラ (ネイティブ コンパイルおよびクロス コンパイル) だけで使用されるコンパイラ オプションです。  
  
 パラメーターが渡されたときに、[!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]コンパイルでは、呼び出し規約によりパラメーターが必要、レジスタに渡されるパラメーターにもします。 詳細については、次を参照してください。[パラメーターの引き渡し](../../build/parameter-passing.md)です。 ただし、既定では、リリース ビルドで、登録パラメーターは書き込めません、スタックにスペースが既に提供されているパラメーターを。 これにより、プログラムの最適化 (リリース) ビルドのデバッグが困難にします。  
  
 リリース ビルドを使用して**/homeparams**にアプリケーションをデバッグしていることを確認します。 **/homeparams**わけでは、パフォーマンスが劣りますスタック レジスタ パラメーターを読み込む必要があるためです。  
  
 デバッグ ビルドでレジスタに渡されたパラメーターを使用して、スタックが常に格納されます。  
  
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