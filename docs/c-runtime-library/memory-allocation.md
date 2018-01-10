---
title: "メモリ割り当て | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.memory
dev_langs: C++
helpviewer_keywords:
- memory allocation, routines
- memory, managing
- memory, allocation
ms.assetid: b4470556-a128-4782-9943-2ccf7a7d9979
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e419cbd30b523121ae1902b49a25d60c0b9d21eb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="memory-allocation"></a>メモリ割り当て
これらのルーチンを使用して、メモリを割り当て、解放、および再割り当てします。  
  
### <a name="memory-allocation-routines"></a>メモリ割り当てルーチン  
  
|ルーチンによって返される値|使用|  
|-------------|---------|  
|[_alloca](../c-runtime-library/reference/alloca.md)、[_malloca](../c-runtime-library/reference/malloca.md)|スタックからメモリを割り当てます。|  
|[calloc](../c-runtime-library/reference/calloc.md)|配列の記憶域を割り当て、割り当てられたブロック内のすべてのバイトを 0 に初期化します。|  
|[_calloc_dbg](../c-runtime-library/reference/calloc-dbg.md)|`calloc` のデバッグ バージョン。ランタイム ライブラリのデバッグ バージョンでのみ使用できます。|  
|[operator delete](../c-runtime-library/operator-delete-crt.md)|割り当てられたブロックを解放します。|  
|[operator delete&#91;&#93;](../c-runtime-library/delete-operator-crt.md)|割り当てられたブロックを解放します。|  
|[_expand](../c-runtime-library/reference/expand.md)|メモリ ブロックを移動しないで拡大および縮小します。|  
|[_expand_dbg](../c-runtime-library/reference/expand-dbg.md)|`_expand` のデバッグ バージョン。ランタイム ライブラリのデバッグ バージョンでのみ使用できます。|  
|[free](../c-runtime-library/reference/free.md)|割り当てられたブロックを解放します。|  
|[_free_dbg](../c-runtime-library/reference/free-dbg.md)|`free` のデバッグ バージョン。ランタイム ライブラリのデバッグ バージョンでのみ使用できます。|  
|[_freea](../c-runtime-library/reference/freea.md)|スタックから割り当てられたブロックを解放します。|  
|[_get_heap_handle](../c-runtime-library/reference/get-heap-handle.md)|CRT ヒープの Win32 HANDLE を取得します。|  
|[_heapadd](../c-runtime-library/heapadd.md)|ヒープにメモリを追加します。|  
|[_heapchk](../c-runtime-library/reference/heapchk.md)|ヒープの一貫性をチェックします。|  
|[_heapmin](../c-runtime-library/reference/heapmin.md)|ヒープ内の未使用のメモリを解放します。|  
|[_heapset](../c-runtime-library/heapset.md)|空きヒープ エントリに、指定された値を設定します。|  
|[_heapwalk](../c-runtime-library/reference/heapwalk.md)|ヒープ内の各エントリに関する情報を返します。|  
|[malloc](../c-runtime-library/reference/malloc.md)|ヒープからメモリ ブロックを割り当てます。|  
|[_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md)|`malloc` のデバッグ バージョン。ランタイム ライブラリのデバッグ バージョンでのみ使用できます。|  
|[_msize](../c-runtime-library/reference/msize.md)|割り当てられたブロックのサイズを返します。|  
|[_msize_dbg](../c-runtime-library/reference/msize-dbg.md)|`_msize` のデバッグ バージョン。ランタイム ライブラリのデバッグ バージョンでのみ使用できます。|  
|[new](../c-runtime-library/operator-new-crt.md)|ヒープからメモリ ブロックを割り当てます。|  
|[new&#91;&#93;](../c-runtime-library/new-operator-crt.md)|ヒープからメモリ ブロックを割り当てます。|  
|[_query_new_handler](../c-runtime-library/reference/query-new-handler.md)|`_set_new_handler` によって設定された現在の新しいハンドラー ルーチンのアドレスを返します。|  
|[_query_new_mode](../c-runtime-library/reference/query-new-mode.md)|`_set_new_mode` に対して `malloc` によって設定された新しいハンドラー モードを示す整数を返します|  
|[realloc](../c-runtime-library/reference/realloc.md)|ブロックを新しいサイズに再割り当てします。|  
|[_realloc_dbg](../c-runtime-library/reference/realloc-dbg.md)|`realloc` のデバッグ バージョン。ランタイム ライブラリのデバッグ バージョンでのみ使用できます。|  
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|`new` 演算子が (メモリの割り当てに) 失敗したときにエラー処理機構を有効にし、C++ 標準ライブラリのコンパイルを有効にします|  
|[_set_new_mode](../c-runtime-library/reference/set-new-mode.md)|`malloc` の新しいハンドラー モードを設定します。|  
  
## <a name="see-also"></a>参照  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)