---
title: "list::push_front (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list::push_front
dev_langs: C++
helpviewer_keywords: push_front member [STL/CLR]
ms.assetid: 47525641-1139-44fc-ac62-bdc04876d9e0
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 28c2526b15e0c6049b1f279b76d48455bdc82ac6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="listpushfront-stlclr"></a>list::push_front (STL/CLR)
新しい最初の要素を追加します。  
  
## <a name="syntax"></a>構文  
  
```  
void push_front(value_type val);  
```  
  
## <a name="remarks"></a>コメント  
 このメンバー関数は、値を持つ要素を挿入します。`val`被制御シーケンスの先頭にします。 使用する前に、一覧に別の要素を付加します。  
  
## <a name="example"></a>例  
  
```  
// cliext_list_push_front.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_front(L'a');   
    c1.push_front(L'b');   
    c1.push_front(L'c');   
  
// display contents " c b a"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/一覧 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [一覧 (STL/CLR)](../dotnet/list-stl-clr.md)   
 [list::pop_back (STL/CLR)](../dotnet/list-pop-back-stl-clr.md)   
 [list::pop_front (STL/CLR)](../dotnet/list-pop-front-stl-clr.md)   
 [list::push_back (STL/CLR)](../dotnet/list-push-back-stl-clr.md)