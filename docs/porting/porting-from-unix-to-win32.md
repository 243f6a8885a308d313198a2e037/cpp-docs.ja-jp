---
title: "UNIX から Win32 への移植 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "APIs [C++], porting to Win32"
  - "migration [C++]"
  - "porting to Win32 [C++]"
  - "porting to Win32 [C++], from UNIX"
  - "UNIX [C++], porting to Win32"
  - "Win32 applications [C++], migrating from UNIX"
  - "Windows API [C++], migrating from UNIX"
ms.assetid: 3837e4fe-3f96-4f24-b2a1-7be94718a881
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# UNIX から Win32 への移植
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

アプリケーションを UNIX から Windows に移行するときにいくつかのオプションがあります。  
  
-   UNIX のライブラリを使用して UNIX から Win32 にアプリケーションを移植する  
  
-   UNIX から Win32 にアプリケーションをネイティブに移植する  
  
-   POSIX サブシステムを使用して Windows 上で UNIX アプリケーションを実行する  
  
## UNIX ライブラリ  
 UNIX プログラマが通常検討する 1 つのオプションは、Win32 実行可能ファイルとして UNIX コードをコンパイルできるサードパーティ製の UNIX のようなライブラリを使用することです。  いくつかの商用 \(および少なくとも 1 つのパブリック ドメイン\) のライブラリがこれを行います。  これは、一部のアプリケーションのためのオプションです。  これらの移植ライブラリの利点は、最初の移植作業を最小限にできることです。  競争力のあるソフトウェア製品にとっての主な短所は、通常アプリケーションのネイティブ Win32 の移植の方が高速で、機能も多くなります。  Win32 呼び出しを行って Windows のパワーを利用する必要がある場合は、アプリケーションが UNIX シェルの外に出ることで不便が生じる可能性があります。  
  
 UNIX を Visual C\+\+ に移植してサポートするためのMicrosoft とサード パーティのリソースを次に示します。  
  
