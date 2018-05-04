---
title: -SUBSYSTEM |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /subsystem
dev_langs:
- C++
helpviewer_keywords:
- /SUBSYSTEM editbin option
- -SUBSYSTEM editbin option
- SUBSYSTEM editbin option
ms.assetid: 515e4cdf-3cc4-4659-8764-1f2757b49215
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c12df1a2166c9ef5a1af8a33a5764a8899909edb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="subsystem"></a>/SUBSYSTEM
実行可能イメージに必要な実行環境を指定します。  
  
```  
/SUBSYSTEM:{BOOT_APPLICATION|CONSOLE|EFI_APPLICATION|  
        EFI_BOOT_SERVICE_DRIVER|EFI_ROM|EFI_RUNTIME_DRIVER|  
        NATIVE|POSIX|WINDOWS|WINDOWSCE}[,major[.minor]]  
```  
  
## <a name="remarks"></a>コメント  
 このオプションは、イメージを編集して、実行のためにオペレーティング システムから呼び出すサブシステムを指定します。  
  
 以下のいずれかのサブシステムを指定できます。  
  
 BOOT_APPLICATION  
 Windows のブート環境で実行するアプリケーションです。 ブート アプリケーションの詳細については、次を参照してください。 [BCD WMI プロバイダーに関する](http://msdn.microsoft.com/library/aa362639.aspx)です。  
  
 CONSOLE  
 Windows キャラクター モード アプリケーション。 オペレーティング システムには、コンソール アプリケーションのコンソールが用意されています。  
  
 拡張可能なファームウェア インターフェイス (EFI) イメージ  
 EFI サブシステムのオプションは、拡張可能なファームウェア インターフェイスの環境で実行できる実行可能イメージを設定します。 この環境は通常、ハードウェアと共に提供され、オペレーティング システムが読み込まれる前に実行されます。 EFI のイメージの種類による主な相違点は、イメージが読み込まれるメモリ位置、およびイメージへの呼び出しが返されるときに実行される処理です。 EFI_APPLICATION イメージは、制御が返されるとアンロードされます。 EFI_BOOT_SERVICE_DRIVER または EFI_RUNTIME_DRIVER は、エラー コードと共に制御が返された場合にのみアンロードされます。 EFI_ROM イメージは ROM から実行されます。 詳細についてを参照してください、仕様上、 [Unified EFI Forum](http://www.uefi.org/) web サイトです。  
  
 NATIVE  
 サブシステム環境なしで実行されるコード、たとえばカーネル モード デバイス ドライバーやネイティブ システム プロセス。 このオプションは、通常、Windows システムの機能のために予約されています。  
  
 POSIX  
 Windows 上の POSIX サブシステムで実行するアプリケーション。  
  
 WINDOWS  
 Windows のグラフィカル環境で実行するアプリケーション。 これには、デスクトップ アプリとユニバーサル Windows プラットフォーム (UWP) アプリの両方が含まれます。  
  
 WINDOWSCE  
 WINDOWSCE サブシステムは、アプリケーションが Windows CE カーネルのバージョンがあるデバイスで実行するように設計されたことを示します。 カーネルのバージョンには、PocketPC、Windows Mobile、Windows Phone 7、Windows CE V1.0-6.0R3、および Windows Embedded Compact 7 があります。  
  
 `major` および `minor` 値 (省略可能) で、指定したサブシステムの必要最低バージョンを指定します。  
  
-   バージョン番号の整数部 (小数点の左側) は、`major` で指定します。  
  
-   バージョン番号の小数部 (小数点の右側) は、`minor` で指定します。  
  
-   `major` と `minor` で指定できる値は、0 ～ 65,535 の範囲です。  
  
 選択したサブシステムに応じて、プログラムの既定の開始アドレスも変わります。 詳細については、次を参照してください。 [/ENTRY (エントリ ポイント シンボル)](../../build/reference/entry-entry-point-symbol.md)、リンカーの/ENTRY:*関数*オプション。  
  
 詳細については、各サブシステムのメジャーおよびマイナー バージョン番号の最小値と既定値を含む、次を参照してください。、 [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md)リンカー オプション。  
  
## <a name="see-also"></a>関連項目  
 [EDITBIN オプション](../../build/reference/editbin-options.md)