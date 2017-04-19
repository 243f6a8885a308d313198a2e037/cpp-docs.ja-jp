---
title: "insert_iterator クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iterator/std::insert_iterator
- insert_iterator
- iterator/std::insert_iterator::container_type
- iterator/std::insert_iterator::reference
dev_langs:
- C++
helpviewer_keywords:
- insert_iterator class
- insert_iterator class, syntax
ms.assetid: d5d86405-872e-4e3b-9e68-c69a2b7e8221
caps.latest.revision: 17
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
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 9ff1d22bafa778db24fb489d33e83b1a553711e5
ms.lasthandoff: 02/24/2017

---
# <a name="insertiterator-class"></a>insert_iterator クラス
出力反復子の要件を満たす反復子アダプターについて説明します。 シーケンスに要素を上書きではなく、挿入し、C++ のシーケンスと連想コンテナーの反復子が提供する上書きセマンティクスとは異なるセマンティクスを提供します。 `insert_iterator` クラスは、適合させるコンテナーの型でテンプレート化されます。  
  
## <a name="syntax"></a>構文  
  
```
template <class Container>  
class insert_iterator;
```  
  
#### <a name="parameters"></a>パラメーター  
 `Container`  
 要素が `insert_iterator` によって挿入されるコンテナーの型。  
  
