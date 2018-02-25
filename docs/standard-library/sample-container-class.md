---
title: "サンプル コンテナー クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- container classes [C++]
ms.assetid: 5b1451f2-c708-45da-bbf0-9e42fd687a1a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0d528f53747979da7b95d8d3298a43ea717007a5
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="sample-container-class"></a>サンプル コンテナー クラス
> [!NOTE]
>  このトピックは、C++ 標準ライブラリで使用されるコンテナーの例 (実際には機能しない) として、Visual C++ ドキュメントに含まれています。 詳細については、「[C++ 標準ライブラリ コンテナー](../standard-library/stl-containers.md)」を参照してください。  
  
 要素の可変長シーケンスを制御するオブジェクトを表します (通常は **Ty** 型)。 シーケンスは、実際のコンテナーに応じて、さまざまな方法で格納されます。  
  
 コンテナーのコンストラクターまたはメンバー関数がコンストラクター **Ty**(**const Ty&**) または関数 **Ty::operator=**(**const Ty&**) を呼び出す場合があります。 このような呼び出しで例外がスローされた場合、コンテナー オブジェクトは、その整合性を維持し、すべての例外をキャッチして再スローする必要があります。 コンテナー オブジェクトによっていずれか 1 つの例外がスローされた後に、コンテナー オブジェクトを安全にスワップ、消去、または破棄できます。 ただし、通常、それ以外の場合はコンテナー オブジェクトによって制御されるシーケンスの状態を予測できません。  
  
 その他の注意点:  
  
-   式 **~Ty** が例外をスローする場合、コンテナー オブジェクトの結果の状態は未定義です。  
  
-   コンテナーは、アロケーター オブジェクトを保存する場合は*al*、および*al*への呼び出しの結果として以外の例外をスロー * al ***.allocate**コンテナーの結果の状態オブジェクトは、定義されていません。  
  
-   コンテナーが被制御シーケンスの順序付け方法を指定する関数オブジェクト *comp* を格納し、*comp* がいずれかの例外をスローする場合、コンテナー オブジェクトの結果の状態は未定義です。  
  
 C++ 標準ライブラリで定義されているコンテナー クラスは、次に説明するいくつかの追加要件を満たします。  
  
 コンテナーのテンプレート クラス [list](../standard-library/list-class.md) は、上記の例外が存在する場合でも、決定的かつ便利な動作を提供します。 たとえば、1 つまたは複数の要素の挿入時に例外がスローされた場合、コンテナーは変更されず、再度例外がスローされます。  
  
 C++ 標準ライブラリで定義されている*すべての*コンテナー クラスの場合、次のメンバー関数への呼び出し中に例外がスローされると、次のようになります。  
  
```  
<A NAME="vclrfcontainerinsert"></A>insert // single element inserted  
<A NAME="vclrfcontainerpushback"></A>push_back  
<A NAME="vclrfcontainerpushfront"></A>push_front  
```  
  
 コンテナーは変更されず、例外が再度スローされます。  
  
 C++ 標準ライブラリで定義されている*すべての*コンテナー クラスの場合、次のメンバー関数への呼び出し中に例外がスローされないと、次のようになります。  
  
```  
<A NAME="vclrfcontainerpopback"></A>pop_back  
<A NAME="vclrfcontainerpopfront"></A>pop_front  
```  
  
 メンバー関数 [erase](../standard-library/container-class-erase.md) は、コピー操作 (割り当てまたはコピーの構築) が例外をスローする場合にのみ例外をスローします。  
  
 さらに、メンバー関数によって返される反復子のコピー中に例外はスローされません。  
  
 メンバー関数 [swap](../standard-library/container-class-swap.md) は、C++ 標準ライブラリで定義されている*すべての*コンテナー クラスに対する追加の確実性を実現します。  
  
-   コンテナーがアロケーター オブジェクト al を格納し、`al` がコピーされるときに例外をスローする場合にのみ、メンバー関数が例外をスローします。  
  
-   スワップされる被制御シーケンスの要素を指定する参照、ポインター、および反復子は有効なままです。  
  
 C++ 標準ライブラリで定義されたコンテナー クラスのオブジェクトが、`Alloc` 型の格納されているオブジェクトによって制御するシーケンスの記憶域の割り当ておよび解放を行います (これは通常、テンプレート パラメーターです)。 このアロケーター オブジェクトは、クラス **allocator\<Ty>** のオブジェクトと同じ外部インターフェイスを持っている必要があります。 具体的には、`Alloc` は **Alloc::rebind<value_type>::other** と同じ型である必要があります。  
  
 C++ 標準ライブラリで定義されている*すべての*コンテナー クラスの場合、メンバー関数 **Alloc get_allocator const;** は格納されたアロケーター オブジェクトのコピーを返します。 コンテナー オブジェクトを代入しても、格納されているアロケーター オブジェクトはコピー*されない*点に注意してください。 すべてのコンストラクターは、コンストラクターにアロケーターのパラメーターが含まれていない場合、**allocator** に格納されている値を `Alloc` に初期化します。  
  
 C++ 標準に従って、C++ 標準ライブラリで定義されたコンテナー クラスは次を想定できます。  
  
-   クラス `Alloc` のすべてのオブジェクトの比較結果が同じになります。  
  
-   型 **Alloc::const_pointer** が **const Ty \*** と同じです。  
  
-   型 **Alloc::const_reference** が **const Ty&** と同じです。  
  
-   型 **Alloc::pointer** が **Ty \*** と同じです。  
  
-   型 **Alloc::reference** が **Ty&** と同じです。  
  
 ただし、この実装では、コンテナーはこのような単純な想定を行いません。 このため、コンテナーはより意欲的なアロケーター オブジェクトと共に適切に動作します。  
  
-   クラス `Alloc` のすべてのオブジェクトの比較結果が同じである必要はありません。 (記憶域の複数のプールを維持することができます。)  
  
-   型 **Alloc::const_pointer** が **const Ty \*** と同じである必要はありません。 (const ポインターには、クラスを指定できます。)  
  
-   型 **Alloc::pointer** が **Ty \*** と同じである必要はありません。 (ポインターには、クラスを指定できます。)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー**: \<sample container>  
  
## <a name="see-also"></a>参照  
 [\<sample container>](../standard-library/sample-container.md)

