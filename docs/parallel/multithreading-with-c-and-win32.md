---
title: "C と Win32 を使用するマルチ スレッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/02/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Windows API [C++], multithreading
- multithreading [C++], C and Win32
- Visual C, multithreading
- Win32 applications [C++], multithreading
- threading [C++], C and Win32
- Win32 [C++], multithreading
- threading [C]
ms.assetid: 67cdc99e-1ad9-452b-a042-ed246b70040e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 16353937046384f9dc130048c510197697fb678f
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2018
---
# <a name="multithreading-with-c-and-win32"></a>C と Win32 を使用するマルチスレッド
Microsoft Visual C では、マルチ スレッド アプリケーションを作成するためのサポートを提供します。 複数のスレッドを使用して、アプリケーションが応答しなくなるユーザー インターフェイスを原因となる高価な操作を実行する必要がある場合を検討してください。  
  
 Visual C++ では、複数のスレッドを含むプログラムを作成する方法として、MFC (Microsoft Foundation Class) ライブラリを使用する方法と、C ランタイム ライブラリと Win32 API を使用する方法の 2 つがあります。 MFC でマルチ スレッド アプリケーションの作成方法の詳細については、次を参照してください[C++ と MFC を使用するマルチ スレッド](../parallel/multithreading-with-cpp-and-mfc.md)c でのマルチ スレッドに関する次のトピックを読む。  
  
 以下のトピックでは、マルチスレッド プログラムの作成をサポートする Visual C++ の機能について説明します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [どのようなマルチ スレッド処理については、](../parallel/multithread-programs.md)  
  
-   [ライブラリのサポートのマルチ スレッド](../parallel/library-support-for-multithreading.md)  
  
-   [ファイルをインクルードするマルチ スレッド](../parallel/include-files-for-multithreading.md)  
  
-   [スレッド コントロールのための C ランタイム ライブラリ関数](../parallel/c-run-time-library-functions-for-thread-control.md)  
  
-   [C のサンプルのマルチ スレッド プログラム](../parallel/sample-multithread-c-program.md)  
  
-   [マルチ スレッド Win32 プログラムの作成](../parallel/writing-a-multithreaded-win32-program.md)  
  
-   [コンパイルとリンクのマルチ スレッド プログラム](../parallel/compiling-and-linking-multithread-programs.md)  
  
-   [マルチ スレッド プログラムの問題の回避](../parallel/avoiding-problem-areas-with-multithread-programs.md)  
  
-   [スレッド ローカル ストレージ (TLS)](../parallel/thread-local-storage-tls.md)  
  
## <a name="see-also"></a>参照  
 [旧形式のコードのためのマルチスレッド サポート (Visual C++)](../parallel/multithreading-support-for-older-code-visual-cpp.md)