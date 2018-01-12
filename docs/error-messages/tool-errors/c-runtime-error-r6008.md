---
title: "C ランタイム エラー R6008 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6008
dev_langs: C++
helpviewer_keywords: R6008
ms.assetid: f0f304fc-709a-4843-bc7e-bad1ae0d1649
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 86b64f97768359b95d2c5e2003cfb5b95a2aac71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="c-runtime-error-r6008"></a>C ランタイム エラー R6008
引数に必要な領域が足りません。  
  
> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン、内部メモリの問題があるためです。 このエラーは、いくつかの理由が考えられますが、多くの場合、これがによる、非常に低いメモリの状態、環境変数、またはプログラムのバグによって取得されるメモリが多すぎます。  
>   
>  このエラーを解決するには、次の手順を試してみます。  
>   
>  -   その他の実行中のアプリケーションを閉じるか、メモリを解放する、コンピューターを再起動します。  
> -   アプリにコマンドライン引数のサイズと数を削減します。  
> -   使用して、**アプリおよび機能**または**プログラムと機能**] ページで、**コントロール パネルの [**を修復またはプログラムを再インストールします。  
> -   確認**Windows Update**で、**コントロール パネルの** ソフトウェアの更新。  
> -   アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリ ベンダーにお問い合わせください。  
  
 **プログラマのための情報**  
  
 プログラムを読み込むための十分なメモリが作成するのに十分なメモリが発生しました、 **argv**配列。 これは、一般に大きいコマンドラインまたは環境変数の使用法、非常に低いメモリ条件によって可能性があります。 次の解決策のいずれかを検討してください。  
  
-   プログラムに使用可能なメモリの量を増やします。  
  
-   コマンドライン引数のサイズと数を削減します。  
  
-   不要な変数を削除することで環境のサイズを削減します。