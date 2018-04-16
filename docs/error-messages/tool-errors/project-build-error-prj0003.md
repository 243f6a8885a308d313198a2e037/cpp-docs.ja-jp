---
title: "プロジェクト ビルド エラー PRJ0003 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0003
dev_langs:
- C++
helpviewer_keywords:
- PRJ0003
ms.assetid: fc5a84bb-c6d3-41d6-8dd6-475455820778
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bcf80eb4d45fe1ae163772b96339c123996ae377
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="project-build-error-prj0003"></a>プロジェクト ビルド エラー PRJ0003  
  
> エラーの生成 '*コマンドライン*' です。  
  
*コマンドライン*コマンドの形式で入力から、**プロパティ ページ** ダイアログ ボックスに、エラー コードが返されますが表示されます、**出力**ウィンドウです。  

このエラーの考えられる原因は次のとおりです。  
  
-   プロジェクトは、ATL サーバーによって異なります。 Visual Studio 2008 以降では、ATL サーバーは不要になった、Visual Studio の一部として含めるが、CodePlex での共有ソース プロジェクトとしてリリースされています。 ATL Server のソース コードとツールをダウンロードするには[ATL サーバー ライブラリとツール](http://go.microsoft.com/fwlink/p/?linkid=81979)です。  
  
-   リソースが不足します。 これを解決するのには、一部のアプリケーションを閉じます。  
  
-   セキュリティ特権が不十分です。 セキュリティのための十分な特権があることを確認します。  
  
-   指定された実行可能パス**vc++ ディレクトリ**実行しようとしているツールのパスを含めないでください。 詳細については、次を参照してください[のプロジェクト プロパティの操作。](../../ide/working-with-project-properties.md)  
  
-   メイクファイル プロジェクトの場合は、いずれかで実行するコマンドがない**ビルド コマンドライン**または**リビルド コマンドライン**です。  
  
## <a name="see-also"></a>参照  
 [プロジェクト ビルド エラーと警告 (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)