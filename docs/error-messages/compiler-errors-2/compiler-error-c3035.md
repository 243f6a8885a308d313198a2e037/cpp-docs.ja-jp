---
title: "コンパイラ エラー C3035 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3035
dev_langs: C++
helpviewer_keywords: C3035
ms.assetid: af34fad2-2b45-42d0-a9ff-04eab3e91c37
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 09b007b4dc68415a7419d876ee642fc20f747b25
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3035"></a>コンパイラ エラー C3035
OpenMP 'ordered' ディレクティブは、'ordered' 句と共に 'for' または 'parallel for' ディレクティブに直接バインドしなければなりません  
  
 ordered 句の形式が正しくありません。  
  
 次の例では C3035 が生成されます。  
  
```  
// C3035.cpp  
// compile with: /openmp /link vcomps.lib  
int main() {  
   int n = 0, x, i;  
  
   #pragma omp parallel private(n)  
   {  
      #pragma omp ordered   // C3035  
      // Try the following line instead:  
      // #pragma omp for ordered  
       for (i = 0 ; i < 10 ; ++i)  
         ;  
   }  
}  
```