## <a name="remarks"></a>コメント  
 **Container** 型のコンテナーは、可変サイズのコンテナーの要件を満たし、2 つの引数を取る insert メンバー関数を備えている必要があります。このメンバー関数のパラメーターは **Container::iterator** 型と **Container::value_type** 型で、**Container::iterator** 型を返します。 C++ 標準ライブラリ シーケンスおよび並べ替えられた連想コンテナーはこれらの要件を満たしており、`insert_iterator` で使用するために適合させることができます。 連想コンテナーでは、位置の引数はヒントとして扱われ、ヒントの品質に応じてパフォーマンスを向上させる場合も、低下させる場合もあります。 `insert_iterator` は、常に、コンテナーで初期化されている必要があります。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[insert_iterator](#insert_iterator__insert_iterator)|コンテナーの指定された位置に要素を挿入する `insert_iterator` を構築します。|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[container_type](#insert_iterator__container_type)|一般的な挿入の対象となるコンテナーを表す型。|  
|[reference](#insert_iterator__reference)|関連するコンテナーによって制御されるシーケンスの要素への参照を提供する型。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator*](#insert_iterator__operator_star)|一般的な挿入のための出力反復子式 * `i` = `x` を実装するために使用される逆参照演算子。|  
|[operator++](#insert_iterator__operator_add_add)|値を格納できる次の位置に `insert_iterator` をインクリメントします。|  
|[operator=](#insert_iterator__operator_eq)|一般的な挿入のための出力反復子式 * `i` = `x` を実装するために使用される代入演算子。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー**: \<iterator>  
  
 **名前空間:** std  
  
##  <a name="insert_iterator__container_type"></a>  insert_iterator::container_type  
 一般的な挿入の対象となるコンテナーを表す型。  
  
```
typedef Container container_type;
```  
  
### <a name="remarks"></a>コメント  
 この型は、テンプレート パラメーター **Container** のシノニムです。  
  
### <a name="example"></a>例  
  
```cpp  
// insert_iterator_container_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L1;  
   insert_iterator<list<int> >::container_type L2 = L1;  
   inserter ( L2, L2.end ( ) ) = 20;  
   inserter ( L2, L2.end ( ) ) = 10;  
   inserter ( L2, L2.begin ( ) ) = 40;  
  
   list <int>::iterator vIter;  
   cout << "The list L2 is: ( ";  
   for ( vIter = L2.begin ( ) ; vIter != L2.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L2 is: ( 40 20 10 ).  
*\  
```  
  
##  <a name="insert_iterator__insert_iterator"></a>  insert_iterator::insert_iterator  
 コンテナーの指定された位置に要素を挿入する `insert_iterator` を構築します。  
  
```
insert_iterator(Container& _Cont, typename Container::iterator _It);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Cont`  
 `insert_iterator` によって要素が挿入されるコンテナ―です。  
  
 `_It`  
 挿入の位置。  
  
### <a name="remarks"></a>コメント  
 すべてのコンテナーには、`insert_iterator`によって呼び出される insert メンバー関数があります。 連想コンテナーについては、位置パラメーターは参考にすぎません。 Inserter 関数は、値を挿入する便利な手段となります。  
  
### <a name="example"></a>例  
  
```cpp  
// insert_iterator_insert_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   list <int>::iterator L_Iter;  
  
   list<int> L;  
   for (i = 1 ; i < 4 ; ++i )    
   {  
      L.push_back ( 10 * i );  
   }  
  
   cout << "The list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++)  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
  
   // Using the member function to insert an element  
   inserter ( L, L.begin ( ) ) = 2;  
  
   // Alternatively, you may use the template version  
   insert_iterator< list < int> > Iter(L, L.end ( ) );  
 *Iter = 300;  
  
   cout << "After the insertions, the list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++ )  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The list L is:  
 ( 10 20 30 ).  
After the insertions, the list L is:  
 ( 2 10 20 30 300 ).  
*\  
```  
  
##  <a name="insert_iterator__operator_star"></a>  insert_iterator::operator*  
 アドレス指定された要素を返す挿入反復子を逆参照します。  
  
```
insert_iterator<Container>& operator*();
```  
  
### <a name="return-value"></a>戻り値  
 このメンバー関数は、アドレス指定された要素の値を返します。  
  
### <a name="remarks"></a>コメント  
 出力反復子式 **\*Iter** = **value** を実装するために使用されます。 **Iter** がシーケンス内の要素をアドレス指定する反復子である場合、**\*Iter** = **value** はその要素を値に置き換え、シーケンス内の要素の合計数は変えません。  
  
### <a name="example"></a>例  
  
```cpp  
// insert_iterator_op_deref.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   list <int>::iterator L_Iter;  
  
   list<int> L;  
   for (i = 0 ; i < 4 ; ++i )    
   {  
      L.push_back ( 2 * i );  
   }  
  
   cout << "The original list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++ )  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
  
   insert_iterator< list < int> > Iter(L, L.begin ( ) );  
 *Iter = 10;  
 *Iter = 20;  
 *Iter = 30;  
  
   cout << "After the insertions, the list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++ )  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The original list L is:  
 ( 0 2 4 6 ).  
After the insertions, the list L is:  
 ( 10 20 30 0 2 4 6 ).  
*\  
```  
  
##  <a name="insert_iterator__operator_add_add"></a>  insert_iterator::operator++  
 値を格納できる次の位置に **insert_iterator** をインクリメントします。  
  
```
insert_iterator<Container>& operator++();

insert_iterator<Container> operator++(int);
```  
  
### <a name="parameters"></a>パラメーター  
 値を格納できる次の位置をアドレス指定する `insert_iterator`。  
  
### <a name="remarks"></a>コメント  
 preincrementation と postincrementation の演算子は、どちらも同じ結果を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// insert_iterator_op_incr.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   vector<int> vec;  
   for (i = 1 ; i < 5 ; ++i )   
   {  
      vec.push_back (  i );  
   }  
  
   vector <int>::iterator vIter;  
   cout << "The vector vec is:\n ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   insert_iterator<vector<int> > ii ( vec, vec.begin ( ) );  
 *ii = 30;  
   ii++;  
 *ii = 40;  
   ii++;  
 *ii = 50;  
  
   cout << "After the insertions, the vector vec becomes:\n ( ";  
   for ( vIter = vec.begin ( ) ; vIter != vec.end ( ); vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The vector vec is:  
 ( 1 2 3 4 ).  
After the insertions, the vector vec becomes:  
 ( 30 40 50 1 2 3 4 ).  
*\  
```  
  
##  <a name="insert_iterator__operator_eq"></a>  insert_iterator::operator=  
 コンテナーに値を挿入し、新しい要素を指すように更新された反復子を返します。  
  
```
insert_iterator<Container>& operator=(
    typename Container::const_reference val,);

insert_iterator<Container>& operator=(
    typename Container::value_type&& val);
```  
  
### <a name="parameters"></a>パラメーター  
 `val`  
 コンテナーに割り当てられる値。  
  
### <a name="return-value"></a>戻り値  
 コンテナーに挿入される要素への参照。  
  
### <a name="remarks"></a>コメント  
 1 つ目のメンバー演算子は次の評価をします。  
  
 `Iter = container->insert(Iter, val)`;  
  
 `++Iter;`  
  
 そして `*this`を返します。  
  
 2 つ目のメンバー演算子は次の評価をします。  
  
 `Iter = container->insert(Iter, std::move(val));`  
  
 `++Iter;`  
  
 そして `*this`を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// insert_iterator_op_assign.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   list <int>::iterator L_Iter;  
  
   list<int> L;  
   for (i = 0 ; i < 4 ; ++i )   
   {  
      L.push_back ( 2 * i );  
   }  
  
   cout << "The original list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++ )  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
  
   insert_iterator< list < int> > Iter(L, L.begin ( ) );  
 *Iter = 10;  
 *Iter = 20;  
 *Iter = 30;  
  
   cout << "After the insertions, the list L is:\n ( ";  
   for ( L_Iter = L.begin( ) ; L_Iter != L.end( ); L_Iter++ )  
      cout << *L_Iter << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The original list L is:  
 ( 0 2 4 6 ).  
After the insertions, the list L is:  
 ( 10 20 30 0 2 4 6 ).  
*\  
```  
  
##  <a name="insert_iterator__reference"></a>  insert_iterator::reference  
 関連するコンテナーによって制御されるシーケンスの要素への参照を提供する型。  
  
```
typedef typename Container::reference reference;
```  
  
### <a name="remarks"></a>コメント  
 この型は、関連するコンテナーによって制御されるシーケンスの要素への参照を示します。  
  
### <a name="example"></a>例  
  
```cpp  
// insert_iterator_container_reference.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <list>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   list<int> L;  
   insert_iterator<list<int> > iivIter( L , L.begin ( ) );  
 *iivIter = 10;  
 *iivIter = 20;  
 *iivIter = 30;  
  
   list<int>::iterator LIter;  
   cout << "The list L is: ( ";  
   for ( LIter = L.begin ( ) ; LIter != L.end ( ); LIter++ )  
      cout << *LIter << " ";  
   cout << ")." << endl;  
  
   insert_iterator<list<int> >::reference   
        RefFirst = *(L.begin ( ));  
   cout << "The first element in the list L is: "   
        << RefFirst << "." << endl;  
}  
\* Output:   
The list L is: ( 10 20 30 ).  
The first element in the list L is: 10.  
*\  
```  
  
## <a name="see-also"></a>関連項目  
 [\<iterator>](../standard-library/iterator.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)




