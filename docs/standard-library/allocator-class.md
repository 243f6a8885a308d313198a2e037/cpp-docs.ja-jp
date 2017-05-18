---
title: "allocator クラス |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocator
- memory/std::allocator
- memory/std::allocator::const_pointer
- memory/std::allocator::const_reference
- memory/std::allocator::difference_type
- memory/std::allocator::pointer
- memory/std::allocator::reference
- memory/std::allocator::size_type
- memory/std::allocator::value_type
- memory/std::allocator::address
- memory/std::allocator::allocate
- memory/std::allocator::construct
- memory/std::allocator::deallocate
- memory/std::allocator::destroy
- memory/std::allocator::max_size
- memory/std::allocator::rebind
dev_langs:
- C++
helpviewer_keywords:
- allocator class
ms.assetid: 3fd58076-56cc-43bb-ad58-b4b7c9c6b410
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: a2447e0e42cc0a7fdc22db9de415f6dde46c40a5
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="allocator-class"></a>allocator クラス
このテンプレート クラスは、**Type** 型のオブジェクトの配列に対し、ストレージの割り当てと解放を管理するオブジェクトを記述します。 **allocator** クラスのオブジェクトは、C++ 標準ライブラリのいくつかのコンテナー テンプレート クラスのコンストラクターで指定されている既定のアロケーター オブジェクトです。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Type>  
class allocator  
```  
  
#### <a name="parameters"></a>パラメーター  
 *Type*  
 ストレージが割り当てまたは割り当て解除されるオブジェクトの型。  
  
## <a name="remarks"></a>コメント  
 すべての C++ 標準ライブラリのコンテナーには、**allocator** を既定値として持つテンプレート パラメーターがあります。 カスタム アロケーターを持つコンテナーを作成すると、そのコンテナーの要素の割り当てと解放を制御できます。  
  
 たとえば、アロケーター オブジェクトは、プライベート ヒープまたは共有メモリ内でストレージを割り当てたり、小さなまたは大きなオブジェクトのサイズ用に最適化したりできます。 さらに、種類の型定義を介して、共有メモリを管理する特殊なアクセサー オブジェクトを経由で要素にアクセスすること、または自動ガベージ コレクションを実行することを指定できます。 そのため、アロケーター オブジェクトを使用してストレージを割り当てるクラスでは、C++ 標準ライブラリのコンテナーと同様に、これらの型を使用してポインターおよび参照オブジェクトを宣言する必要があります。  
  
 **(C_++98/03 のみ)** allocator クラスから派生するときは、`_Other` typedef で新しく派生するクラスを参照する [rebind](#rebind) 構造体を指定する必要があります。  
  
 したがって、アロケーターは、次の型を定義します。  
  
- [pointer](#pointer) は、**Type** へのポインターのように動作します。  
  
- [const_pointer](#const_pointer) は、**Type** への const ポインターのように動作します。  
  
- [reference](#reference) は、**Type** の参照のように動作します。  
  
- [const_reference](#const_reference) は、**Type** の定数参照のように動作します。  
  
 これらの **Type** は、割り当てられる要素に対してポインターと参照が従う必要がある形式を指定します  (**allocator** クラスの明確な定義があるにもかかわらず、[allocator::pointer](#pointer) は、必ずしもすべてのアロケーター オブジェクトで **Type**\* と同じではありません)。  
  
 **C++ 11 以降:** アロケーターでの移動操作を有効にするには、最小限のアロケーター インターフェイスを使用し、さらにコピー コンストラクター、== 演算子、! = 演算子、allocate、および deallocate を実装します。 詳細および例については、「[アロケーター](../standard-library/allocators.md)」を参照してください。  
  
## <a name="members"></a>メンバー  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[allocator](#allocator)|`allocator` オブジェクトを作成するために使用するコンストラクター。|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[const_pointer](#const_pointer)|アロケーターによって管理されるオブジェクトの型に対する定数ポインターを提供する型。|  
|[const_reference](#const_reference)|アロケーターによって管理されるオブジェクトの型に対する定数参照を提供する型。|  
|[difference_type](#difference_type)|アロケーターによって管理されるオブジェクトの型に対するポインターの値の差を表すことができる符号付き整数型。|  
|[pointer](#pointer)|アロケーターによって管理されるオブジェクトの型に対するポインターを提供する型。|  
|[reference](#reference)|アロケーターによって管理されるオブジェクトの型に対する参照を提供する型。|  
|[size_type](#size_type)|テンプレート クラス `allocator` のオブジェクトが割り当てることができる、シーケンスの長さを表すことのできる符号なし整数型。|  
|[value_type](#value_type)|アロケーターによって管理される型。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[address](#address)|値が指定されたオブジェクトのアドレスを検索します。|  
|[allocate](#allocate)|指定された要素数だけは格納できるメモリのブロックを割り当てます。|  
|[construct](#construct)|指定された値で初期化され、指定されたアドレスに配置される、指定された型のオブジェクトを構築します。|  
|[deallocate](#deallocate)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|  
|[destroy](#destroy)|オブジェクトが格納されたメモリの割り当てを解除せずに、オブジェクトのデストラクターを呼び出します。|  
|[max_size](#max_size)|空きメモリがすべて使用される前に `allocator` クラスによって割り当てることのできる、型 `Type` の要素の数を返します。|  
|[rebind](#rebind)|1 つの型のオブジェクトのアロケーターを使用して別の型のオブジェクトのストレージの割り当てを可能にする構造体。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator=](#op_eq)|`allocator` オブジェクトを別の `allocator` オブジェクトに割り当てます。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<memory>  
  
 **名前空間:** std  
  
##  <a name="address"></a>  allocator::address  
 値が指定されたオブジェクトのアドレスを検索します。  
  
```  
pointer address(reference val) const;
const_pointer address(const_reference val) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `val`  
 アドレスが検索対象となっているオブジェクトの const 値または nonconst 値。  
  
