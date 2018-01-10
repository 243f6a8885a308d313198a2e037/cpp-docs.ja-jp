---
title: "ドット ディレクティブ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, dot directives
- dot directives in NMAKE
ms.assetid: ab35da65-30b6-48b7-87d6-61503d7faf9f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9958b13a6f06b0024ec2d4dd304abfe93b16741e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="dot-directives"></a>ドット ディレクティブ
行の先頭の記述ブロックの外側のドット ディレクティブを指定します。 ドット ディレクティブの先頭にピリオド (です。 )、コロン (:) が続きます。 スペース、タブが許可されています。 ドット ディレクティブの名前は、大文字小文字を区別、大文字です。  
  
|ディレクティブ|目的|  
|---------------|-------------|  
|**.無視する します。**|メイクファイルの末尾に指定されている場所からのコマンドによって返される 0 以外の終了コードを無視します。 既定では、コマンドが 0 以外の終了コードを返す場合 (nmake の) が停止します。 エラー チェックを復元するには、次のように使用します**!。CMDSWITCHES**です。 1 つのコマンドの終了コードを無視するのには、ダッシュ (-) 修飾子を使用します。 ファイル全体の終了コードを無視するのには、使用/しました。|  
|**.貴重:** *ターゲット*|保持*ターゲット*ディスクの場合、それらを更新するコマンドが停止されるためです。 影響を与えませんコマンドは、ファイルを削除して、割り込みを処理する場合。 1 つ以上のスペースまたはタブでターゲットの名前を区切ります。 既定では、(nmake の) は、ビルドが CTRL + C または CTRL + BREAK によって中断された場合に、ターゲットを削除します。 各使用**です。貴重な**メイクファイル全体に適用される複数の仕様は累積します。|  
|**.サイレント。**|メイクファイルの末尾に指定されている場所から、実行されたコマンドの表示を抑制します。 既定では、(nmake の) には、起動したコマンドが表示されます。 エコーを復元するには、次のように使用します**!。CMDSWITCHES**です。 1 つのコマンドのエコーを抑制するのには、使用、  **@** 修飾子です。 ファイル全体のエコーを抑制するのには、使用/%s|  
|**.サフィックス:**`list`|用の推論規則に一致する; 拡張機能を一覧表示します。次の拡張機能を含めるに定義済み: .exe .obj .asm .c .cpp .cxx .bas .cbl られます以下 .pas .res .rc .f .f90。|  
  
 変更する、**です。サフィックス**リストの順序、または新しいリストを指定する一覧を消去し、新しい設定を指定します。 クリアするには、リストを指定しない拡張機能、コロンの後。  
  
```  
.SUFFIXES :  
```  
  
 リストの末尾に追加のサフィックスを追加するに次のように指定します。  
  
```  
.SUFFIXES : suffixlist  
```  
  
 ここで*suffixlist* 1 つ以上のスペースまたはタブで区切られた追加のサフィックスの一覧を示します。 現在の設定を表示する**です。サフィックス**/P. で (nmake の) を実行  
  
## <a name="see-also"></a>参照  
 [NMAKE リファレンス](../build/nmake-reference.md)