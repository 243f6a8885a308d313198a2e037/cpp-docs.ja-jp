---
title: "multimap::swap (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multimap::swap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "swap メンバー [STL/CLR]"
ms.assetid: 198018d2-7814-4237-8ec3-5f3ea950e8af
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# multimap::swap (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

2 つのコンテナーのコンテンツを交換します。  
  
## 構文  
  
```  
void swap(multimap<Key, Mapped>% right);  
```  
  
#### パラメーター  
 \[right\]  
 コンテンツの交換先のコンテナー。  
  
## 解説  
 このメンバー関数は、`this` と `right` の間で被制御シーケンスを交換します。  この処理は定数時間で実行され、例外はスローしません。  2 個のコンテナーのコンテンツを交換する単純として使用します。  
  
## 使用例  
  
```  
// cliext_multimap_swap.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    Mymultimap c2;   
    c2.insert(Mymultimap::make_value(L'd', 4));   
    c2.insert(Mymultimap::make_value(L'e', 5));   
    c2.insert(Mymultimap::make_value(L'f', 6));   
    for each (Mymultimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// swap and redisplay   
    c1.swap(c2);   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    for each (Mymultimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **1 \[\] \[b 2 \[\]c 3\]**  
 **d 4 \[\] \[e 5 \[\]f 6\]**  
 **d 4 \[\] \[e 5 \[\]f 6\]**  
 **1 \[\] \[b 2 \[\]c 3\]**   
## 必要条件  
 **ヘッダー:** の \<cliext\/マップ\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multimap::operator\=](../dotnet/multimap-operator-assign-stl-clr.md)