### <a name="return-value"></a>戻り値  
 見つかった const 値または nonconst 値のそれぞれのオブジェクトに対する const ポインターまたは nonconst ポインター。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、割り当てられた要素のためにポインターが取得しなければならない形式で、`val` のアドレスを返します。  
  
### <a name="example"></a>例  
  
```cpp  
// allocator_address.cpp  
// compile with: /EHsc  
#include <memory>  
#include <algorithm>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 1 ; i <= 7 ; i++ )  
   {  
      v1.push_back( 2 * i );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   allocator<int>::const_pointer v1Ptr;  
   const int k = 8;  
   v1Ptr = v1Alloc.address( *find(v1.begin( ), v1.end( ), k) );  
   // v1Ptr = v1Alloc.address( k );  
   cout << "The integer addressed by v1Ptr has a value of: "  
        << "*v1Ptr = " << *v1Ptr << "." << endl;  
}  
```  
  
```Output  
The original vector v1 is:  
 ( 2 4 6 8 10 12 14 ).  
The integer addressed by v1Ptr has a value of: *v1Ptr = 8.  
```  
  
##  <a name="allocate"></a>  allocator::allocate  
 指定された要素数だけは格納できるメモリのブロックを割り当てます。  
  
```  
pointer allocate(size_type count, const void* _Hint);
```  
  
### <a name="parameters"></a>パラメーター  
 `count`  
 十分な記憶域を割り当てる要素の数。  
  
 *_Hint*  
 アロケーター オブジェクトを支援できる const ポインターは、記憶域への要求を、要求の前に割り当てられたオブジェクトのアドレスを見つけることで満たします。  
  
### <a name="return-value"></a>戻り値  
 割り当てられたオブジェクトへのポインター、またはメモリが割り当てられていない場合は null。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、演算子 new( `count`) を呼び出すことで、**Type** 型の count 要素の配列に対し、記憶域を割り当てます。 この関数は、割り当てられたオブジェクトへのポインターを返します。 hint 引数は、参照の局所性を向上することにおいて、一部のアロケーターに役立ちます。有効な選択肢は、同じアロケーターによって以前に割り当てられ、まだ割り当て解除されていないオブジェクトのアドレスです。 hint を指定しない場合は、代わりに Null ポインター引数を使用します。  
  
