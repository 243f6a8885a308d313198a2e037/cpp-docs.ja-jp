---
title: デスクトップ アプリケーション (Visual C) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a020b534-293c-44e2-aa48-516c43ddeb8f
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 22f90be7d89a006ccbfdfde2f4c2580a7b2a13de
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643846"
---
# <a name="desktop-applications-visual-c"></a>デスクトップ アプリケーション (Visual C)
A*デスクトップ アプリケーション*C++ では、ウィンドウ、またはシステム コンソールで実行される、Windows Api との完全なセットにアクセスできるネイティブ アプリケーション。 C++ でデスクトップ アプリケーションは、(Windows XP が不要になった正式にサポートされているし、それ以降に導入された多くの Windows Api があります) は、Windows XP、Windows 10 で実行できます。

デスクトップ アプリケーションは、ユニバーサル Windows プラットフォーム (UWP) アプリ、または Windows 10 を実行している Pc でも XBox、Windows Phone、Surface Hub、およびその他のデバイスで実行できるとは異なります。 デスクトップの vs の詳細についてはします。UWP アプリケーションを参照してください[テクノロジを選ぶ](https://msdn.microsoft.com/library/windows/desktop/dn614993\(v=vs.85\).aspx)します。  


### <a name="desktop-bridge"></a>デスクトップ ブリッジ
Windows 10 で、既存のデスクトップ アプリケーションまたは COM オブジェクトを UWP アプリとしてパッケージ化し、タッチなどの UWP 機能を追加したり、最新の Windows API のセットから Api を呼び出します。 Visual Studio、およびパッケージをパッケージ化し、間の通信に Windows Api を使用して、1 つにまとめることでデスクトップ ソリューションに UWP アプリを追加することもできます。  
   
Visual Studio 2017 バージョン 15.4 以降では、既存のデスクトップ アプリケーションをパッケージ化の作業を大幅に簡略化するには、Windows アプリケーション パッケージ プロジェクトを作成することができます。 に関してどのようなレジストリ呼び出しは、いくつかの制限が適用されます。 または、デスクトップ アプリケーションの Api を使用して、、多くの場合、アプリ パッケージの実行中に同様の機能を実現するために代替のコード パスを作成することができます。 詳細については、[デスクトップ ブリッジ](/windows-uwp/porting/desktop-to-uwp-root)に関するページをご覧ください。  
  
### <a name="terminology"></a>用語  
  
-   A *Win32*アプリケーションは、C++ でデスクトップ アプリケーションを使用して、ネイティブの Windows [Windows C Api および COM Api](https://msdn.microsoft.com/library/windows/desktop/ff818516\(v=vs.85\).aspx) CRT と標準ライブラリ Api、およびサード パーティ製のライブラリです。 ウィンドウで実行される Win32 アプリケーションでは、Windows プロシージャ関数内での Windows メッセージを明示的に使用する開発者が必要です。 名前にかかわらず、Win32 アプリケーションは、32 ビット (x86) または 64 ビット (x64) バイナリとしてコンパイルできます。 Visual Studio ide、Win32、x86 の用語は同義です。  
  
-   [コンポーネント オブジェクト モデル (COM)](https://msdn.microsoft.com/library/windows/desktop/ms694363\(v=vs.85\).aspx)は、プログラムが相互に通信するさまざまな言語で記述された仕様です。 多くの Windows コンポーネントが COM オブジェクトとして実装され、オブジェクトの作成の標準の COM 規則に従うには、検出とオブジェクトの破棄がインターフェイスです。  C++ デスクトップ アプリケーションから COM オブジェクトを使用しては比較的簡単ですが、独自の COM オブジェクトの書き込みより高度な。 [Active Template Library (ATL)](../atl/atl-com-desktop-components.md)マクロおよび COM 開発を簡略化するヘルパー関数を提供します。  
  
-   MFC アプリケーションが使用する Windows デスクトップ アプリケーション、 [Microsoft Foundation Classes](../mfc/mfc-desktop-applications.md)ユーザー インターフェイスを作成します。 MFC アプリケーションは、COM コンポーネントだけでなく CRT と標準ライブラリの Api も使用できます。 MFC では、ウィンドウ メッセージ ループと Windows Api 経由でシン C++ オブジェクト指向ラッパーを提供します。 MFC アプリケーションの既定のオプションは、特にエンタープライズ型のアプリケーション-多数のユーザー インターフェイス コントロールまたはカスタム ユーザー コントロールがあります。 MFC では、ウィンドウの管理、シリアル化、テキスト操作、印刷、およびリボンなどの最新のユーザー インターフェイス要素の便利なヘルパー クラスを提供します。 MFC で有効にするための Win32 とよく理解します。  
  
-   C++/cli CLI アプリケーションまたはコンポーネントを使用して C++ 構文の拡張機能 (C++ 仕様で許可されている) と .NET とネイティブ c++ コードの間の対話を有効にします。  C++/cli CLI アプリケーションでネイティブに実行される部品と部品 .NET 基本クラス ライブラリにアクセス権を持つ .NET Framework で実行されることができます。 C +/cli CLI は、c# または Visual Basic で記述されたコードを操作する必要があるネイティブの C++ コードがある場合に推奨されるオプション。 ユーザー インターフェイスのコードではなく .NET Dll で使用するためのものでは主に。 詳細については、次を参照してください。 [C + での .NET プログラミング/cli (Visual c)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)します。  
  
 C ランタイム (CRT) と標準ライブラリのクラスと関数、COM オブジェクト、およびパブリックの Windows の関数は、Windows API と総称されて、C++ では、デスクトップ アプリケーションを使用できます。 C++ の Windows デスクトップ アプリケーションの概要については、「 [C++ による Windows プログラミングの学習](http://go.microsoft.com/fwlink/p/?LinkId=262281)」を参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
|Title|説明|  
|-----------|-----------------|  
|[コンソール アプリケーション](../windows/console-applications-in-visual-cpp.md)|コンソール アプリに関する情報が含まれています。 Win32 (または Win64) コンソール アプリケーションには、独自のウィンドウとメッセージ ループはありません。 コンソール ウィンドウで動作し、入出力はコマンド ラインを使用して扱われます。|  
|[Windows デスクトップ アプリケーション](../windows/windows-desktop-applications-cpp.md)|コンソールではなく windows で実行されるデスクトップ アプリケーションを作成する方法。|  
|[DirectX (C++) を使用してゲームを作成するためのリソース](../windows/resources-for-creating-a-game-using-directx.md)|C++ でのゲームを作成するためのコンテンツへのリンク。|  
|[チュートリアル: を作成して、スタティック ライブラリを使用](../windows/walkthrough-creating-and-using-a-static-library-cpp.md)|.Lib バイナリ ファイルを作成する方法。|  
|[方法: Windows デスクトップ アプリケーションでの Windows 10 SDK の使用](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Windows 10 SDK を使用してビルドするプロジェクトの設定手順が示されています。|  
  
## <a name="related-articles"></a>関連トピック  
  
|タイトル|説明|  
|-----------|-----------------|  
|[Windows 開発](http://go.microsoft.com/fwlink/p/?LinkId=262282)|Windows API と COM に関する情報が含まれています (一部の Windows API とサードパーティ製 DLL は、COM オブジェクトとして実装されています)。|  
|[Hilo: Windows 7 対応 C++ アプリケーションの開発](http://go.microsoft.com/fwlink/p/?LinkId=262284)|手荷物の受け取り場所に基づくユーザー インターフェイスを作成するために、Windows Animation と Direct2D を使用するリッチ クライアントの Windows デスクトップ アプリケーションを作成する方法について説明します。  このチュートリアルは Windows 7 以降に更新されていませんが、Win32 プログラミングに完全な概要についても提供されます。|  
|[Visual C++](../visual-cpp-in-visual-studio.md)|Visual Studio での Visual C++ の主な機能について説明し、他の Visual C++ ドキュメントへのリンクを示します。|  
  
## <a name="see-also"></a>関連項目  
 [Visual C++](../visual-cpp-in-visual-studio.md)