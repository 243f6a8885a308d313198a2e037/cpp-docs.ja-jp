---
title: "binary_negate クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xfunctional/std::binary_negate
dev_langs:
- C++
helpviewer_keywords:
- binary_negate class
ms.assetid: 7b86f02c-af7e-4c7f-9df1-08addae4dd65
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5b645d0bb6e4efc4fe3cc2850a318ddea994306b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="binarynegate-class"></a>binary_negate クラス
指定した二項関数の戻り値を否定するメンバー関数を提供するテンプレート クラス。  
  
## <a name="syntax"></a>構文  
  
```
template <class Operation>
class binary_negate
    : public binaryFunction <typename Operation::first_argument_type,
                              typename Operation::second_argument_type, bool>
{
public:    
    explicit binary_negate(const Operation& Func);
    bool operator()(const typename Operation::first_argument_type& left,
                    const typename Operation::second_argument_type& right) const;
};
```  
  
#### <a name="parameters"></a>パラメーター  
 `Func`  
 否定する二項関数。  
  
 `left`  
 否定する二項関数の左オペランド。  
  
 `right`  
 否定する二項関数の右オペランド。  
  
## <a name="return-value"></a>戻り値  
 二項関数の否定。  
  
## <a name="remarks"></a>コメント  
 このテンプレート クラスは、二項関数オブジェクト _ *Func* のコピーを格納します。 そのメンバー関数 `operator()` は **!**\_*Func(left, right) を返すように定義されています。*  
  
 `binary_negate` のコンストラクターが直接使用されることはほとんどありません。 **binary_negator** アダプター述語を宣言し、使用するとき、通常、ヘルパー関数 [not2](../standard-library/functional-functions.md#not2) が選択されます。  
  
## <a name="example"></a>例  
  
```cpp  
// functional_binary_negate.cpp  
// compile with: /EHsc  
#define _CRT_RAND_S  
#include <stdlib.h>  
  
#include <vector>  
#include <algorithm>  
#include <functional>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector <unsigned int> v1;  
   vector <unsigned int>::iterator Iter1;  
  
   unsigned int i;  
   v1.push_back( 6262 );  
   v1.push_back( 6262 );  
   unsigned int randVal = 0;  
   for ( i = 0 ; i < 5 ; i++ )  
   {  
      rand_s(&randVal);  
      v1.push_back( randVal );  
   }  
  
   cout << "Original vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   // To sort in ascending order,  
   // use default binary predicate less<unsigned int>( )  
   sort( v1.begin( ), v1.end( ) );  
   cout << "Sorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   // To sort in descending order,  
   // use the binary_negate function  
   sort( v1.begin( ), v1.end( ),  
   binary_negate<less<unsigned int> >(less<unsigned int>( ) ) );  
  
   // The helper function not2 could also have been used  
   // in the above line and is usually preferred for convenience  
   // sort( v1.begin( ), v1.end( ), not2(less<unsigned int>( ) ) );  
  
   cout << "Resorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
}  
\* Output:   
Original vector v1 = ( 6262 6262 2233879413 2621500314 580942933 3715465425 3739828298 )  
Sorted vector v1 = ( 6262 6262 580942933 2233879413 2621500314 3715465425 3739828298 )  
Resorted vector v1 = ( 3739828298 3715465425 2621500314 2233879413 580942933 6262 6262 )  
*\  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<関数型>  
  
 std  
  
## <a name="see-also"></a>参照  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)



