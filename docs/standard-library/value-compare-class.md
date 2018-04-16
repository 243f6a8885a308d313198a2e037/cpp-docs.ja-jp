---
title: "value_compare クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- value_compare
dev_langs:
- C++
helpviewer_keywords:
- value_compare class
ms.assetid: c306c5b9-3505-4357-aa6b-216451b951ed
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c8ecc53d5bd7069d364d881c69f34d4a25b44915
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="valuecompare-class"></a>value_compare クラス
要素のキーの値を比較し、要素の hash_map 内の相対順序を決定して、hash_map の要素を比較できる関数オブジェクトを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class value_compare
 : std::public binary_function<value_type, value_type, bool>
{
public:
    bool operator()(
    const value_type& left,
    const value_type& right) const
 {
    return (comp(left.first, right.first));

 }
protected:
    value_compare(const key_compare& c) : comp (c) { }
    key_compare comp;
};
```  
  
## <a name="remarks"></a>コメント  
 hash_map に含まれる要素全体の **value_type** 間で value_compare によって提供される比較の基準は、補助型クラスの構築によって各要素のキーの間で比較を行うことから導き出されます。 メンバー関数の演算子は、value_compare によって提供される関数オブジェクトに格納されている型 `key_compare` のオブジェクト **comp** を使って、2 つの要素の並べ替えキー構成要素を比較します。  
  
 hash_set と hash_multiset (キーの値が要素の値を同一である単純なコンテナー) の場合、value_compare は `key_compare` と等価です。hash_map と hash_multimap の場合、型 `pair` の要素の値が要素のキーの値と同一ではないため、その 2 つは等価ではありません。  
  
   
  
## <a name="example"></a>例  
 value_compare の宣言方法や使用方法の例については、[hash_map::value_comp](../standard-library/hash-map-class.md#value_comp) の例を参照してください。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<hash_map>  
  
 **名前空間:** stdext  
  
## <a name="see-also"></a>参照  
 [binary_function 構造体](../standard-library/binary-function-struct.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)