### <a name="example"></a>例  
  
```cpp  
// allocator_allocate.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   allocator<int> v1Alloc;    
   allocator<int>::pointer v1aPtr;    
   v1aPtr = v1Alloc.allocate ( 10 );  
  
   int i;  
   for ( i = 0 ; i < 10 ; i++ )  
   {  
      v1aPtr[ i ] = i;  
   }  
  
   for ( i = 0 ; i < 10 ; i++ )  
   {  
      cout << v1aPtr[ i ] << " ";  
   }  
   cout << endl;    
   v1Alloc.deallocate( v1aPtr, 10 );  
}  
```  
  
```Output  
0 1 2 3 4 5 6 7 8 9   
```  
  
##  <a name="allocator"></a>  allocator::allocator  
 オブジェクトを割り当てるために使用するコンストラクター。  
  
```  
allocator();
allocator(const allocator<Type>& right);
template <class Other>  
allocator(const allocator<Other>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `right`  
 コピーするアロケーター オブジェクト。  
  
### <a name="remarks"></a>コメント  
 コンストラクターは何も行いません。 ただし、通常は、別のアロケーター オブジェクトから構築されたアロケーター オブジェクトは、それと等しいことを比較し、オブジェクトの割り当ての混在と、2 つのアロケーター オブジェクト間の解放を許可する必要があります。  
  
### <a name="example"></a>例  
  
```cpp  
// allocator_allocator.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
class Int {  
public:  
   Int( int i )   
   {  
      cout << "Constructing " << ( void* )this  << endl;   
      x = i;  
      bIsConstructed = true;  
   };  
   ~Int( )   
   {  
      cout << "Destructing " << ( void* )this << endl;   
      bIsConstructed = false;  
   };  
   Int &operator++( )   
   {  
      x++;  
      return *this;  
   };  
   int x;  
private:  
   bool bIsConstructed;  
};  
  
int main( )   
{  
   allocator<double> Alloc;  
   vector <Int>:: allocator_type v1Alloc;  
  
   allocator<double> cAlloc(Alloc);   
   allocator<Int> cv1Alloc(v1Alloc);  
  
   if ( cv1Alloc == v1Alloc )  
      cout << "The allocator objects cv1Alloc & v1Alloc are equal."  
           << endl;  
   else  
      cout << "The allocator objects cv1Alloc & v1Alloc are not equal."  
           << endl;  
  
   if ( cAlloc == Alloc )  
      cout << "The allocator objects cAlloc & Alloc are equal."  
           << endl;  
   else  
      cout << "The allocator objects cAlloc & Alloc are not equal."  
           << endl;  
}  
```  
  
```Output  
The allocator objects cv1Alloc & v1Alloc are equal.  
The allocator objects cAlloc & Alloc are equal.  
```  
  
##  <a name="const_pointer"></a>  allocator::const_pointer  
 アロケーターによって管理されるオブジェクトの型に対する定数ポインターを提供する型。  
  
```  
typedef const value_type *const_pointer;  
```  
  
### <a name="remarks"></a>コメント  
 ポインター型は、式 **\*ptr** を通じて指定できるオブジェクト **ptr** を記述します。これは、テンプレート クラス アロケーターのオブジェクトを割り当てることができる任意の const オブジェクトです。  
  
### <a name="example"></a>例  
  
```cpp  
// allocator_const_ptr.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 1 ; i <= 7 ; i++ )  
   {  
      v1.push_back( i * 2 );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   allocator<int>::const_pointer v1Ptr;  
   const int k = 10;  
   v1Ptr = v1Alloc.address( k );  
  
   cout << "The integer's address found has a value of: "  
        << *v1Ptr << "." << endl;  
}  
```  
  
```Output  
The original vector v1 is:  
 ( 2 4 6 8 10 12 14 ).  
