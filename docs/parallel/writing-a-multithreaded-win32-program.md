---
title: "マルチ スレッド Win32 プログラムの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- thread stacks [C++]
- resources [C++], multithreading
- stacks [C++]
- shared resources [C++]
- threading [C++], sharing common resources
- multithreading [C++], thread stacks
- multithreading [C++], sharing common resources
- mutual exclusion [C++]
- communications [C++], between threads
- mutex [C++]
- threading [C++], thread stacks
ms.assetid: 1415f47d-417f-4f42-949b-946fb28aab0e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4ede0e6dc1740f93f4905dc69b1927aee0d1a7ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="writing-a-multithreaded-win32-program"></a>マルチスレッド Win32 プログラムの作成
複数のスレッドでプログラムを記述するときに、その動作を調整する必要がありますと[プログラムのリソースの使用](#_core_sharing_common_resources_between_threads)です。 各スレッドが受信することを確認することも必要[独自のスタック](#_core_thread_stacks)です。  
  
##  <a name="_core_sharing_common_resources_between_threads"></a>スレッド間でのリソースの共有  
  
> [!NOTE]
>  MFC の観点から説明については、次を参照してください。[マルチ スレッド: プログラミングのヒント](../parallel/multithreading-programming-tips.md)と[マルチ スレッド: 同期クラスを使用するときに](../parallel/multithreading-when-to-use-the-synchronization-classes.md)です。  
  
 各スレッドは、専用のスタックと CPU レジスタの専用コピーを持っています。 ファイル、静的データ、ヒープ メモリなどのリソースは、プロセス内のすべてのスレッドで共有します。 これらの共通リソースを使うスレッドは、同期をとる必要があります。 Win32 には、セマフォや、クリティカル セクション、イベント、ミューテックスなど、リソースの同期をとるためにさまざまな方法が用意されています。  
  
 複数のスレッドが静的データにアクセスするときには、リソースの競合に備える必要があります。 1 つのスレッドが、静的データを含む構造体を更新プログラムについて考えてみましょう*x*、*y*別のスレッドに表示する項目の座標。 更新スレッドを変更する場合、 *x*を調整し、それを変更前に、プリエンプションの対象、 *y*座標、表示スレッドがスケジュールする前に、 *y*座標は、更新されます。 その結果、項目は間違った場所に表示されます。 このような問題は、セマフォを使って構造体へのアクセスを制御することにより解決できます。  
  
 ミュー テックス (の略*mut*ual *ex*clusion) のいずれかの別の非同期的に実行されているスレッドやプロセスの間で通信する方法を示します。 この通信は、複数のスレッドやプロセスの処理を調整する一般的な方法で、共有リソースをロックまたはロックを解除することにより共有リソースへのアクセスを制御します。 これを解決する*x*、*y*座標の更新の問題、更新スレッドは、データ構造が、更新プログラムを実行する前に使用することを示すミュー テックスを設定します。 両方の座標が更新されたら、ミューテックスを解除します。 表示スレッドは、ミューテックスが解除されるのを待ってから画面を更新する必要があります。 この場合プロセスはブロックされて、ミューテックスが解除されるまで先へ進むことができないので、ミューテックスを待つこのプロセスは、ミューテックスによりブロッキングされているということがあります。  
  
 Bounce.c プログラムに示すように[マルチ スレッドの C サンプル プログラム](../parallel/sample-multithread-c-program.md)名前付きミュー テックスを使用`ScreenMutex`を画面の更新を調整します。 表示スレッドの 1 つを書き込む準備が画面に毎回呼び出して**WaitForSingleObject**を識別するハンドルと`ScreenMutex`定数と**無限**ことを示す、 **WaitForSingleObject**呼び出しがタイムアウトしない、ミュー テックス ブロックする必要があります。`ScreenMutex` が解除されると、待機している関数がミューテックスをセットして、ほかのスレッドが表示に干渉できないようにしてスレッドの実行を続けます。 ScreenMutex が解除されない場合、スレッドはミューテックスが解除されるまでブロックされます。 呼び出すことにより、ミュー テックスを解放スレッドには、表示更新が完了すると、 **ReleaseMutex**です。  
  
 画面表示と静的データは、注意深く管理する必要がある 2 つのリソース例にすぎません。 たとえば、プログラムには、同じファイルにアクセスする複数のスレッドが存在する場合があります。 別のスレッドがファイル ポインターを移動した可能性があるので、それぞれのスレッドは、読み書きする前にファイル ポインターをリセットする必要があります。 さらに、各スレッドは、ポインターに位置をセットしてからファイルにアクセスするまでの間にプリエンプトされないようにする必要があります。 これらのスレッドは、セマフォを使用してで各ファイルのアクセスを囲むことにより、ファイルへのアクセスを調整する**WaitForSingleObject**と**ReleaseMutex**呼び出しです。 この手法を説明するコード例を次に示します。  
  
```  
HANDLE    hIOMutex= CreateMutex (NULL, FALSE, NULL);  
  
WaitForSingleObject( hIOMutex, INFINITE );  
fseek( fp, desired_position, 0L );  
fwrite( data, sizeof( data ), 1, fp );  
ReleaseMutex( hIOMutex);  
```  
  
##  <a name="_core_thread_stacks"></a>スレッド スタック  
 アプリケーションの既定のスタック領域はすべて、スレッド 1 と呼ばれる、最初に実行されるスレッドに必ず割り当てられます。 したがって、2 番目以降のスレッドのスタックに割り当てるメモリの量を指定する必要があります。 オペレーティング システムは、必要に応じて、スレッドに対してスタック領域をさらに割り当てますが、既定値は指定する必要があります。  
  
 最初の引数で、`_beginthread`呼び出しがへのポインター、 **BounceProc**関数で、スレッドを実行します。 2 番目の引数では、スレッドに対する既定のスタック サイズを指定します。 最後の引数に渡される ID 番号は、 **BounceProc**です。 **BounceProc**乱数ジェネレーターのシードと、スレッドの色の属性を選択し、文字の表示を ID 番号を使用します。  
  
 C のランタイム ライブラリまたは Win32 API を呼び出すスレッドは、呼び出すライブラリと API 関数のために十分なスタック領域を用意する必要があります。 C 言語ライブラリの `printf` 関数には、500 バイト以上のスタック領域が必要です。また Win32 API ルーチンを呼び出すには、スタック領域として 2K バイト用意する必要があります。  
  
 スレッドはそれぞれ自分自身のスタックを持っているので、できる限り静的データを使わないことで、データ項目に対して起こりうる衝突を避けることができます。 スレッドが持つ各データに対しては、すべて auto 自動スタック変数を使うようにプログラムをデザインします。 Bounce.c プログラムのグローバル変数は、ミューテックスか、初期化後に変化しない変数のいずれかです。  
  
 Win32 には、スレッドの個別データを格納するために、スレッド ローカル ストレージ (TLS: Thread-Local Storage) も用意されています。 詳細については、次を参照してください。[スレッド ローカル ストレージ (TLS)](../parallel/thread-local-storage-tls.md)です。  
  
## <a name="see-also"></a>参照  
 [C と Win32 を使用するマルチスレッド](../parallel/multithreading-with-c-and-win32.md)