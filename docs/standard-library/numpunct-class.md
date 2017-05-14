---
title: "numpunct クラス |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xlocnum/std::numpunct
- numpunct
- locale/std::numpunct::char_type
- locale/std::numpunct::string_type
- locale/std::numpunct::decimal_point
- locale/std::numpunct::do_decimal_point
- locale/std::numpunct::do_falsename
- locale/std::numpunct::do_grouping
- locale/std::numpunct::do_thousands_sep
- locale/std::numpunct::do_truename
- locale/std::numpunct::falsename
- locale/std::numpunct::grouping
- locale/std::numpunct::thousands_sep
- locale/std::numpunct::truename
dev_langs:
- C++
helpviewer_keywords:
- numpunct class
ms.assetid: 73fb93cc-ac11-4c98-987c-bfa6267df596
caps.latest.revision: 22
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
ms.openlocfilehash: 56dbd3ed6e655ec5f431d383864f949925baaf5c
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="numpunct-class"></a>numpunct クラス
数値とブール式の書式設定および区切りに関する情報を表すために使用される、`CharType` 型のシーケンスを表すロケール ファセットとして使用できるオブジェクトを表すテンプレート クラス。  
  
## <a name="syntax"></a>構文  
  
```  
template <class CharType>  
class numpunct : public locale::facet;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `CharType`  
 ロケールの文字をエンコードするためにプログラム内で使用される型。  
  
## <a name="remarks"></a>コメント  
 すべてのロケールのファセットと同様、静的オブジェクト ID に最初に格納されている値は 0 です。 格納されている値に初めてアクセスしようとすると、**id** に一意の正の値が格納されます。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[numpunct](#numpunct)|`numpunct` 型のオブジェクトのコンストラクター。|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#char_type)|ロケールによって使用される文字を表すために使用される型。|  
|[string_type](#string_type)|`CharType` 型の文字を格納する文字列を表す型。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[decimal_point](#decimal_point)|小数点として使用するロケール固有の要素を返します。|  
|[do_decimal_point](#do_decimal_point)|小数点として使用するロケール固有の要素を返すために呼び出されるプロテクト仮想メンバー関数。|  
|[do_falsename](#do_falsename)|`false` 値のテキスト表現として使用する文字列を返すために呼び出されるプロテクト仮想メンバー関数。|  
|[do_grouping](#do_grouping)|小数点の左側の数字をグループ化する方法を決定するロケール固有の規則を返すために呼び出されるプロテクト仮想メンバー関数。|  
|[do_thousands_sep](#do_thousands_sep)|桁区切り記号として使用するロケール固有の要素を返すために呼び出されるプロテクト仮想メンバー関数。|  
|[do_truename](#do_truename)|`true` 値のテキスト表現として使用する文字列を返すために呼び出されるプロテクト仮想メンバー関数。|  
|[falsename](#falsename)|`false` 値のテキスト表現として使用する文字列を返します。|  
|[grouping](#grouping)|小数点の左側の数字をグループ化する方法を決定するロケール固有の規則を返します。|  
|[thousands_sep](#thousands_sep)|桁区切り記号として使用するロケール固有の要素を返します。|  
|[truename](#truename)|`true` 値のテキスト表現として使用する文字列を返します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<locale>  
  
 **名前空間:** std  
  
##  <a name="char_type"></a>  numpunct::char_type  
 ロケールによって使用される文字を表すために使用される型。  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、テンプレート パラメーター **CharType** のシノニムです。  
  
##  <a name="decimal_point"></a>  numpunct::decimal_point  
 小数点として使用するロケール固有の要素を返します。  
  
```  
CharType decimal_point() const;
```  
  
### <a name="return-value"></a>戻り値  
 小数点として使用するロケール固有の要素。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、[do_decimal_point](#do_decimal_point) を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// numpunct_decimal_point.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const numpunct <char> &npunct =   
   use_facet <numpunct <char> >( loc);  
   cout << loc.name( ) << " decimal point "<<   
   npunct.decimal_point( ) << endl;  
   cout << loc.name( ) << " thousands separator "   
   << npunct.thousands_sep( ) << endl;  
};  
```  
  
```Output  
German_Germany.1252 decimal point ,  
German_Germany.1252 thousands separator .  
```  
  
##  <a name="do_decimal_point"></a>  numpunct::do_decimal_point  
 小数点として使用するロケール固有の要素を返すために呼び出されるプロテクト仮想メンバー関数。  
  
