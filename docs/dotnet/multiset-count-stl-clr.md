---
title: "multiset::count (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::multiset::count
dev_langs: C++
helpviewer_keywords: count member [STL/CLR]
ms.assetid: 6c668667-0047-4101-8dfc-0f538655b3d1
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 149d32a171167d1c75ecbc2f357c2380eb4f4a88
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="multisetcount-stlclr"></a>multiset::count (STL/CLR)
指定したキーに一致する要素の数を検索します。  
  
## <a name="syntax"></a>構文  
  
```  
size_type count(key_type key);  
```  
  
#### <a name="parameters"></a>パラメーター  
 key  
 検索対象のキー値。  
  
## <a name="remarks"></a>コメント  
 メンバー関数と同じ順序付けする被制御シーケンスの要素の数を返します`key`です。 それを使用して、指定したキーと一致する、被制御シーケンスの現在の要素の数を決定します。  
  
## <a name="example"></a>例  
  
```  
// cliext_multiset_count.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));   
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));   
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
count(L'A') = 0  
count(L'b') = 1  
count(L'C') = 0  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext と set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [マルチセット (STL/CLR)](../dotnet/multiset-stl-clr.md)   
 [multiset::equal_range (STL/CLR)](../dotnet/multiset-equal-range-stl-clr.md)