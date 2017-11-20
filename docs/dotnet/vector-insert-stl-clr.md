---
title: "vector::insert (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector::insert
dev_langs: C++
helpviewer_keywords: insert member [STL/CLR]
ms.assetid: f240cabf-f9d1-40c1-9cfb-975a90955546
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b72907b7579b6739a2c1873877eeeb3ae536d8fa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="vectorinsert-stlclr"></a>vector::insert (STL/CLR)
指定した位置にある要素を追加します。  
  
## <a name="syntax"></a>構文  
  
```  
iterator insert(iterator where, value_type val);  
void insert(iterator where, size_type count, value_type val);  
template<typename InIt>  
    void insert(iterator where, InIt first, InIt last);  
void insert(iterator where,  
    System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 count  
 挿入する要素の数。  
  
 先頭  
 挿入する範囲の開始しています。  
  
 last  
 挿入する範囲の終了。  
  
 右  
 列挙型を挿入します。  
  
 val  
 挿入する要素の値です。  
  
 where  
 前に挿入するためのコンテナー内の場所。  
  
## <a name="remarks"></a>コメント  
 メンバーの各関数が指す要素の前に、挿入`where`被制御シーケンスのシーケンスは、残りのオペランドで指定します。  
  
 最初のメンバー関数は、値を持つ要素を挿入します。`val`し、新しく挿入される要素を指定する反復子を返します。 使用する反復子によって指定された場所の前に 1 つの要素を挿入します。  
  
 2 番目のメンバー関数は、値 `count` の要素を `val` 個挿入します。 使用する同じ値のすべてのコピーである 0 個以上の連続する要素を挿入します。  
  
 `InIt` が整数型である場合、3 番目のメンバー関数は `insert(where, (size_type)first, (value_type)last)` と同じように動作します。 それ以外の場合、これは、シーケンスを挿入 [`first`、 `last`)。 使用する別のシーケンスからコピーした 0 個以上の連続する要素を挿入します。  
  
 4 番目のメンバー関数で指定されたシーケンスを挿入する、`right`です。 使用する列挙子によって説明されているシーケンスを挿入します。  
  
 1 つの要素を挿入するときに要素のコピーの数はカーソルと、シーケンスの最も近い最後の要素の数に比例します。 (1 つまたは複数の要素を挿入する、シーケンスの先頭または末尾にある、ときに要素のコピーは発生しません。)場合`InIt`は入力反復子は、3 番目のメンバー関数は、シーケンス内の各要素の 1 つの挿入を効果的に実行します。 それ以外の場合、挿入するときに`N`要素、要素のコピーの数が線形に`N`+ カーソルと、シーケンスの最も近い最後の要素の数。  
  
## <a name="example"></a>例  
  
```  
// cliext_vector_insert.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value using iterator   
    cliext::vector<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",   
        *c1.insert(++it, L'x'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a repetition of values   
    cliext::vector<wchar_t> c2;   
    c2.insert(c2.begin(), 2, L'y');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    it = c1.end();   
    c2.insert(c2.end(), c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    c2.insert(c2.begin(),   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
insert(begin()+1, L'x') = x  
 a x b c  
 y y  
 y y a x b  
 a x b c y y a x b  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/vector >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [ベクトル (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [vector::assign (STL/CLR)](../dotnet/vector-assign-stl-clr.md)