---
title: "&lt;スレッド&gt;|Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <thread>
dev_langs:
- C++
ms.assetid: 0c858405-4efb-449d-bf76-70d3693c9234
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 496269689428e73dc78893092844afb1650da20d
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="ltthreadgt"></a>&lt;thread&gt;
標準ヘッダーをインクルード\<スレッド > クラスを定義する`thread`やさまざまなサポートする関数。  
  
## <a name="syntax"></a>構文  
  
```cpp  
#include <thread>  
```  
  
## <a name="remarks"></a>コメント  
  
> [!NOTE]
>  使用してコンパイルされたコードで**/clr**、このヘッダーはブロックされます。  
  
 `__STDCPP_THREADS__`スレッドはこのヘッダーでサポートされていることを示すために 0 以外の値としてマクロを定義します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-classes"></a>パブリック クラス  
  
|名前|説明|  
|----------|-----------------|  
|[thread クラス](../standard-library/thread-class.md)|観察およびアプリケーションの実行のスレッドを管理するために使用できるオブジェクトを定義します。|  
  
### <a name="public-structures"></a>パブリック構造体  
  
|名前|説明|  
|----------|-----------------|  
|[hash 構造体 (C++ 標準ライブラリ)](../standard-library/hash-structure-stl.md)|によって一意に決定される値を返すメンバー関数の定義、`thread::id`です。 このメンバー関数を定義、[ハッシュ](../standard-library/hash-class.md)型のマッピングの値に適した関数`thread::id`インデックス値の分布にします。|  
  
### <a name="public-functions"></a>パブリック関数  
  
|名前|説明|  
|----------|-----------------|  
|[get_id](../standard-library/thread-functions.md#get_id)|現在の実行スレッドを一意に識別します。|  
|[sleep_for](../standard-library/thread-functions.md#sleep_for)|呼び出し元のスレッドをブロックします。|  
|[sleep_until](../standard-library/thread-functions.md#sleep_until)|少なくとも指定された時間まで、呼び出し元スレッドをブロックします。|  
|[swap](../standard-library/thread-functions.md#swap)|2 つの状態と交換`thread`オブジェクト。|  
|[yield](../standard-library/thread-functions.md#yield)|現在のスレッドが通常引き続き実行される場合であっても、他のスレッドを実行するようオペレーティング システムに通知します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator > = 演算子](../standard-library/thread-operators.md#op_gt_eq)|一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値以上かどうかを判断します。|  
|[operator > 演算子](../standard-library/thread-operators.md#op_gt)|一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値より大きいかどうかを判断します。|  
|[operator < = 演算子](../standard-library/thread-operators.md#op_lt_eq)|一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値以下かどうかを判断します。|  
|[operator < 演算子](../standard-library/thread-operators.md#op_lt)|一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値より小さいかどうかを判断します。|  
|[operator! = 演算子](../standard-library/thread-operators.md#op_neq)|2 つの `thread::id` オブジェクトが等しくないかどうかを比較します。|  
|[演算子 = = 演算子](../standard-library/thread-operators.md#op_eq_eq)|2 つの `thread::id` オブジェクトが等しいかどうかを比較します。|  
|[演算子 << 演算子](../standard-library/thread-operators.md#op_lt_lt)|`thread::id` オブジェクトのテキスト表現をストリームに挿入します。|  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)


