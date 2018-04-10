---
title: -arch (ARM) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: 4f1406ff-f174-487c-a126-8ab06cf447c1
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 468401bcee2d627149175d022c420b8bb905c4ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="arch-arm"></a>/arch (ARM)
ARM でのコード生成のアーキテクチャを指定します。 関連項目[/arch (x86)](../../build/reference/arch-x86.md)と[/arch (x64)](../../build/reference/arch-x64.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
/arch:[ARMv7VE|VFPv4]  
```  
  
## <a name="arguments"></a>引数  
 **/arch:ARMv7VE**  
 ARMv7VE 仮想化拡張命令の使用を有効にします。  
  
 **/arch:VFPv4**  
 ARM VFPv4 命令の使用を有効にします。 このオプションを指定しない場合は、VFPv3 が既定値です。  
  
## <a name="remarks"></a>コメント  
 `_M_ARM_FP`マクロ (ARM のみ) を示します。 存在する場合、 **/arch**コンパイラ オプションを使用します。 詳細については、「 [Predefined Macros](../../preprocessor/predefined-macros.md)」を参照してください。  
  
 使用すると[/clr](../../build/reference/clr-common-language-runtime-compilation.md)をコンパイルする**/arch**マネージ関数のコード生成に影響を与えません。 **/arch**だけでネイティブ関数の生成のコードに影響します。  
  
### <a name="to-set-the-archarmv7ve-or-archvfpv4-compiler-option-in-visual-studio"></a>Visual Studio で、/arch:ARMv7VE または/arch:VFPv4 コンパイラ オプションを設定するには  
  
1.  開く、**プロパティ ページ**プロジェクトのダイアログ ボックス。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  選択、 **C/C++**フォルダーです。  
  
3.  選択、**コマンドライン**プロパティ ページ。  
  
4.  **追加オプション**ボックスで、追加`/arch:ARMv7VE`または`/arch:VFPv4`です。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [/arch (最小限の CPU アーキテクチャ)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)