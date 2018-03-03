---
title: "3.1.3 omp_get_max_threads 関数 |Microsoft ドキュメント"
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
ms.assetid: 5548897c-546e-4d19-b37b-a76f6b30a0a9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 13aee27dc04afb8414a89bb8f30a98c8e73fb694
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="313-ompgetmaxthreads-function"></a>3.1.3 omp_get_max_threads 関数
**Omp_get_max_threads**関数には、少なくともチームを形成する場合、並行領域なしに使用されるスレッドの数と同じ大きさが保証される整数を返します、 **num_threads**句その時点でコードを検出することでした。 形式は次のとおりです。  
  
```  
#include <omp.h>  
int omp_get_max_threads(void);  
```  
  
 次の値の下限の境界を表現する**omp_get_max_threads**:  
  
```  
  
threads-used-for-next-team  
 <= omp_get_max_threads  
  
```  
  
 場合は、後続の並行領域を使用して、 **num_threads**句の結果の下限の境界の保証、スレッドの特定の番号を要求する**omp_get_max_threads**なしの long を保持します。  
  
 **Omp_get_max_threads**以降の並列領域で形成されるチームのすべてのスレッドに十分な記憶域を動的に割り当てるには関数の戻り値を使用できます。  
  
## <a name="cross-references"></a>クロス リファレンス  
  
-   **omp_get_num_threads**関数を参照してください[セクション 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) [37] ページ。  
  
-   **omp_set_num_threads**関数を参照してください[セクション 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md)ページ 36 にします。  
  
-   **omp_set_dynamic**関数を参照してください[セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)ページ 39 にします。  
  
-   **num_threads**句を参照してください[セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 ページのです。