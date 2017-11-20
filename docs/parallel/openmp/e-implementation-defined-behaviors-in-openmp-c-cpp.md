---
title: "電子メール。 OpenMP C と C++ の動作の実装で定義された |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: b8d660ca-9bb3-4b6b-87af-45c67d43a731
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d54705947db5125bd9d30adb8a074a6ac354b94a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="e-implementation-defined-behaviors-in-openmp-cc"></a>電子メール。 OpenMP C と C++ の実装で定義される動作
この付録の内容は、"実装定義として"この API で記述されている動作をまとめたものです。  各動作は、メインの仕様では、その説明に相互参照です。  
  
## <a name="remarks"></a>コメント  
 実装が必要ですを定義して、このような場合は、その動作をドキュメントにこの一覧は完全でない可能性があります。  
  
-   **スレッドの数:**スレッドの数を動的に調整が無効になっているし、並行領域に対して要求されたスレッドの数は、ランタイム システムが提供できるの動作数を超えています中に、並行領域が発生した場合。プログラムは、実装定義 (9 ページを参照してください)。  
  
     Visual c での入れ子になっていないの並列領域では、64 個のスレッド (最大) が提供されます。  
  
-   **プロセッサの数:**実際にどの時点でも、スレッドをホストしている物理プロセッサの数は、実装定義 (10 ページを参照してください)。  
  
     Visual c では、この番号は、定数ではなくされ、オペレーティング システムによって制御されます。  
  
-   **スレッドのチームの作成:**は実装定義に入れ子になった並列領域を実行する、チーム内のスレッドの数です (。10 ページを参照)。  
  
     Visual c は、これは、オペレーティング システムによって決定されます。  
  
-   **schedule (runtime):**関連スケジュールは実行時まで遅延が決定します。 スケジュールの種類とチャンクのサイズを設定して実行時に選択できます、`OMP_SCHEDULE`環境変数。 この環境変数が設定されていない場合、結果として得られるスケジュールは、実装定義 (13 ページを参照してください)。  
  
     スケジュールの種類は、Visual c で`static`チャンク サイズがありません。  
  
-   **既定のスケジュール:**スケジュール句のない場合は、既定のスケジュールは、実装定義 (13 ページを参照してください)。  
  
     既定のスケジュールの種類は、Visual c で`static`チャンク サイズがありません。  
  
-   **ATOMIC:**は実装定義されているかどうか、実装をすべて置き換えます`atomic`ディレクティブを**重要な**ディレクティブを持つ同じ一意の名前 (20 ページを参照してください)。  
  
     によってデータが変更された場合、Visual C で[アトミック](../../parallel/openmp/reference/atomic.md)自然なアラインメントはそのプロパティを満たすすべての時間のアトミックな操作が 1 つの重要なセクションを使用して 1 つまたは 2 バイトである場合またはします。 それ以外の場合、クリティカル セクションは使用されません。  
  
-   **omp_get_num_threads:**スレッドの数が設定されていない場合に明示的にユーザーが、既定値は実装定義 (9、ページを参照し、[セクション 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) [37] ページ)。  
  
     Visual c では、既定のスレッド数はプロセッサの数と等しいです。  
  
-   **omp_set_dynamic:**動的なスレッドの調整の既定値は実装定義 (を参照してください[セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 ページ上)。  
  
     既定値は、Visual c で`FALSE`です。  
  
-   **omp_set_nested:**入れ子になった並列領域の実行に使用するスレッドの数は実装定義に入れ子になった並列処理を有効にすると、(を参照してください[セクション 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) 40 ページ上)。  
  
     Visual c では、スレッドの数をオペレーティング システムによって決まります。  
  
-   `OMP_SCHEDULE`環境変数: この環境変数の既定値は実装定義 (を参照してください[セクション 4.1](../../parallel/openmp/4-1-omp-schedule.md) 48 ページ)。  
  
     スケジュールの種類は、Visual c で`static`チャンク サイズがありません。  
  
-   `OMP_NUM_THREADS`環境変数: の値が指定されていない場合、`OMP_NUM_THREADS`環境変数、または指定された値が正の整数または使用するスレッドの数は、値が、システムでサポートできるスレッドの最大数よりも大きい場合は、実装定義 (を参照してください[セクション 4.2](../../parallel/openmp/4-2-omp-num-threads.md) 48 ページ)。  
  
     Visual c でがゼロの値が指定されている場合または、以下の場合、スレッドの数がプロセッサの数と等しい。  値が 64 を超える場合は、スレッドの数は 64 です。  
  
-   `OMP_DYNAMIC`環境変数: 既定値は実装定義 (を参照してください[セクション 4.3](../../parallel/openmp/4-3-omp-dynamic.md) 49 ページ上)。  
  
     既定値は、Visual c で`FALSE`です。