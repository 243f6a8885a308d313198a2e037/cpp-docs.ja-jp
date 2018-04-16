---
title: "&lt;hash_map&gt; 演算子 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- hash_map/std::operator!=
- hash_map/std::operator==
dev_langs:
- C++
ms.assetid: 24b9bb9e-e983-4060-bce5-2c7c8161ee61
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: 9a1d27828908faa779101be4727e50d46a059fc2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="lthashmapgt-operators"></a>&lt;hash_map&gt; 演算子
|||  
|-|-|  
|[operator!=](#op_neq)|[operator!= (multimap)](#op_neq_mm)|
|[operator==](#op_eq_eq)|[operator== (multimap)](#op_eq_eq_mm)|
  
##  <a name="op_neq"></a>  operator!=  
  
> [!NOTE]
>  この API は、互換性のために残されています。 代わりに、[unordered_map クラス](unordered-map-class.md)を使用してください。  
  
 演算子の左辺の hash_map オブジェクトが右辺の hash_map オブジェクトと等しくないかどうかを調べます。  
  
```  
bool operator!=(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 `hash_map` 型のオブジェクト。  
  
 `right`  
 `hash_map` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 hash_maps が等しくない場合は **true**、hash_maps が等しい場合は **false**。  
  
### <a name="remarks"></a>コメント  
 hash_map オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つの hash_maps は、同じ数の要素を持ち、各要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。  
  
 メンバー、 [< hash_map >](hash-map.md)と[< hash_set >](hash-set.md)でファイルのヘッダー、 [ stdext Namespace](stdext-namespace.md)です。  
  
### <a name="example"></a>例  
  
```cpp  
// hash_map_op_ne.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1, hm2, hm3;  
   int i;  
   typedef pair <int, int> Int_Pair;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      hm1.insert ( Int_Pair ( i, i ) );  
      hm2.insert ( Int_Pair ( i, i * i ) );  
      hm3.insert ( Int_Pair ( i, i ) );  
   }  
  
   if ( hm1 != hm2 )  
      cout << "The hash_maps hm1 and hm2 are not equal." << endl;  
   else  
      cout << "The hash_maps hm1 and hm2 are equal." << endl;  
  
   if ( hm1 != hm3 )  
      cout << "The hash_maps hm1 and hm3 are not equal." << endl;  
   else  
      cout << "The hash_maps hm1 and hm3 are equal." << endl;  
}  
```  
  
```Output  
The hash_maps hm1 and hm2 are not equal.  
The hash_maps hm1 and hm3 are equal.  
```  
  
##  <a name="op_eq_eq"></a>  operator== 
  
> [!NOTE]
>  この API は、互換性のために残されています。 代わりに、[unordered_map クラス](unordered-map-class.md)を使用してください。  
  
 演算子の左辺の hash_map オブジェクトが右辺の hash_map オブジェクトと等しいかどうかを調べます。  
  
```  
bool operator==(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 `hash_map` 型のオブジェクト。  
  
 `right`  
 `hash_map` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 演算子の左辺の hash_map が演算子の右辺の hash_map と等しい場合は **true**、それ以外の場合は **false**。  
  
### <a name="remarks"></a>コメント  
 hash_map オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つの hash_maps は、同じ数の要素を持ち、各要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。  
    
### <a name="example"></a>例  
  
```cpp  
// hash_map_op_eq.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1, hm2, hm3;  
   int i;  
   typedef pair <int, int> Int_Pair;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      hm1.insert ( Int_Pair ( i, i ) );  
      hm2.insert ( Int_Pair ( i, i * i ) );  
      hm3.insert ( Int_Pair ( i, i ) );  
   }  
  
   if ( hm1 == hm2 )  
      cout << "The hash_maps hm1 and hm2 are equal." << endl;  
   else  
      cout << "The hash_maps hm1 and hm2 are not equal." << endl;  
  
   if ( hm1 == hm3 )  
      cout << "The hash_maps hm1 and hm3 are equal." << endl;  
   else  
      cout << "The hash_maps hm1 and hm3 are not equal." << endl;  
}  
```  
  
```Output  
The hash_maps hm1 and hm2 are not equal.  
The hash_maps hm1 and hm3 are equal.  
```  
  
##  <a name="op_neq_mm"></a>  operator! = (hash_multimap) 
  
> [!NOTE]
>  この API は、互換性のために残されています。 代替が必要な場合は、[unordered_multimap クラス](unordered-multimap-class.md)をご使用ください。  
  
 演算子の左側の hash_multimap オブジェクトが右側の hash_multimap オブジェクトと等しくないかどうかをテストします。  
  
```  
bool operator!=(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 `hash_multimap` 型のオブジェクト。  
  
 `right`  
 `hash_multimap` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 hash_multimaps が等しくない場合は **true**、hash_multimaps が等しい場合は **false**。  
  
### <a name="remarks"></a>コメント  
 hash_multimap オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つの hash_multimaps は、同じ数の要素を持ち、各要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。  
   
### <a name="example"></a>例  
  
```cpp  
// hash_multimap_op_ne.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap <int, int> hm1, hm2, hm3;  
   int i;  
   typedef pair <int, int> Int_Pair;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      hm1.insert ( Int_Pair ( i, i ) );  
      hm2.insert ( Int_Pair ( i, i * i ) );  
      hm3.insert ( Int_Pair ( i, i ) );  
   }  
  
   if ( hm1 != hm2 )  
      cout << "The hash_multimaps hm1 and hm2 are not equal." << endl;  
   else  
      cout << "The hash_multimaps hm1 and hm2 are equal." << endl;  
  
   if ( hm1 != hm3 )  
      cout << "The hash_multimaps hm1 and hm3 are not equal." << endl;  
   else  
      cout << "The hash_multimaps hm1 and hm3 are equal." << endl;  
}  
```  
  
```Output  
The hash_multimaps hm1 and hm2 are not equal.  
The hash_multimaps hm1 and hm3 are equal.  
```  
  
##  <a name="op_eq_eq_mm"></a>  演算子 = = (hash_multimap)
  
> [!NOTE]
>  この API は、互換性のために残されています。 代替が必要な場合は、[unordered_multimap クラス](unordered-multimap-class.md)をご使用ください。  
  
 演算子の左側の hash_multimap オブジェクトが右側の hash_multimap オブジェクトと等しいかどうかをテストします。  
  
```  
bool operator==(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `left`  
 `hash_multimap` 型のオブジェクト。  
  
 `right`  
 `hash_multimap` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 演算子の左辺の hash_multimap が演算子の右辺の hash_multimap と等しい場合は **true**、それ以外の場合は **false**。  
  
### <a name="remarks"></a>コメント  
 hash_multimap オブジェクト間の比較は、要素のペアの比較に基づいています。 2 つの hash_multimaps は、同じ数の要素を持ち、各要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。  
  
### <a name="example"></a>例  
  
```cpp  
// hash_multimap_op_eq.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap<int, int> hm1, hm2, hm3;  
   int i;  
   typedef pair<int, int> Int_Pair;  
  
   for (i = 0; i < 3; i++)  
   {  
      hm1.insert(Int_Pair(i, i));  
      hm2.insert(Int_Pair(i, i*i));  
      hm3.insert(Int_Pair(i, i));  
   }  
  
   if ( hm1 == hm2 )  
      cout << "The hash_multimaps hm1 and hm2 are equal." << endl;  
   else  
      cout << "The hash_multimaps hm1 and hm2 are not equal." << endl;  
  
   if ( hm1 == hm3 )  
      cout << "The hash_multimaps hm1 and hm3 are equal." << endl;  
   else  
      cout << "The hash_multimaps hm1 and hm3 are not equal." << endl;  
}  
```  
  
```Output  
The hash_multimaps hm1 and hm2 are not equal.  
The hash_multimaps hm1 and hm3 are equal.  
```  
  
## <a name="see-also"></a>参照  
 [<hash_map>](hash-map.md)

