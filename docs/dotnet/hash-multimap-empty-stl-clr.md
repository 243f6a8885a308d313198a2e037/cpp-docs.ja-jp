---
title: "hash_multimap::empty (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_multimap::empty
dev_langs: C++
helpviewer_keywords: empty member [STL/CLR]
ms.assetid: 5fd29e90-e33a-460f-9d42-491b82dbaa40
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ef6161cfc7a4051dc25e60648cd68f927f1ef205
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="hashmultimapempty-stlclr"></a>hash_multimap::empty (STL/CLR)
要素が存在しないかどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```  
bool empty();  
```  
  
## <a name="remarks"></a>コメント  
 このメンバー関数は、被制御シーケンスが空の場合に true を返します。 等価である[hash_multimap::size (STL/CLR)](../dotnet/hash-multimap-size-stl-clr.md)`() == 0`です。 これを使用するには、hash_multimap が空かどうかをテストします。  
  
## <a name="example"></a>例  
  
```  
// cliext_hash_multimap_empty.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
size() = 3  
empty() = False  
size() = 0  
empty() = True  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap::size (STL/CLR)](../dotnet/hash-multimap-size-stl-clr.md)