---
title: "ヒープ競合の回避 |Microsoft ドキュメント"
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
helpviewer_keywords:
- heap contention
ms.assetid: 797129d7-5f8c-4b0e-8974-bb93217e9ab5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f17f73efc8fba19bb129e3b118f8a4357444aad0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="avoidance-of-heap-contention"></a>ヒープ競合の回避
MFC と ATL で提供される既定の文字列マネージャーは、グローバル ヒープ上に単純なラッパーです。 このグローバル ヒープは、完全にスレッド セーフである、つまり、複数のスレッドが割り当てし、同時に、ヒープを破損することがなくそこからメモリを解放することができます。 スレッド セーフが提供するには、ヒープが、自身へのアクセスをシリアル化します。 通常、これは、クリティカル セクションまたは同様のロック機構で実現します。 2 つのスレッドが、ヒープを同時にアクセスしようとすると、ときに、その他のスレッドの要求が完了するまでに 1 つのスレッドがブロックされます。 多くのアプリケーションでは、このような状況が発生することはほとんどなく、ヒープのロック メカニズムのパフォーマンスに与える影響はごくわずかです。 ただし、複数のスレッドからのヒープを頻繁にアクセスするアプリケーションでは、ヒープのロックの競合によりアプリケーションを実行 (複数の cpu を搭載したマシン) の場合でも、シングル スレッドがある場合よりも速度が低下することができます。  
  
 使用するアプリケーション[CStringT](../atl-mfc-shared/reference/cstringt-class.md)特に、ヒープの競合が発生しやすいために対する操作`CStringT`オブジェクトは、文字列バッファーの再割り当てを頻繁に必要です。  
  
 スレッド間でヒープの競合を軽減する方法の 1 つは、プライベート、スレッド ローカル ヒープから文字列を割り当てる各スレッドです。 文字列が割り当てられている限り、特定のスレッドのアロケーターは、そのスレッドでのみ使用されます、アロケーターでスレッド セーフである必要はありません。  
  
## <a name="example"></a>例  
 次の例は、そのスレッドで文字列を使用する、独自のプライベート非スレッド セーフなヒープの割り当てをスレッド プロシージャを示しています。  
  
 [!code-cpp[NVC_ATLMFC_Utilities#182](../atl-mfc-shared/codesnippet/cpp/avoidance-of-heap-contention_1.cpp)]  
  
## <a name="comments"></a>コメント  
 同じスレッド プロシージャを使用して複数のスレッドが実行される可能性があるが、スレッド間で競合がないため、各スレッドがある、独自のヒープ。 さらに、各ヒープがスレッド セーフではないこと、ファクトは、スレッドの 1 つだけのコピーが実行されている場合でも、測定可能なパフォーマンス向上を示します。 これは、同時実行のアクセスを保護する高価なインタロックされた操作を使用していない、ヒープの結果です。  
  
 手順についてより複雑なスレッドは、スレッド ローカル ストレージ (TLS) スロット内のスレッドの文字列のマネージャーへのポインターを格納すると便利な場合があります。 これにより、他の関数、スレッドの文字列のマネージャーにアクセスするスレッド プロシージャによって呼び出されます。  
  
## <a name="see-also"></a>参照  
 [CStringT によるメモリ管理](../atl-mfc-shared/memory-management-with-cstringt.md)

