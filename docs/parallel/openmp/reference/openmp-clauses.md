---
title: "OpenMP 句 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 806e7d8f-b204-4e4c-a12c-273ab540a7ca
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a63dacb8da2b7c4b1c7264cfccc6d2839db1b8b1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="openmp-clauses"></a>OpenMP 句
OpenMP API で使用される句へのリンクを提供します。  
  
 Visual C には、次の OpenMP 句がサポートされています。  
  
|句|説明|  
|------------|-----------------|  
|[copyin](../../../parallel/openmp/reference/copyin.md)|スレッドのマスター スレッドの値にアクセスできるように、 [threadprivate](../../../parallel/openmp/reference/threadprivate.md)変数。|  
|[copyprivate](../../../parallel/openmp/reference/copyprivate.md)|すべてのスレッド間で 1 つまたは複数の変数を共有する必要がありますを指定します。|  
|[default](../../../parallel/openmp/reference/default-openmp.md)|並列領域で、対象範囲外の変数の動作を指定します。|  
|[firstprivate](../../../parallel/openmp/reference/firstprivate.md)|Parallel コンストラクトの前に存在するために、各スレッドは、変数の独自のインスタンスである必要があり、変数の値を持つ変数を初期化する必要がありますを指定します。|  
|[if](../../../parallel/openmp/reference/if-openmp.md)|並列または直列に、ループを実行するかどうかを指定します。|  
|[lastprivate](../../../parallel/openmp/reference/lastprivate.md)|いる変数の外側のコンテキストのバージョンを設定して、最後の反復処理 (for ループ コンストラクト) または最後のセクション (#pragma セクション) を実行したスレッドのプライベート バージョンを指定します。|  
|[nowait](../../../parallel/openmp/reference/nowait.md)|ディレクティブ内の暗黙のバリアをオーバーライドします。|  
|[num_threads](../../../parallel/openmp/reference/num-threads.md)|スレッドのチームのスレッドの数を設定します。|  
|[順序付け](../../../parallel/openmp/reference/ordered-openmp-clauses.md)|並列で必要な[の](../../../parallel/openmp/reference/for-openmp.md)ステートメント場合、[順序付け](../../../parallel/openmp/reference/ordered-openmp-directives.md)ディレクティブは、ループで使われます。|  
|[private](../../../parallel/openmp/reference/private-openmp.md)|各スレッドは、変数の独自のインスタンスである必要がありますを指定します。|  
|[reduction](../../../parallel/openmp/reference/reduction.md)|各スレッドに対してプライベートである 1 つまたは複数の変数、並列領域の末尾にあるリダクション演算の対象となることを指定します。|  
|[schedule](../../../parallel/openmp/reference/schedule.md)|適用されます、[の](../../../parallel/openmp/reference/for-openmp.md)ディレクティブです。|  
|[shared](../../../parallel/openmp/reference/shared-openmp.md)|すべてのスレッド間で 1 つまたは複数の変数を共有する必要がありますを指定します。|  
  
## <a name="see-also"></a>参照  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)   
 [ディレクティブ](../../../parallel/openmp/reference/openmp-directives.md)