---
title: bitor | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- bitor
- std.bitor
- std::bitor
dev_langs: C++
helpviewer_keywords: bitor function
ms.assetid: 3c0a3711-9c74-41f2-b400-2f7797da30d1
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e5696d4e35a23b9be0d42f25eec0fd8d7d1e8302
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="bitor"></a>bitor
&#124; 演算子の代替手段。  
  
## <a name="syntax"></a>構文  
  
```  
  
#define bitor |  
  
```  
  
## <a name="remarks"></a>コメント  
 マクロにより &#124; 演算子が生成されます。  
  
## <a name="example"></a>例  
  
```  
// iso646_bitor.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iso646.h>  
  
int main( )  
{  
   using namespace std;  
   int a = 1, b = 2, result;  
  
   result = a | b;  
   cout << result << endl;  
  
   result= a bitor b;  
   cout << result << endl;  
}  
```  
  
```Output  
3  
3  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<iso646.h>