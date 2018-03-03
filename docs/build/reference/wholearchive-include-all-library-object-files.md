---
title: "-WHOLEARCHIVE (すべてのライブラリ オブジェクト ファイルを含める) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: ee92d12f-18af-4602-9683-d6223be62ac9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3499d6583c7d9801aa4c3b12c66196c975b192ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="wholearchive-include-all-library-object-files"></a>/WHOLEARCHIVE (すべてのライブラリ オブジェクト ファイルを含む)
リンクされた実行可能ファイルでのスタティック ライブラリですべてのオブジェクト ファイルを含めるようにリンカーを強制します。  
  
## <a name="syntax"></a>構文  
  
> /WHOLEARCHIVE [:*ライブラリ*]  
  
## <a name="remarks"></a>コメント  
  
/WHOLEARCHIVE オプションでは、リンカーが、指定された静的ライブラリからすべてのオブジェクト ファイルを含めるまたはライブラリが指定されていない場合に、リンクに指定されたすべての静的ライブラリからコマンドを強制します。 複数のライブラリの/WHOLEARCHIVE オプションを指定するには、リンカーのコマンドラインで/WHOLEARCHIVE スイッチが 1 つ以上を使用できます。 既定では、リンカー ファイルが含まれるオブジェクト リンクの出力実行可能ファイル内の他のオブジェクト ファイルで参照されているシンボルをエクスポートする場合にのみです。 /WHOLEARCHIVE オプションは、リンカーのコマンドラインで個別に指定した場合とスタティック ライブラリでアーカイブされたすべてのオブジェクト ファイルを扱うリンカーを使用します。  
  
/WHOLEARCHIVE オプションは、スタティック ライブラリからのすべてのシンボルを再度エクスポートに使用できます。 これにより、すべてのライブラリ コード、リソース、およびメタデータがある含まれる 1 つ以上の静的ライブラリからコンポーネントを作成するときにかどうかを確認できます。 警告 LNK4264 スタティック ライブラリを作成するときに、エクスポート用の Windows ランタイム コンポーネントが含まれていますを表示する場合は、そのライブラリを別のコンポーネントまたはアプリにリンクするときに/WHOLEARCHIVE オプションを使用します。  
  
/WHOLEARCHIVE オプションは、Visual Studio 2015 Update 2 で導入されました。  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>このリンカー オプションを Visual Studio で設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
1.  選択、**コマンドライン**プロパティ ページ**構成プロパティ**、**リンカー**です。  
  
1.  追加する/WHOLEARCHIVE オプション、**追加のオプション**テキスト ボックス。  
  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)