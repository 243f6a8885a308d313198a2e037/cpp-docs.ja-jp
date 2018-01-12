---
title: "operator! = (組) (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::pair::operator!=
dev_langs: C++
helpviewer_keywords: operator!= member [STL/CLR]
ms.assetid: 167005f9-727d-40af-8d6d-2793d0daa96a
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a94de96f011fffaebaf7c4419adb24a7ae220d31
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="operator-pair-stlclr"></a>operator!= (pair) (STL/CLR)
等しくない比較をペアにします。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator!=(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 左へ  
 比較する左のペア。  
  
 右  
 比較する右のペア。  
  
## <a name="remarks"></a>コメント  
 演算子関数を返します`!(left == right)`です。 テストするために使用するかどうか`left`順序付けされていないと同じ`right`と 2 つのペアは、要素で要素を比較します。  
  
## <a name="example"></a>例  
  
```  
// cliext_pair_operator_ne.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] != [x 3] is {0}",   
        c1 != c1);   
    System::Console::WriteLine("[x 3] != [x 4] is {0}",   
        c1 != c2);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
[x, 4]  
[x 3] != [x 3] is False  
[x 3] != [x 4] is True  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext ユーティリティ/>  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>参照  
 [ペア (STL/CLR)](../dotnet/pair-stl-clr.md)   
 [演算子 = = (組) (STL/CLR)](../dotnet/operator-equality-pair-stl-clr.md)   
 [演算子\<(組) (STL/CLR)](../dotnet/operator-less-than-pair-stl-clr.md)   
 [operator > = (組) (STL/CLR)](../dotnet/operator-greater-or-equal-pair-stl-clr.md)   
 [operator > (組) (STL/CLR)](../dotnet/operator-greater-than-pair-stl-clr.md)   
 [operator<= (pair) (STL/CLR)](../dotnet/operator-less-or-equal-pair-stl-clr.md)