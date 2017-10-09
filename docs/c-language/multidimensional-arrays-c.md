---
title: "多次元配列 (C) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- arrays [C], multidimensional
- multidimensional arrays
- subscript expressions
ms.assetid: 4ba5c360-1f17-4575-b370-45f62e1f2bc2
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: fbc5ca61d1a45521c67426144ad5991170849230
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="multidimensional-arrays-c"></a>多次元配列 (C)
添字式には、次のように複数の添字がある場合があります。  
  
```  
  
expression1  
[  
expression2  
] [  
expression3  
]...  
```  
  
 添字式は、左から右へ関連付けられます。 左端の添字式、*expression1***[***expression2***]** が最初に評価されます。 *expression1* と *expression2* を加算した結果として得られるアドレスからポインター式が形成され、次にこのポインター式に *expression3* が加算されて新しいポインター式が形成されます。このようにして、最後の添字式が加算されるまで処理が行われます。 間接演算子 (**\***) は、最終的なポインター値が配列型のアドレスを指していない限り、最後の添字式が評価された後に適用されます (下の例を参照)。  
  
 複数の添字を持つ式は、"多次元配列" の要素を参照します。 多次元配列は、要素が配列である配列です。 たとえば、3 次元配列の最初の要素は 2 次元配列です。  
  
## <a name="examples"></a>例  
 以下では、その後の各例で使用するために、`prop` という名前の配列を宣言しています。この配列には 3 つの要素があり、各要素は `int` 値の 4 × 6 配列になっています。  
  
```  
int prop[3][4][6];  
int i, *ip, (*ipp)[6];  
```  
  
 `prop` 配列を参照するときには、次のようになります。  
  
```  
i = prop[0][0][1];  
```  
  
 上の例は、`int` の個々の `prop` 要素の 2 番目を参照する方法を示しています。 配列は行ごとに格納されるので、最後の添字が最も速く変化します。そのため、たとえば配列の次の (3 番目の) 要素を参照する式は、`prop[0][0][2]` のようになります。  
  
```  
i = prop[2][1][3];  
```  
  
 このステートメントは、`prop` の個々の要素への、より複雑な参照です。 この式は、次のように評価されます。  
  
1.  最初の添字 `2` に、4 × 6 の `int` 配列のサイズが乗算され、それがポインター値 `prop` に加算されます。 結果は、`prop` の 3 番目の 4 × 6 配列をポイントします。  
  
2.  2 番目の添字 `1` に 6 要素の `int` 配列のサイズが乗算され、それが `prop[2]` で表されるアドレスに加算されます。  
  
3.  6 つの要素を持つ配列の各要素は `int` 値であるため、最後の添字の `3` に `int` のサイズが乗算され、それが `prop[2][1]` に加算されます。 結果のポインターは 6 要素配列の 4 番目の要素のアドレスを指します。  
  
4.  このポインター値に間接演算子が適用されます。 結果は、そのアドレスにある `int` 要素です。  
  
 次の 2 つの例は、間接演算子が適用されないケースを示しています。  
  
```  
ip = prop[2][1];  
  
ipp = prop[2];  
```  
  
 この最初のステートメントの式 `prop[2][1]` は、(上で宣言した) 3 次元配列 `prop` への有効な参照で、この場合は 1 つの 6 要素配列を参照しています。 ポインター値は配列のアドレスを指すため、間接演算子は適用されません。  
  
 同様に、2 番目のステートメント `prop[2]` の式 `ipp = prop[2];` の結果は、1 つの 2 次元配列のアドレスを指すポインター値です。  
  
## <a name="see-also"></a>関連項目  
 [添字演算子:](../cpp/subscript-operator.md)
