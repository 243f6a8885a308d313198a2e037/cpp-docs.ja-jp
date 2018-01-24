---
title: "-FU (Name Forced #using ファイルの using) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.ForcedUsingFiles
- /FU
- VC.Project.VCNMakeTool.ForcedUsingAssemblies
dev_langs: C++
helpviewer_keywords:
- -FU compiler option [C++]
- FU compiler option [C++]
- /FU compiler option [C++]
ms.assetid: 698f8603-457f-435a-baff-5ac9243d6ca1
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 17b62859aaf0c9dc6b3313fbb726602b5b83a82c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fu-name-forced-using-file"></a>/FU (強制 #using ファイルの名前の指定)
ファイル名を渡す代わりとして使用できるコンパイラ オプション[#using ディレクティブ](../../preprocessor/hash-using-directive-cpp.md)ソース コードにします。  
  
## <a name="syntax"></a>構文  
  
```  
/FU file  
```  
  
## <a name="arguments"></a>引数  
 `file`  
 このコンパイルで参照するメタデータ ファイルを指定します。  
  
## <a name="remarks"></a>コメント  
 /FU スイッチは、1 つのファイル名を取得します。 複数のファイルを指定するには、1 つずつ/FU を使用します。  
  
 使用している場合[!INCLUDE[cppcli](../../build/reference/includes/cppcli_md.md)]を使用するメタデータを参照していると、[フレンド アセンブリ](../../dotnet/friend-assemblies-cpp.md)機能を使うことはできません**/FU**です。 使用してコード内のメタデータを参照する必要があります`#using`— と共に、`[as friend]`属性。 フレンド アセンブリでサポートされていない[!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] ([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)])。  
  
 アセンブリまたは共通言語ランタイム (CLR) のモジュールを作成する方法については、次を参照してください。 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)です。 内でビルドする方法については[!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)]を参照してください[アプリとライブラリのビルド](../../cppcx/building-apps-and-libraries-c-cx.md)です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  選択、 **C/C++**フォルダーです。  
  
3.  選択、**詳細**プロパティ ページ。  
  
4.  変更、 **Force #using**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedUsingFiles%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [出力ファイル (/F) オプション](../../build/reference/output-file-f-options.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)