```  
virtual CharType do_decimal_point() const;
```  
  
### <a name="return-value"></a>戻り値  
 小数点として使用するロケール固有の要素。  
  
### <a name="example"></a>例  
  [decimal_point](#decimal_point) の例 (仮想メンバー関数が `decimal_point` で呼び出される) をご覧ください。  
  
##  <a name="do_falsename"></a>  numpunct::do_falsename  
 このプロテクト仮想メンバー関数は、**false** 値のテキスト表現として使用するシーケンスを返します。  
  
```  
virtual string_type do_falsename() const;
```  
  
### <a name="return-value"></a>戻り値  
 **false** 値のテキスト表現として使用するシーケンスを含む文字列。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、すべてのロケールで **false** 値を表す文字列 "false" を返します。  
  
### <a name="example"></a>例  
  [falsename](#falsename) の例 (仮想メンバー関数が `falsename` で呼び出される) をご覧ください。  
  
##  <a name="do_grouping"></a>  numpunct::do_grouping  
 小数点の左側の数字をグループ化する方法を決定するロケール固有の規則を返すために呼び出されるプロテクト仮想メンバー関数。  
  
```  
virtual string do_grouping() const;
```  
  
### <a name="return-value"></a>戻り値  
 小数点の左側の数字をグループ化する方法を決定するロケール固有の規則。  
  
### <a name="remarks"></a>コメント  
 このプロテクト仮想メンバー関数は、小数点の左側の数字をグループ化する方法を決定するロケール固有の規則を返します。 エンコーディングは **lconv::grouping** の場合と同じです。  
  
### <a name="example"></a>例  
  [grouping](#grouping) の例 (仮想メンバー関数が **grouping** で呼び出される) をご覧ください。  
  
##  <a name="do_thousands_sep"></a>  numpunct::do_thousands_sep  
 桁区切り記号として使用するロケール固有の要素を返すために呼び出されるプロテクト仮想メンバー関数。  
  
```  
virtual CharType do_thousands_sep() const;
```  
  
### <a name="return-value"></a>戻り値  
 桁区切り記号として使用するロケール固有の要素を返します。  
  
### <a name="remarks"></a>コメント  
 このプロテクト仮想メンバー関数は、小数点の左側の桁区切り記号として使用する、**CharType** 型のロケール固有の要素を返します。  
  
### <a name="example"></a>例  
  [thousands_sep](#thousands_sep) の例 (仮想メンバー関数が `thousands_sep` で呼び出される) をご覧ください。  
  
##  <a name="do_truename"></a>  numpunct::do_truename  
 **true** 値のテキスト表現として使用する文字列を返すために呼び出されるプロテクト仮想メンバー関数。  
  
```  
virtual string_type do_truename() const;
```  
  
### <a name="remarks"></a>コメント  
 **true** 値のテキスト表現として使用する文字列。  
  
 すべてのロケールは、**true** 値を表す文字列 "true" を返します。  
  
### <a name="example"></a>例  
  [truename](#truename) の例 (仮想メンバー関数が `truename` で呼び出される) をご覧ください。  
  
##  <a name="falsename"></a>  numpunct::falsename  
 **false** 値のテキスト表現として使用する文字列を返します。  
  
```  
string_type falsename() const;
```  
  
### <a name="return-value"></a>戻り値  
 **false** 値のテキスト表現として使用する **CharType** のシーケンスを含む文字列。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、すべてのロケールで **false** 値を表す文字列 "false" を返します。  
  
 このメンバー関数は、[do_falsename](#do_falsename) を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// numpunct_falsename.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "English" );  
  
   const numpunct <char> &npunct = use_facet <numpunct <char> >( loc );  
   cout << loc.name( ) << " truename "<< npunct.truename( ) << endl;  
   cout << loc.name( ) << " falsename "<< npunct.falsename( ) << endl;  
  
   locale loc2( "French" );  
   const numpunct <char> &npunct2 = use_facet <numpunct <char> >(loc2);  
   cout << loc2.name( ) << " truename "<< npunct2.truename( ) << endl;  
   cout << loc2.name( ) << " falsename "<< npunct2.falsename( ) << endl;  
}  
```  
  
```Output  
English_United States.1252 truename true  
English_United States.1252 falsename false  
French_France.1252 truename true  
French_France.1252 falsename false  
```  
  
##  <a name="grouping"></a>  numpunct::grouping  
 小数点の左側の数字をグループ化する方法を決定するロケール固有の規則を返します。  
  
```  
string grouping() const;
```  
  
### <a name="return-value"></a>戻り値  
 小数点の左側の数字をグループ化する方法を決定するロケール固有の規則。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、[do_grouping](#do_grouping) を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// numpunct_grouping.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany");  
  
   const numpunct <char> &npunct =   
       use_facet < numpunct <char> >( loc );  
   for (unsigned int i = 0; i < npunct.grouping( ).length( ); i++)  
   {  
      cout << loc.name( ) << " international grouping:\n the "  
           << i <<"th group to the left of the radix character "  
           << "is of size " << (int)(npunct.grouping ( )[i])   
           << endl;  
   }  
}  
```  
  
```Output  
German_Germany.1252 international grouping:  
 the 0th group to the left of the radix character is of size 3  
```  
  
##  <a name="numpunct"></a>  numpunct::numpunct  
 `numpunct` 型のオブジェクトのコンストラクター。  
  
```  
explicit numpunct(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Refs`  
 オブジェクトのメモリ管理のタイプを指定するために使用する整数値。  
  
### <a name="remarks"></a>コメント  
 `_Refs` パラメーターの可能な値とその重要性は次のとおりです。  
  
-   0: オブジェクトの有効期間はそれが含まれるロケールによって管理されます。  
  
-   1: オブジェクトの有効期間を手動で管理する必要があります。  
  
-   \>1: これらの値が定義されていません。  
  
 デストラクターが保護されているため、利用できる直接的な例はありません。  
  
 コンストラクターは、**locale::**[facet](../standard-library/locale-class.md#facet_class)( `_Refs`) を使用して、その基本オブジェクトを初期化します。  
  
##  <a name="string_type"></a>  numpunct::string_type  
 **CharType** 型の文字を格納する文字列を表す型。  
  
```  
typedef basic_string<CharType, Traits, Allocator> string_type;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、オブジェクトに区切り記号シーケンスのコピーを格納できるテンプレート クラス [basic_string](../standard-library/basic-string-class.md) の特殊化を表します。  
  
##  <a name="thousands_sep"></a>  numpunct::thousands_sep  
 桁区切り記号として使用するロケール固有の要素を返します。  
  
```  
CharType thousands_sep() const;
```  
  
### <a name="return-value"></a>戻り値  
 桁区切り記号として使用するロケール固有の要素。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、[do_thousands_sep](#do_thousands_sep) を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// numpunct_thou_sep.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const numpunct <char> &npunct =   
   use_facet < numpunct < char > >( loc );  
   cout << loc.name( ) << " decimal point "<<   
   npunct.decimal_point( ) << endl;  
   cout << loc.name( ) << " thousands separator "   
   << npunct.thousands_sep( ) << endl;  
};  
```  
  
```Output  
German_Germany.1252 decimal point ,  
German_Germany.1252 thousands separator .  
```  
  
##  <a name="truename"></a>  numpunct::truename  
 **true** 値のテキスト表現として使用する文字列を返します。  
  
```  
string_type falsename() const;
```  
  
### <a name="return-value"></a>戻り値  
 **true** 値のテキスト表現として使用する文字列。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、[do_truename](#do_truename) を返します。  
  
 すべてのロケールは、**true** 値を表す文字列 "true" を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// numpunct_truename.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "English" );  
  
   const numpunct < char> &npunct = use_facet <numpunct <char> >( loc );  
   cout << loc.name( ) << " truename "<< npunct.truename( ) << endl;  
   cout << loc.name( ) << " falsename "<< npunct.falsename( ) << endl;  
  
   locale loc2("French");  
   const numpunct <char> &npunct2 = use_facet <numpunct <char> >( loc2 );  
   cout << loc2.name( ) << " truename "<< npunct2.truename( ) << endl;  
   cout << loc2.name( ) << " falsename "<< npunct2.falsename( ) << endl;  
}  
```  
  
```Output  
English_United States.1252 truename true  
English_United States.1252 falsename false  
French_France.1252 truename true  
French_France.1252 falsename false  
```  
  
## <a name="see-also"></a>関連項目  
 [\<locale>](../standard-library/locale.md)   
 [facet クラス](../standard-library/locale-class.md#facet_class)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)


