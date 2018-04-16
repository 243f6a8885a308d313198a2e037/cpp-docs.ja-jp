---
title: "リンカー ツールの警告 LNK4210 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4210
dev_langs:
- C++
helpviewer_keywords:
- LNK4210
ms.assetid: db48cff8-a2be-4a77-8d03-552b42c228fa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e4e2d596527b60735b42fb4edfff6f36d0be808d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4210"></a>リンカー ツールの警告 LNK4210  
  
> セクション*セクション*が存在する; がある可能性がありますハンドルされていない静的初期化子、または終末記号  
  
静的初期化子、または終末記号、いくつかのコードが導入されましたが、アプリケーションの起動時に、VCRuntime ライブラリ スタートアップ コードまたはその相当するもの (静的初期化子または終端文字を実行する必要があります) が実行されません。 静的初期化子、または終末記号を必要とするコードの例を次に示します。  
  
-   コンス トラクター、デストラクター、または仮想関数テーブルを含むクラスのグローバル変数。  
  
-   グローバル変数が、非コンパイル時定数を使用して初期化します。  
  
この問題を修正するのには、次のいずれかを試してください。  
  
-   静的初期化子を含むすべてのコードを削除します。  
  
-   使用しないでください[/NOENTRY](../../build/reference/noentry-no-entry-point.md)です。 /NOENTRY を削除した後、削除する必要がありますも[/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md)リンカー コマンドラインからです。  
  
-   ビルドは、/MT を使用している場合、libcmt.lib、libvcruntime.lib、および libucrt.lib をリンカー コマンドラインに追加します。 使用する場合、ビルド/MTd、libcmtd.lib、vcruntimed.lib、および libucrtd.lib を追加します。  
  
-   /Clr から移動するとき:/clr:pure に純粋なコンパイルを削除、 [/ENTRY](../../build/reference/entry-entry-point-symbol.md)リンカー コマンドラインからのオプションです。 これは、CRT の初期化を有効にでき、アプリケーションの起動時に実行される静的初期化子。  
  
 [/GS](../../build/reference/gs-buffer-security-check.md)コンパイラ オプションで初期化が必要です、`__security_init_cookie`関数。 この初期化が既定では、VCRuntime ライブラリ スタートアップで実行されるコードで提供される`_DllMainCRTStartup`です。  
  
-   /ENTRY を使用して、プロジェクトをビルドし、/ENTRY が渡された場合、関数以外の`_DllMainCRTStartup`、関数を呼び出す必要があります`_CRT_INIT`CRT を初期化します。 DLL の/GS を使用して、静的初期化子が必要です、または MFC または ATL コードのコンテキストで呼び出される場合、この呼び出しを単独では十分なではありません。 参照してください[Dll および Visual C ランタイム ライブラリの動作](../../build/run-time-library-behavior.md)詳細についてはします。  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)