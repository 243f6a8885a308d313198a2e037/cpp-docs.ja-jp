---
title: "反復子 | Microsoft Docs"
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
- iterator conventions
- C++ Standard Library, iterator conventions
ms.assetid: 2f746be7-b37d-4bfc-bf05-be4336ca982f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b75a4f682b83fb8a738a5b19a7c5aa9a1b38166a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="iterators"></a>Iterators
反復子は、C++ 標準ライブラリ コンテナー内の要素を反復処理し、個々の要素へのアクセスを提供するオブジェクトです。 すべての C++ 標準ライブラリ コンテナーに反復子が用意されているため、アルゴリズムではその要素を格納するコンテナーの型を気にせずに標準的な方法で要素にアクセスできます。  
  
 メンバー関数、begin() や end() などのグローバル関数、前方または後方に移動するための ++ や -- といった演算子を使用することにより、反復子を明示的に使用することができます。 また、range-for ループ (一部の反復子の種類の場合) や添字演算子 [] を使用することにより、暗黙的に反復子を使用することもできます。  
  
 C++ 標準ライブラリでは、シーケンスまたは範囲の始まりが最初の要素になります。 シーケンスまたは範囲の終わりは、常に最後の要素の 1 つ後として定義されます。 グローバル関数の begin および end は、反復子を指定されたコンテナーに返します。 コンテナー内のすべての要素に対する通常の明示的な反復子のループは、次のようになります。  
  
```  
 
vector<int> vec{ 0,1,2,3,4 };  
for (auto it = begin(vec);

it != end(vec);

it++)  
{  // Access element using dereference operator
    cout <<*it <<" ";  
}  
```  
  
 同じ処理を、range-for ループでより単純に実現できます。  
  
```  
for (auto num : vec)  
 {  // no deference operator
    cout <<num <<" ";  
 }  
```  
  
 反復子には、5 つのカテゴリがあります。 これらのカテゴリを、機能が低い方から順に示します。  
  
- **出力**。 出力反復子 `X` は、++ 演算子を使用してシーケンスを前方に反復処理できます。また、* 演算子を使用して要素を 1 回だけ書き込むことができます。  
  
- **入力**。 入力反復子 `X` は、++ 演算子を使用してシーケンスを前方に反復処理できます。また、* 演算子を使用して要素を任意の回数読み取ることができます。 ++ と != 演算子を使用することで、入力反復子を比較することができます。 入力反復子のコピーを増分すると、その他のコピーのいずれも、安全に比較、逆参照、または増分することができなくなります。  
  
- **前方**。 前方反復子 `X` は、++ 演算子を使用してシーケンスを前方に反復処理できます。また、* 演算子を使用して任意の要素の読み取りまたは非定数要素の書き込みを任意の回数行うことができます。 要素のメンバーにアクセスするには、-> 演算子を使用します。前方反復子を比較するには、== および != 演算子を使用します。 前方反復子のコピーを複数作成して、それぞれを個別に逆参照または増分できます。 コンテナーへの参照を使用せずに初期化された前方反復子は、NULL 前方反復子と呼ばれます。 NULL 前方反復子を比較すると、常に等しくなります。  
  
-   双方向。 双方向反復子 `X` は、前方反復子の代わりに使用できます。 ただし、--`X`、`X`--、または (`V` = *`X`--) のように、双方向反復子をデクリメントすることもできます。 要素のメンバーにアクセスし、前方反復子と同じ方法で双方向反復子を比較できます。  
  
- **ランダム アクセス**。 ランダム アクセス反復子 `X` は、双方向反復子の代わりに使用できます。 ランダム アクセス反復子では、添字演算子 [] を使用して要素にアクセスできます。 +、-、+=、および -= 演算子を使用して、指定された数の要素を前方または後方に移動したり、反復子間の距離を計算したりできます。 双方向反復子を比較するには、==、!=、\<、>、\<=、および >= を使用します。  
  
 すべての反復子は、割り当てまたはコピーすることができます。 反復子は軽量のオブジェクトであると見なされ、多くの場合、参照ではなく値によって、渡され、返されます。 前述のすべての操作は、有効な反復子に対して実行したときに例外をスローできないことに注意してください。  
  
 反復子のカテゴリの階層は、次の 3 つのシーケンスを表示することによって要約することができます。 シーケンスに対する書き込み専用アクセスの場合、次のいずれの反復子も使用できます。  
  
```  
output iterator  
 -> forward iterator  
 -> bidirectional iterator  
 -> random-access iterator  
```  
  
 右矢印は、"後続の反復子で置き換え可能" であることを示します。 出力反復子を必要とするすべてのアルゴリズムは前方反復子を使用してうまく動作しますが、その逆の方法ではうまく動作*しません*。  
  
 シーケンスに対する読み取り専用アクセスの場合、次のいずれの反復子も使用できます。  
  
```  
input iterator  
 -> forward iterator  
 -> bidirectional iterator  
 -> random-access iterator  
```  
  
 この場合、すべてのカテゴリのうちで最も弱いのは入力反復子です。  
  
 最後に、シーケンスに対する読み取り/書き込みアクセスの場合、次のいずれの反復子も使用できます。  
  
```  
forward iterator  
 -> bidirectional iterator  
 -> random-access iterator  
```  
  
 オブジェクト ポインターは、常にランダム アクセス反復子としての機能を果たします。したがって、指定したシーケンスに対する適切な読み取り/書き込みアクセスをサポートしている場合は、反復子の任意のカテゴリとしての機能を果たします。  
  
 オブジェクト ポインター以外の反復子 `Iterator` では、特殊化 `iterator_traits<Iterator>` で必要なメンバーの型も定義する必要があります。 これらの要件は、パブリック基底クラス [iterator](../standard-library/iterator-struct.md) から `Iterator` を派生させることによって満たすことができます。  
  
 C++ 標準ライブラリのコンテナーとアルゴリズムで反復子がどのように使用されるかを知るには、各反復子カテゴリの約束ごとと制限事項を理解することが必要です。  
  
> [!NOTE]
>  range-for ループを使用することにより、反復子の明示的な使用を避けることができます。 詳細については、「[ループ (Modern C++)](http://msdn.microsoft.com/en-us/b1b2779c-750e-4576-a514-a84178eae9da)」をご覧ください。  
  
 Visual C には、コンテナーの境界を上書きしないことを確認するには、checked 反復子とデバッグ反復子が用意されています。 詳細については、「[チェックを行う反復子](../standard-library/checked-iterators.md)」および「[デバッグ反復子のサポート](../standard-library/debug-iterator-support.md)」をご覧ください。  
  
## <a name="see-also"></a>参照  
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)

