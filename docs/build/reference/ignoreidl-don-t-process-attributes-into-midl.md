---
title: "-IGNOREIDL (Don &#39; t プロセス属性を MIDL に挿入) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.IgnoreEmbeddedIDL
- /ignoreidl
dev_langs:
- C++
helpviewer_keywords:
- IGNOREIDL linker option
- -IGNOREIDL linker option
- /IGNOREIDL linker option
ms.assetid: 29514098-6a1c-4317-af2f-1dc268972780
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fe2f1d33f9269380bf0d914d5805cce3b0a92b90
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ignoreidl-don39t-process-attributes-into-midl"></a>/IGNOREIDL (Don &#39; t プロセス属性を MIDL に挿入)
```  
/IGNOREIDL  
```  
  
## <a name="remarks"></a>コメント  
 /IGNOREIDL オプションを指定する[IDL 属性](../../windows/idl-attributes.md)ソース内のコード処理は必要ない .idl ファイルにします。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  クリックして、**埋め込み IDL**プロパティ ページ。  
  
4.  変更、**埋め込み IDL の無視**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreEmbeddedIDL%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)   
 [/IDLOUT (MIDL の出力ファイルの名前を付ける)](../../build/reference/idlout-name-midl-output-files.md)   
 [/TLBOUT (名前です。TLB ファイル)](../../build/reference/tlbout-name-dot-tlb-file.md)   
 [/MIDL (MIDL コマンド ライン オプションの指定)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [属性付きプログラムの作成](../../windows/building-an-attributed-program.md)