The integer's address found has a value of: 10.  
```  
  
##  <a name="const_reference"></a>  allocator::const_reference  
 アロケーターによって管理されるオブジェクトの型に対する定数参照を提供する型。  
  
```  
typedef const value_type& const_reference;  
```  
  
### <a name="remarks"></a>コメント  
 参照型は、テンプレート クラス アロケーターのオブジェクトを割り当てることができる任意の const オブジェクトを指定できるオブジェクトを記述します。  
  
### <a name="example"></a>例  
  
```cpp  
// allocator_const_ref.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <double> v;  
   vector <double> ::iterator vIter, vfIter;  
   vector <double> :: allocator_type vAlloc;  
  
   int j;  
   for ( j = 1 ; j <= 7 ; j++ )  
   {  
      v.push_back( 100.0 * j );  
   }  
  
   cout << "The original vector v is:\n ( " ;  
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vfIter = v.begin( );  
   allocator<double>::const_reference vcref =*vfIter;  
   cout << "The value of the element referred to by vref is: "  
        << vcref << ",\n the first element in the vector." << endl;  
  
   // const references can have their elements modified,  
   // so the following would generate an error:  
   // vcref = 150;  
   // but the value of the first element could be modified through  
   // its nonconst iterator and the const reference would remain valid  
 *vfIter = 175;  
   cout << "The value of the element referred to by vcref,"  
        <<"\n after nofication through its nonconst iterator, is: "  
        << vcref << "." << endl;  
}  
```  
  
```Output  
The original vector v is:  
 ( 100 200 300 400 500 600 700 ).  
The value of the element referred to by vref is: 100,  
 the first element in the vector.  
The value of the element referred to by vcref,  
 after nofication through its nonconst iterator, is: 175.  
