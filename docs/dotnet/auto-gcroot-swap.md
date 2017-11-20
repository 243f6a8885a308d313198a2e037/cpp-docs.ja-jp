---
title: "auto_gcroot::swap |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- msclr.auto_gcroot.swap
- msclr::auto_gcroot::swap
- auto_gcroot::swap
- auto_gcroot.swap
dev_langs: C++
helpviewer_keywords: auto_gcroot::swap
ms.assetid: 4915c629-6a53-432c-8155-3a7511dc70cb
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3f3876550ed48c0ab570220042b64ccadc4cff33
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="autogcrootswap"></a>auto_gcroot::swap
他のオブジェクトを交換`auto_gcroot`です。  
  
## <a name="syntax"></a>構文  
  
```  
void swap(  
   auto_gcroot<_element_type> & _right  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `_right`  
 `auto_gcroot`交換先のオブジェクトします。  
  
## <a name="example"></a>例  
  
```  
// msl_auto_gcroot_swap.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
int main() {  
   auto_gcroot<String^> s1 = "string one";  
   auto_gcroot<String^> s2 = "string two";  
  
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",  
      s1->ToString(), s2->ToString() );  
   s1.swap( s2 );  
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",  
      s1->ToString(), s2->ToString() );  
}  
```  
  
```Output  
s1 = 'string one', s2 = 'string two'  
s1 = 'string two', s2 = 'string one'  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー ファイル** \<msclr\auto_gcroot.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>関連項目  
 [auto_gcroot メンバー](../dotnet/auto-gcroot-members.md)   
 [swap 関数 (auto_gcroot)](../dotnet/swap-function-auto-gcroot.md)