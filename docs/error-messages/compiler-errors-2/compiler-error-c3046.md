---
title: コンパイラ エラー C3046 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3046
dev_langs:
- C++
helpviewer_keywords:
- C3046
ms.assetid: 2e53d835-faa1-4ec0-9807-41f3dc552635
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d39290f821b96c7b94018f3f28910a480ff0102
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3046"></a>コンパイラ エラー C3046
OpenMP '#pragma omp sections' の領域で構造化ブロックがありません  
  
 [sections](../../parallel/openmp/reference/sections-openmp.md) ディレクティブに空のコード ブロックが含まれています。  
  
 次の例では C3046 が生成されます。  
  
```  
// C3046.cpp  
// compile with: /openmp /c  
#include "omp.h"  
  
int main() {  
   int n2 = 2, n3 = 3;  
  
   #pragma omp parallel  
   {  
      ++n2;  
  
      #pragma omp sections  
      {  
/*  
         ++n2;  
  
         #pragma omp section  
         {  
            ++n3;  
         }  
*/  
       }   // C3046 uncomment code to resolve this C3046  
   }  
}  
```