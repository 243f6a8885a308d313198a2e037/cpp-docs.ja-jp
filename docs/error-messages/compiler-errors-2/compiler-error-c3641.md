---
title: "コンパイラ エラー C3641 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3641
dev_langs: C++
helpviewer_keywords: C3641
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 145d1739752f96b35cbf9af51c81900ab66fe6c4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3641"></a>コンパイラ エラー C3641
'function': の呼び出し規約 'calling_convention'/clr でコンパイルされた関数が無効です:/clr:pure または/clr:safe  
  
 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で使用されていません。  
  
 のみ[_ _clrcall](../../cpp/clrcall.md)と呼び出し規約が許可されている[/clr: 純粋な](../../build/reference/clr-common-language-runtime-compilation.md)します。  
  
 次の例では、C3641 が生成されます。  
  
```  
// C3641.cpp  
// compile with: /clr:pure /c  
void __cdecl f() {}   // C3641  
```