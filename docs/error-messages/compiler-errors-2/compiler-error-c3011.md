---
title: コンパイラ エラー C3011 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3011
dev_langs:
- C++
helpviewer_keywords:
- C3011
ms.assetid: 24c3a917-ebff-4deb-9155-23adf6468531
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb78e658c0f56798fa0c23201889809d6c68d184
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33241913"
---
# <a name="compiler-error-c3011"></a>コンパイラ エラー C3011
インライン アセンブリを、並行領域内で使用することはできません  
  
 `omp` 並列領域は、インライン アセンブリの命令を含めることはできません。  
  
 次の例では C3011 が生成されます。  
  
```  
// C3011.cpp  
// compile with: /openmp  
// processor: /x86  
int main() {  
   int   n = 0;  
  
   #pragma omp parallel  
   {  
      _asm mov eax, n   // Delete this line to resolve this error.  
   }   // C3011  
}  
```