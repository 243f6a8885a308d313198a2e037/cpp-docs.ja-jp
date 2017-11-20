---
title: "方法: キャンセルを使用して並列ループを中断する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- writing a parallel search algorithm [Concurrency Runtime]
- parallel search algorithm, writing [Concurrency Runtime]
ms.assetid: 421cd2de-f058-465f-b890-dd8fcc0df273
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c8814c5b1856e912adf076c4d6fc9e476df8addf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-use-cancellation-to-break-from-a-parallel-loop"></a>方法: キャンセル処理を使用して並列ループを中断する
この例では、キャンセルを使用して基本的な並列検索アルゴリズムを実装する方法を示します。  
  
## <a name="example"></a>例  

 次の例では、キャンセルを使用して、配列内の要素を検索します。 `parallel_find_any`関数は、 [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)アルゴリズムと[concurrency::run_with_cancellation_token](reference/concurrency-namespace-functions.md#run_with_cancellation_token)関数を指定した値を格納する位置を検索します。 並列ループには、値が検出されると、呼び出し、 [concurrency::cancellation_token_source::cancel](reference/cancellation-token-source-class.md#cancel)将来の処理を取り消す方法です。  


  
 [!code-cpp[concrt-parallel-array-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-cancellation-to-break-from-a-parallel-loop_1.cpp)]  
  

 [Concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)アルゴリズムが同時に動作します。 したがって、あらかじめ決められた順序で処理は実行しません。 配列値の複数のインスタンスが含まれている場合、結果は、その位置のいずれかを指定できます。  

  
## <a name="compiling-the-code"></a>コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるかという名前のファイルに貼り付けます`parallel-array-search.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。  
  
 **cl.exe/EHsc 並列-配列-search.cpp**  
  
## <a name="see-also"></a>関連項目  
 [PPL における取り消し処理](cancellation-in-the-ppl.md)   
 [並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)   
 [parallel_for 関数](reference/concurrency-namespace-functions.md#parallel_for)   
 [cancellation_token_source クラス](../../parallel/concrt/reference/cancellation-token-source-class.md)
