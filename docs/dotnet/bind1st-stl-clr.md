---
title: "bind1st (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::bind1st
dev_langs: C++
helpviewer_keywords: bind1st function [STL/CLR]
ms.assetid: 03a04cef-60fb-4667-b22a-22a387adb028
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b17a2bdcfee80b027423c24a7a430095eed6297d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="bind1st-stlclr"></a>bind1st (STL/CLR)
生成、`binder1st`引数およびファンクタ。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Fun,  
    typename Arg>  
    binder1st<Fun> bind1st(Fun% functor,  
        Arg left);  
```  
  
## <a name="template-parameters"></a>テンプレート パラメーター  
 arg  
 引数の型。  
  
 楽しい  
 ファンクタの型。  
  
## <a name="function-parameters"></a>関数パラメーター  
 ファンクター  
 ラップするファンクタ。  
  
 左へ  
 ラップする最初の引数。  
  
## <a name="remarks"></a>コメント  
 テンプレート関数を返します[binder1st (STL/CLR)](../dotnet/binder1st-stl-clr.md)`<Fun>(functor, left)`です。 2 番目の引数を持つ呼び出し元引数が 1 つファンクタで 2 つの引数ファンクターと、最初の引数をラップする便利な手段として使用するとします。  
  
## <a name="example"></a>例  
  
```  
// cliext_bind1st.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::minus<int> sub_op;   
    cliext::binder1st<cliext::minus<int> > subfrom3(sub_op, 3);   
  
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        subfrom3);   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display with function   
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),   
        bind1st(sub_op, 3));   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
4 3  
-1 0  
-1 0  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext/機能 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [binder1st (STL/CLR)](../dotnet/binder1st-stl-clr.md)