### UNIX 移行ガイド  
 UNIX カスタム アプリケーションの移行ガイドは、UNIX から Win32 環境にコードを移行するときの技術的な助けを提供します。  
  
 [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=95428](http://go.microsoft.com/fwlink/?LinkId=95428)  
  
 Unix 移行プロジェクト ガイドは、UNIX から Win32 への大きなプロジェクトの移行に関する概要レベルの支援を提供する点で、UNIX カスタム アプリケーション移行ガイドを補足します。  ガイドは、プロジェクトの移行の各段階で考慮する問題へのアドバイスを提供します。  ガイドは次の場所からダウンロードできます。  
  
 [http:\/\/go.microsoft.com\/fwlink\/?linkid\=20012](http://go.microsoft.com/fwlink/?linkid=20012)  
  
### Microsoft Windows Services for UNIX \(SFU\)  
 Microsoft Windows Services for UNIX \(SFU\) は、Windows を既存の UNIX ベースの環境に統合するための幅広いクロス プラットフォーム サービスを提供します。  UNIX 用のサービスは、ファイル共有、リモート アクセスと管理、パスワード同期、一般的なディレクトリの管理、一連の共通ユーティリティ、およびシェルを提供します。  
  
 [Windows Services for UNIX](http://www.microsoft.com/ja-jp/download/details.aspx?id=274)  
  
### InteropSystems.com  
 [http:\/\/www.interopsystems.com\/](http://www.interopsystems.com/)  
  
 UNIX から Win32 への移植をサポートするソフトウェアを提供する企業のサードパーティ サイトです。  
  
### C\+\+ による Web サイトの向上  
 [http:\/\/boost.sourceforge.net\/regression\-logs\/](http://boost.sourceforge.net/regression-logs/)  
  
 [http:\/\/boost.sourceforge.net\/boost\-build2\/](http://boost.sourceforge.net/boost-build2/)  
  
## Win32 に UNIX アプリケーションを直接移植する  
 別のオプションは、Win32 に直接 UNIX アプリケーションを移植することです。  ANSI C と C\+\+ のライブラリ、および商用の C コンパイラのライブラリを使用して、UNIX アプリケーションが使用する従来のシステム呼び出しの多くが Win32 アプリケーションで使用できます。  
  
 **stdio** ベースのアプリケーションの出力モデルは、Win32 コンソール API が **stdio** モデルを模倣していて、Win32 コンソールの API を使用する *curses* のバージョンが存在するため、変更する必要がありません。  詳細については、「[SetConsoleCursorPosition](http://msdn.microsoft.com/library/windows/desktop/ms686025)」を参照してください。  
  
 Berkeley ソケット ベースのアプリケーションが Win32 アプリケーションとして機能するために、変更はほとんど必要ありません。  Windows ソケット インターフェイスは、WinSock の仕様の序論のセクションで説明されている最小限の変更により、BSD ソケットの移植のために設計されました。  
  
 Windows は DCE に準拠した RPC をサポートするので、RPC ベースのアプリケーションは簡単に使用できます。  「[RPC 関数](http://msdn.microsoft.com/library/windows/desktop/aa378623)」を参照してください。  
  
 最も大きな違いの 1 つが、プロセス モデルにあります。  UNIX には**fork** がありますが、Win32 にはありません。  **fork** とコード ベースの使用法によりますが、Win32 では**CreateProcess** と `CreateThread` の 2 つの API を使用できます。  複数のコピーを fork する UNIX アプリケーションは、複数のプロセス、または複数のスレッド内の 1 つのプロセスのいずれかを持つよう Win32 で書き直すことができます。  複数のプロセスを使用している場合は、プロセス間で通信するため \(そしておそらく、**fork** が提供する機能が必要とされる場合は、親のように新しいプロセスのコードとデータを更新するため\) に使用できる IPC のメソッドが複数あります。   IPC の詳細については、「[プロセス間通信](http://msdn.microsoft.com/library/windows/desktop/aa365574)」を参照してください。  
  
 Windows と UNIX のグラフィカルなモデルは、大きく異なります。  UNIX はX Window System GUIを使用し、Windows は GUI を使用します。  概念的に似ていますが、X API と GDI API の単純なマッピングはありません。  ただし、OpenGL のサポートが、UNIX の OpenGL ベースのアプリケーションを移行するのに使用できます。  また、Windows 用の X クライアントと X サーバーもあります。  GDI の詳細については、「[デバイス コンテキスト](http://msdn.microsoft.com/library/windows/desktop/dd183553) を参照してください。  
  
 多くの CGI アプリケーションを含む基本的な UNIX アプリケーションは、Windows で実行されている Visual C\+\+ に簡単に移植できるはずです。  **open**、`fopen`、**read**、**write**などの関数が、Visual C\+\+ ランタイム ライブラリで利用できます。  また、C UNIX API と Win32 API の間には 1 対 1 のマッピングがあります。**open** は **CreateFile**、**read** は **ReadFile**、**write** は **WriteFile**、`ioctl`は **DeviceIOControl**、**close** は **CloseFile** などのマッピングです。  
  
## Windows の POSIX サブシステム  
 UNIX プログラマが確認するもう 1 つのオプション は、Windows の POSIX サブシステムです。  ただし、これは Windows NT の作成時に標準化された唯一の POSIX バージョンである POSIX 1003.1 のみサポートします。  それ以降は、ほとんどのアプリケーションは Win32 に変換されたので、このサブシステムを拡張する要求がほとんどありませんでした。  1003.1 システムは全機能を備えたアプリケーションに対しては、多くの機能 \(1003.2 にあるもの、ネットワークのサポートなど\) が含まれていないため、機能が制限されます。  Windows POSIX サブシステムで動作する、全機能を備えたアプリケーションは、メモリ マップ ファイル、ネットワーク、グラフィックなど、Win32 アプリケーションで利用できる Windows の機能にアクセスしません。  VI、LS、および GREP などのアプリケーションが、Windows POSIX サブシステムの主な対象です。  
  
## 参照  
 [プログラムの移植](http://msdn.microsoft.com/ja-jp/c36c44b3-5a9b-4bb4-9b7a-469aa770ed00)   
 [UNIX](../Topic/UNIX.md)   
 [推論規則](../build/inference-rules.md)