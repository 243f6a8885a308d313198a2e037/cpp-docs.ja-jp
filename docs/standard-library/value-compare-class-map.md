---
title: value_compare Class (&lt;map&gt;) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- std::value_compare
- std.value_compare
- map/std::value_compare
- value_compare
dev_langs:
- C++
helpviewer_keywords:
- std::value_compare
ms.assetid: ea97c1d0-04b2-4d42-8d96-23522c04cc41
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fbb0f651c22702fdad7ca392fa76e4827c6c2e25
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="valuecompare-class-ltmapgt"></a>value_compare クラス (&lt;map&gt;)
要素のキーの値を比較し要素のマップ内の相対順序を決定して、マップの要素を比較できる関数オブジェクトを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class value_compare : public binary_function<value_type, value_type, bool>
{
public:
    bool operator()(const value_type& left, const value_type& right) const;
    value_compare(key_compare pred) : comp(pred);
protected:
    key_compare comp;
};
```  
  
## <a name="remarks"></a>コメント  
 マップに含まれる要素全体の **value_type** 間で `value_compare` によって提供される比較の基準は、補助型クラスの構築によって各要素のキーの間で比較を行うことから導き出されます。 メンバー関数の演算子は、`value_compare` によって提供される関数オブジェクトに格納されている型 `key_compare` のオブジェクト **comp** を使って、2 つの要素の並べ替えキー構成要素を比較します。  
  
 セットとマルチセット (キーの値が要素の値と同一である単純なコンテナー) の場合、`value_compare` は `key_compare` と等価です。マップとマルチマップの場合、型 `pair` の要素の値が要素のキーの値と同一ではないため、その 2 つは等価ではありません。  
  
## <a name="example"></a>例  
  `value_compare` の宣言方法や使用方法の例については、[value_comp](../standard-library/map-class.md#value_comp)の例を参照してください。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<map>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [binary_function 構造体](../standard-library/binary-function-struct.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)



