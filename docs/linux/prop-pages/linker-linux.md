---
title: "リンカー プロパティ (Linux C++) | Microsoft Docs"
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0243a94-8164-425b-b2fe-b84ff363d546
author: mikeblome
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.VCLinkerTool.OutputFile
- VC.Project.VCLinkerTool.ShowProgress
- VC.Project.VCLinkerTool.Version
- VC.Project.VCLinkerTool.VerboseOutput
- VC.Project.VCLinkerTool.UnresolvedReferences
- VC.Project.VCLinkerTool.OptimizeForMemory
- VC.Project.VCLinkerTool.SharedLibrarySearchPath
- VC.Project.VCLinkerTool.AdditionalLibraryDirectories
- VC.Project.VCConfiguration.BuildLogFile
- VC.Project.VCLinkerTool.IgnoreDefaultLibraryNames
- VC.Project.VCLinkerTool.ForceSymbolReferences
- VC.Project.VCLinkerTool.LibraryDependencies
- VC.Project.VCLinkerTool.ForceFileOutput
- VC.Project.VCLinkerTool.GenerateMapFile
- VC.Project.VCLinkerTool.Relocation
- VC.Project.VCLinkerTool.FunctionBinding
- VC.Project.VCLinkerTool.NoExecStackRequired
- VC.Project.WholeArchive
- VC.Project.AdditionalOptionsPage
- VC.Project.VCLinkerTool.AdditionalDependencies
ms.openlocfilehash: 963d73e73e42930f0245c0fef443da27bf451bc6
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="linker-properties-linux-c"></a>リンカー プロパティ (Linux C++)

## <a name="general"></a>全般
プロパティ | 説明 | オプション
--- | ---| ---
出力ファイル | このオプションは、リンカーによって作成されるプログラムの既定の名前と場所をオーバーライドします。 (-o)
進行状況の表示 | リンカーの進行状況メッセージを出力します。
Version | -version オプションは、実行ファイルのヘッダーにバージョン番号を付けるようにリンカーを設定します。
詳細出力の有効にする | -verbose オプションは、デバッグ用に詳細メッセージを出力するようにリンカーを設定します。
トレース | --trace オプションは、処理中の入力ファイルを出力するようにリンカーを設定します。
トレース シンボル | シンボルを表示するファイルの一覧を印刷します。 (--trace-symbol=symbol)
マップの印刷 | --print-map オプションはリンク マップを出力するようにリンカーを設定します。
未解決のシンボル参照の報告 | このオプションを有効にすると未解決のシンボル参照が報告されます。
メモリ使用量の最適化 | 必要に応じてシンボル テーブルを再度読み取ることでメモリの使用量を最適化します。
共有ライブラリの検索パス | 共有ライブラリの検索パスをユーザーが設定できるようにします。 (-rpath-link=path)
追加のライブラリ ディレクトリ | 環境のライブラリ パスをユーザーがオーバーライドできるようにします。 (-L フォルダー)
リンカー | リンク中に起動するプログラムか、またはリモート システム上のリンカーへのパスを指定します。
リンクのタイムアウト | リモート リンクのタイムアウト (ミリ秒)。
出力データをコピーします | リモート システムからローカル コンピューターにビルドの出力ファイルをコピーするかどうかを指定します。

## <a name="input"></a>入力
プロパティ | 説明 | オプション
--- | ---| ---
特定の既定のライブラリの無視 | 無視する既定のライブラリの名前を 1 つ以上指定します。 (--exclude-libs lib,lib)
既定のライブラリを無視する | 既定のライブラリを無視して、明示的に指定されたライブラリのみを検索します。
未定義のシンボル参照の強制 | 出力ファイルに未定義のシンボルとしてシンボルを入力するように強制します。 (-u symbol --undefined=symbol)
ライブラリの依存ファイル | このオプションでは、リンカー コマンド ラインに追加する追加ライブラリを指定できます。 追加ライブラリは、'lib' で始まり、拡張子 '.a' で終わるリンカー コマンド ラインの終わりに追加されます。  (-lFILE)
[追加の依存ファイル] | リンク コマンド ラインに追加する項目を指定します。

## <a name="debugging"></a>デバッグ
プロパティ | 説明 | オプション
--- | ---| ---
デバッガー シンボル情報 | 出力ファイルのデバッガー シンボル情報。 | **すべて含む**<br>**デバッガー シンボル情報のみを除外**<br>**すべてのシンボル情報を除外**<br>
マップ ファイル名 | マップ オプションは、ユーザーが指定した名前を使用してマップ ファイルを作成するようにリンカーを設定します。 (-Map=)

## <a name="advanced"></a>詳細設定
プロパティ | 説明 | オプション
--- | ---| ---
再配置後に変数を読み取り専用としてマーク | このオプションは、再配置後に変数を読み取り専用としてマークします。
即時関数バインディングの有効化 | このオプションは、即時関数バインディング用にオブジェクトをマークします。
実行可能スタックは必要ありません | このオプションは、実行可能スタックを必要としないものとして出力をマークします。
アーカイブ全体 | アーカイブ全体は、ソースおよびその他の依存関係のすべてのコードを使用します。


## <a name="additional-options"></a>その他のオプション



