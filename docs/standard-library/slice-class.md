---
title: "slice クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- valarray/std::slice
- slice
- valarray/std::slice::size
- valarray/std::slice::start
- valarray/std::slice::stride
dev_langs:
- C++
helpviewer_keywords:
- slice class
ms.assetid: 00f0b03d-d657-4b81-ba53-5a9034bb2bf2
caps.latest.revision: 23
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
ms.openlocfilehash: 1732814d42a3c20e9c0248d61bd93f830c073bd9
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="slice-class"></a>slice クラス
親 valarray の 1 次元サブセットを定義するために使用する valarray のユーティリティ クラス。 valarray が配列内のすべての要素を持つ 2 次元行列と見なされる場合、スライスにより 2 次元配列のうち 1 次元のベクターが抽出されます。  
  
## <a name="remarks"></a>コメント  
 クラスは、[slice_array](../standard-library/slice-array-class.md) 型のオブジェクトを特徴とするパラメーターを格納します。クラスのスライスのオブジェクトが [valarray](../standard-library/valarray-class.md#op_at)**\<Type>** クラスのオブジェクトの引数として現れる場合、valarray のサブセットは間接的に構築されます。 親の valarray から選択したサブセットを指定する格納値には、以下が含まれています。  
  
-   valarray の開始インデックス。  
  
-   合計の長さ、またはのスライスの要素の数。  
  
-   ストライド、または valarray の後続の要素のインデックス間の距離。  
  
 スライスによって定義されたセットが定数の valarray のサブセットの場合、スライスは新しい valarray です。 スライスによって定義されたセットが非定数の valarray のサブセットの場合、スライスには元の valarray に対する参照セマンティクスが含まれます。 非定数 valarray の評価メカニズムを使用すると、時間とメモリを節約できます。  
  
 valarray での操作は、スライスによって定義されたソースとターゲットのサブセットが同じでなく、すべてのインデックスが有効な場合にのみ保証されます。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[slice](#slice)|等間隔で離れ、指定した要素で開始する多数の要素で構成する `valarray` のサブセットを定義します。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[size](#size)|`valarray` のスライスにある要素の数を調べます。|  
|[start](#start)|`valarray` のスライスの開始インデックスを検索します。|  
|[stride](#stride)|`valarray` のスライスにある要素間の距離を検索します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<valarray>  
  
 **名前空間:** std  
  
##  <a name="size"></a>  slice::size  
 valarray のスライスにある要素の数を調べます。  
  
```  
size_t size() const;
```  
  
### <a name="return-value"></a>戻り値  
 valarray のスライスにある要素の数。  
  
### <a name="example"></a>例  
  
```cpp  
// slice_size.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   size_t sizeVA, sizeVAR;  
  
   valarray<int> va ( 20 ), vaResult;  
   for ( i = 0 ; i < 20 ; i += 1 )  
      va [ i ] =  i+1;  
  
   cout << "The operand valarray va is:\n ( ";  
      for ( i = 0 ; i < 20 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
  
   sizeVA = va.size ( );  
   cout << "The size of the valarray is: "  
        << sizeVA << "." << endl << endl;  
  
   slice vaSlice ( 3 , 6 , 3 );  
   vaResult = va [ vaSlice ];  
  
   cout << "The slice of valarray va is vaResult = "  
        << "va[slice( 3, 6, 3)] =\n ( ";  
      for ( i = 0 ; i < 6 ; i++ )  
         cout << vaResult [ i ] << " ";  
   cout << ")." << endl;  
  
   sizeVAR = vaSlice.size ( );  
   cout << "The size of slice vaSlice is: "  
        << sizeVAR << "." << endl;  
}  
```  
  
```Output  
The operand valarray va is:  
 ( 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 ).  
The size of the valarray is: 20.  
  
The slice of valarray va is vaResult = va[slice( 3, 6, 3)] =  
 ( 4 7 10 13 16 19 ).  
The size of slice vaSlice is: 6.  
```  
  
##  <a name="slice"></a>  slice::slice  
 等間隔で離れ、指定した要素で開始する多数の要素で構成する valarray のサブセットを定義します。  
  
```  
slice();

slice(
    size_t _StartIndex,  
    size_t _Len,   
    size_t stride);
```  
  
### <a name="parameters"></a>パラメーター  
 `_StartIndex`  
 サブセットの最初の要素の valarray インデックス。  
  
 `_Len`  
 サブセット内の要素数。  
  
 `stride`  
 サブセット内の要素間の距離。  
  
### <a name="return-value"></a>戻り値  
 既定のコンストラクターは、開始インデックス、長さの合計、およびストライドに対して 0 を格納します。 2 番目のコンストラクターは、開始インデックスには `_StartIndex`、長さの合計には `_Len`、ストライドには `stride` を格納します。  
  
### <a name="remarks"></a>コメント  
 ストライドは負となる場合があります。  
  
### <a name="example"></a>例  
  
```cpp  
// slice_ctor.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> va ( 20 ), vaResult;  
   for ( i = 0 ; i < 20 ; i+=1 )  
      va [ i ] =  2 * (i + 1 );  
  
   cout << "The operand valarray va is:\n( ";  
      for ( i = 0 ; i < 20 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
  
   slice vaSlice ( 1 , 7 , 3 );  
   vaResult = va [ vaSlice ];  
  
   cout << "\nThe slice of valarray va is vaResult:"  
        << "\nva[slice( 1, 7, 3)] = ( ";  
      for ( i = 0 ; i < 7 ; i++ )  
         cout << vaResult [ i ] << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The operand valarray va is:  
( 2 4 6 8 10 12 14 16 18 20 22 24 26 28 30 32 34 36 38 40 ).  
  
The slice of valarray va is vaResult:  
va[slice( 1, 7, 3)] = ( 4 10 16 22 28 34 40 ).  
```  
  
##  <a name="start"></a>  slice::start  
 valarray のスライスの開始インデックスを検索します。  
  
```  
size_t start() const;
```  
  
### <a name="return-value"></a>戻り値  
 valarray のスライスの開始インデックス。  
  
### <a name="example"></a>例  
  
```cpp  
// slice_start.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   size_t startVAR;  
  
   valarray<int> va ( 20 ), vaResult;  
   for ( i = 0 ; i < 20 ; i += 1 )  
      va [ i ] = i+1;  
  
   cout << "The operand valarray va is:\n ( ";  
      for ( i = 0 ; i < 20 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
  
   slice vaSlice ( 3 , 6 , 3 );  
   vaResult = va [ vaSlice ];  
  
   cout << "The slice of valarray va is vaResult = "  
        << "va[slice( 3, 6, 3)] =\n ( ";  
      for ( i = 0 ; i < 6 ; i++ )  
         cout << vaResult [ i ] << " ";  
   cout << ")." << endl;  
  
   startVAR = vaSlice.start ( );  
   cout << "The start index of slice vaSlice is: "  
        << startVAR << "." << endl;  
}  
```  
  
```Output  
The operand valarray va is:  
 ( 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 ).  
The slice of valarray va is vaResult = va[slice( 3, 6, 3)] =  
 ( 4 7 10 13 16 19 ).  
The start index of slice vaSlice is: 3.  
```  
  
##  <a name="stride"></a>  slice::stride  
 valarray のスライスにある要素間の距離を検索します。  
  
```  
size_t stride() const;
```  
  
### <a name="return-value"></a>戻り値  
 valarray のスライスにある要素間の距離。  
  
### <a name="example"></a>例  
  
```cpp  
// slice_stride.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   size_t strideVAR;  
  
   valarray<int> va ( 20 ), vaResult;  
   for ( i = 0 ; i < 20 ; i += 1 )  
      va [ i ] =  3 * ( i + 1 );  
  
   cout << "The operand valarray va is:\n ( ";  
      for ( i = 0 ; i < 20 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
  
   slice vaSlice ( 4 , 5 , 3 );  
   vaResult = va [ vaSlice ];  
  
   cout << "The slice of valarray va is vaResult = "  
        << "va[slice( 4, 5, 3)] =\n ( ";  
      for ( i = 0 ; i < 5 ; i++ )  
         cout << vaResult [ i ] << " ";  
   cout << ")." << endl;  
  
   strideVAR = vaSlice.stride ( );  
   cout << "The stride of slice vaSlice is: "  
        << strideVAR << "." << endl;  
}  
```  
  
```Output  
The operand valarray va is:  
 ( 3 6 9 12 15 18 21 24 27 30 33 36 39 42 45 48 51 54 57 60 ).  
The slice of valarray va is vaResult = va[slice( 4, 5, 3)] =  
 ( 15 24 33 42 51 ).  
The stride of slice vaSlice is: 3.  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)