```  
  
##  <a name="construct"></a>  allocator::construct  
 指定された値で初期化され、指定されたアドレスに配置される、指定された型のオブジェクトを構築します。  
  
```  
void construct(pointer ptr, const Type& val);
void construct(pointer ptr, Type&& val);
template <class _Other>  
void construct(pointer ptr, _Other&&...   val);
```  
  
### <a name="parameters"></a>パラメーター  
 `ptr`  
 オブジェクトが構築される場所へのポインター。  
  
 `val`  
 構築されるオブジェクトが初期化される値。  
  
### <a name="remarks"></a>コメント  
 最初のメンバー関数は、**new** ( ( `void` \*) `ptr` ) **Type** ( `val` ) と同じです。  
  
### <a name="example"></a>例  
  
```cpp  
// allocator_construct.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <algorithm>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 1 ; i <= 7 ; i++ )  
   {  
      v1.push_back( 3 * i );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   allocator<int>::pointer v1PtrA;  
   int kA = 6, kB = 7;  
   v1PtrA = v1Alloc.address( *find( v1.begin( ), v1.end( ), kA ) );  
   v1Alloc.destroy ( v1PtrA );  
   v1Alloc.construct ( v1PtrA , kB );  
  
   cout << "The modified vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The original vector v1 is:  
 ( 3 6 9 12 15 18 21 ).  
The modified vector v1 is:  
 ( 3 7 9 12 15 18 21 ).  
```  
  
##  <a name="deallocate"></a>  allocator::deallocate  
 指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。  
  
```  
void deallocate(pointer ptr, size_type count);
```  
  
### <a name="parameters"></a>パラメーター  
 `ptr`  
 記憶域から割り当てを解除される最初のオブジェクトへのポインター。  
  
 `count`  
 記憶域から割り当てを解除されるオブジェクトの数。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、型の数のオブジェクトの配列の記憶域を解放**型**始点`ptr`、呼び出すことによって`operator delete(ptr)`です。 ポインター `ptr` は、同じサイズと型の配列オブジェクトを割り当てる **\*this** と等しいことを比較するアロケーター オブジェクトに対し、[allocate](#allocate) を呼び出すことで、既に返されているはずです。 `deallocate` は例外をスローしません。  
  
### <a name="example"></a>例  
  メンバー関数の使用例については、「[allocator::allocate](#allocate)」を参照してください。  
  
##  <a name="destroy"></a>  allocator::destroy  
 オブジェクトが格納されたメモリの割り当てを解除せずに、オブジェクトのデストラクターを呼び出します。  
  
```  
void destroy(pointer ptr);
```  
  
### <a name="parameters"></a>パラメーター  
 `ptr`  
 破棄するオブジェクトのアドレスを指定するポインター。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数によって指定されたオブジェクトを破棄する`ptr`、デストラクターを呼び出すことによって`ptr->`**型**::**~ 型**です。  
  
### <a name="example"></a>例  
  
```cpp  
// allocator_destroy.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <algorithm>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 1 ; i <= 7 ; i++ )  
   {  
      v1.push_back( 2 * i );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   allocator<int>::pointer v1PtrA;  
   int kA = 12, kB = -99;  
   v1PtrA = v1Alloc.address( *find(v1.begin( ), v1.end( ), kA) );  
   v1Alloc.destroy ( v1PtrA );  
   v1Alloc.construct ( v1PtrA , kB );  
  
   cout << "The modified vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The original vector v1 is:  
 ( 2 4 6 8 10 12 14 ).  
The modified vector v1 is:  
 ( 2 4 6 8 10 -99 14 ).  
```  
  
##  <a name="difference_type"></a>  allocator::difference_type  
 アロケーターによって管理されるオブジェクトの型に対するポインターの値の差を表すことができる符号付き整数型。  
  
```  
typedef ptrdiff_t difference_type;  
```  
  
### <a name="remarks"></a>コメント  
 符号付き整数型は、テンプレート クラス アロケーターのオブジェクトが割り当てることができるシーケンス内にある 2 つの要素のアドレスの違いを表すことのできるオブジェクトを記述します。  
  
### <a name="example"></a>例  
  
```cpp  
// allocator_diff_type.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 0 ; i <= 7 ; i++ )  
   {  
      v1.push_back( i * 2 );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   allocator<int>::const_pointer v1PtrA, v1PtrB;  
   const int kA = 4, kB =12;  
   v1PtrA = v1Alloc.address( kA );  
   v1PtrB = v1Alloc.address( kB );  
   allocator<int>::difference_type v1diff = *v1PtrB - *v1PtrA;  
  
   cout << "Pointer v1PtrA addresses " << *v1PtrA << "." << endl;  
   cout << "Pointer v1PtrB addresses " << *v1PtrB <<  "." << endl;  
   cout << "The difference between the integer's addresses is: "  
        << v1diff << "." << endl;  
}  
```  
  
```Output  
The original vector v1 is:  
 ( 0 2 4 6 8 10 12 14 ).  
Pointer v1PtrA addresses 4.  
Pointer v1PtrB addresses 12.  
The difference between the integer's addresses is: 8.  
```  
  
##  <a name="max_size"></a>  allocator::max_size  
 空きメモリがすべて使用される前にクラス アロケーター オブジェクトによって割り当てることのできる、**Type** 型の要素の数を返します。  
  
```  
size_type max_size() const;
```  
  
### <a name="return-value"></a>戻り値  
 割り当てることができる要素の数。  
  
### <a name="example"></a>例  
  
```cpp  
// allocator_max_size.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 1 ; i <= 7 ; i++ )  
   {  
      v1.push_back( i );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   vector <double> v2;  
   vector <double> ::iterator v2Iter;  
   vector <double> :: allocator_type v2Alloc;  
   allocator<int>::size_type v1size;  
   v1size = v1Alloc.max_size( );  
  
   cout << "The number of integers that can be allocated before\n"  
        << " the free memory in the vector v1 is used up is: "  
        << v1size << "." << endl;  
  
   int ii;  
   for ( ii = 1 ; ii <= 7 ; ii++ )  
   {  
      v2.push_back( ii * 10.0 );  
   }  
  
   cout << "The original vector v2 is:\n ( " ;  
   for ( v2Iter = v2.begin( ) ; v2Iter != v2.end( ) ; v2Iter++ )  
      cout << *v2Iter << " ";  
   cout << ")." << endl;  
   allocator<double>::size_type v2size;  
   v2size = v2Alloc.max_size( );  
  
   cout << "The number of doubles that can be allocated before\n"  
        << " the free memory in the vector v2 is used up is: "  
        << v2size << "." << endl;  
}  
```  
  
##  <a name="op_eq"></a>  allocator::operator=  
 1 つのアロケーター オブジェクトを別のアロケーター オブジェクトに割り当てます。  
  
```  
template <class Other>  
allocator<Type>& operator=(const allocator<Other>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `right`  
 このような別のオブジェクトに割り当てられるアロケーター オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 アロケーター オブジェクトへの参照  
  
### <a name="remarks"></a>コメント  
 テンプレートの代入演算子は、何も行いません。 ただし、通常は、別のアロケーター オブジェクトに割り当てられたアロケーター オブジェクトは、それと等しいことを比較し、オブジェクトの割り当ての混在と、2 つのアロケーター オブジェクト間の解放を許可する必要があります。  
  
### <a name="example"></a>例  
  
```cpp  
// allocator_op_assign.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
class Int {  
public:  
   Int(int i)   
   {  
      cout << "Constructing " << ( void* )this  << endl;   
      x = i;  
      bIsConstructed = true;  
   };  
   ~Int( ) {  
      cout << "Destructing " << ( void* )this << endl;   
      bIsConstructed = false;  
   };  
   Int &operator++( )   
   {  
      x++;  
      return *this;  
   };  
   int x;  
private:  
   bool bIsConstructed;  
};  
  
int main( )   
{  
   allocator<Int> Alloc;  
   allocator<Int> cAlloc ;  
   cAlloc = Alloc;      
}  
```  
  
##  <a name="pointer"></a>  allocator::pointer  
 アロケーターによって管理されるオブジェクトの型に対するポインターを提供する型。  
  
```  
typedef value_type *pointer;  
```  
  
### <a name="remarks"></a>コメント  
 ポインター型は、式 **\*ptr** を通じて指定できるオブジェクト **ptr** を記述します。これは、テンプレート クラスのアロケーター オブジェクトを割り当てることができる任意のオブジェクトです。  
  
### <a name="example"></a>例  
  
```cpp  
// allocator_ptr.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <int> v1;  
   vector <int>::iterator v1Iter;  
   vector <int>:: allocator_type v1Alloc;  
  
   int i;  
   for ( i = 1 ; i <= 7 ; i++ )  
   {  
      v1.push_back( 3 * i );  
   }  
  
   cout << "The original vector v1 is:\n ( " ;  
   for ( v1Iter = v1.begin( ) ; v1Iter != v1.end( ) ; v1Iter++ )  
      cout << *v1Iter << " ";  
   cout << ")." << endl;  
  
   allocator<int>::const_pointer v1Ptr;  
   const int k = 12;  
   v1Ptr = v1Alloc.address( k );  
  
   cout << "The integer addressed by v1Ptr has a value of: "  
        << "*v1Ptr = " << *v1Ptr << "." << endl;     
}  
```  
  
```Output  
The original vector v1 is:  
 ( 3 6 9 12 15 18 21 ).  
The integer addressed by v1Ptr has a value of: *v1Ptr = 12.  
```  
  
##  <a name="rebind"></a>  allocator::rebind  
 1 つの型のオブジェクトのアロケーターを使用して別の型のオブジェクトのストレージの割り当てを可能にする構造体。  
```  
struct rebind {    typedef allocator<_Other> other ;    };  
```  
### <a name="parameters"></a>パラメーター  
 *other*  
 メモリが割り当てられる要素の型。  
  
### <a name="remarks"></a>コメント  
 この構造体は、実装されているコンテナーの要素の型とは異なる型のメモリの割り当てに役立ちます。  
  
 メンバー テンプレート クラスは、型 other を定義します。 その唯一の目的は、所定の型名 **allocator**\< **Type**> で、型名 **allocator**\<_ **Other**> を提供することです。  
  
 たとえば、型 **A** のアロケーター オブジェクト **al** の場合、次の式で型 **_Other** のオブジェクトを割り当てることができます。  
  
```  
A::rebind<Other>::other(al).allocate(1, (Other *)0)  
```  
  
 または、次のように型を記述して、ポインター型を指定することができます。  
  
```  
A::rebind<Other>::other::pointer  
```  
  
### <a name="example"></a>例  
  
```cpp  
// allocator_rebind.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <algorithm>  
#include <vector>  
  
using namespace std;  
  
typedef vector<int>::allocator_type IntAlloc;  
int main( )   
{  
   IntAlloc v1Iter;  
   vector<int> v1;  
  
   IntAlloc::rebind<char>::other::pointer pszC =  
      IntAlloc::rebind<char>::other(v1.get_allocator()).allocate(1, (void *)0);  
  
   int * pInt = v1Iter.allocate(10);  
}  
```  
  
##  <a name="reference"></a>  allocator::reference  
 アロケーターによって管理されるオブジェクトの型に対する参照を提供する型。  
  
```  
typedef value_type& reference;  
```  
  
### <a name="remarks"></a>コメント  
 参照型は、テンプレート クラスのアロケーター オブジェクトを割り当てることができる任意のオブジェクトを指定できるオブジェクトを記述します。  
  
### <a name="example"></a>例  
  
```cpp  
// allocator_reference.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   vector <double> v;  
   vector <double> ::iterator vIter, vfIter;  
   vector <double> :: allocator_type vAlloc;  
  
   int j;  
   for ( j = 1 ; j <= 7 ; j++ )  
   {  
      v.push_back( 100.0 * j );  
   }  
  
   cout << "The original vector v is:\n ( " ;  
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vfIter = v.begin( );  
   allocator<double>::reference vref =*vfIter;  
   cout << "The value of the element referred to by vref is: "  
        << vref << ",\n the first element in the vector." << endl;  
  
   // nonconst references can have their elements modified  
   vref = 150;  
   cout << "The element referred to by vref after being modified is: "  
        << vref << "." << endl;  
}  
```  
  
```Output  
The original vector v is:  
 ( 100 200 300 400 500 600 700 ).  
The value of the element referred to by vref is: 100,  
 the first element in the vector.  
The element referred to by vref after being modified is: 150.  
```  
  
##  <a name="size_type"></a>  allocator::size_type  
 テンプレート クラス アロケーターのオブジェクトが割り当てることができる、シーケンスの長さを表すことのできる符号なし整数型。  
  
```  
typedef size_t size_type;  
```  
  
### <a name="example"></a>例  
  
```cpp  
// allocator_size_type.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )  
{  
   vector <double> v;  
   vector <double> ::iterator vIter;  
   vector <double> :: allocator_type vAlloc;  
  
   int j;  
   for ( j = 1 ; j <= 7 ; j++ )  
   {  
      v.push_back( 100.0 * j );  
   }  
  
   cout << "The original vector v is:\n ( " ;  
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   allocator<double>::size_type vsize;  
   vsize = vAlloc.max_size( );  
  
   cout << "The number of doubles that can be allocated before\n"  
        << " the free memory in the vector v is used up is: "  
        << vsize << "." << endl;  
}  
```  
  
##  <a name="value_type"></a>  allocator::value_type  
 アロケーターによって管理される型。  
  
```  
typedef Type value_type;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、テンプレート パラメーター **Type** のシノニムです。  
  
### <a name="example"></a>例  
  
```cpp  
// allocator_value_type.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
using namespace std;  
  
int main( )   
{  
   vector <double> v;  
   vector <double> ::iterator vIter, vfIter;  
   vector <double> :: allocator_type vAlloc;  
  
   int j;  
   for ( j = 1 ; j <= 7 ; j++ )  
   {  
      v.push_back( 100.0 * j );  
   }  
  
   cout << "The original vector v is:\n ( " ;  
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
  
   vfIter = v.begin( );  
   allocator<double>::value_type vecVal = 150.0;  
 *vfIter = vecVal;  
   cout << "The value of the element addressed by vfIter is: "  
        << *vfIter << ",\n the first element in the vector." << endl;  
  
   cout << "The modified vector v is:\n ( " ;  
   for ( vIter = v.begin( ) ; vIter != v.end( ) ; vIter++ )  
      cout << *vIter << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The original vector v is:  
 ( 100 200 300 400 500 600 700 ).  
The value of the element addressed by vfIter is: 150,  
 the first element in the vector.  
The modified vector v is:  
 ( 150 200 300 400 500 600 700 ).  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)


