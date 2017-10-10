---
title: "致命的なエラー C1017 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1017
dev_langs:
- C++
helpviewer_keywords:
- C1017
ms.assetid: 5542e604-599d-4e36-8f83-1d454c5753c9
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 478a0a17ef8e0f0e6cb6589798d901837e7aff75
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1017"></a>致命的なエラー C1017
整数定数式が無効です。  
  
 内の式、`#if`ディレクティブが存在しない、または定数に評価されませんでした。  
  
 使用して定義されている定数`#define`値で使用されている場合は、整数の定数に評価される必要があります、 `#if`、 `#elif`、または`#else`ディレクティブです。  
  
 次の例では、C1017 が生成されます。  
  
```  
// C1017.cpp  
#define CONSTANT_NAME "YES"  
#if CONSTANT_NAME   // C1017  
#endif  
```  
  
 考えられる解決策:  
  
```  
// C1017b.cpp  
// compile with: /c  
#define CONSTANT_NAME 1  
#if CONSTANT_NAME  
#endif  
```  
  
 `CONSTANT_NAME`に文字列と整数ではありません、評価、`#if`ディレクティブで致命的なエラー C1017 が生成されます。  
  
 それ以外の場合に、プリプロセッサは、0 として定数 undefined を評価します。 次の例に示すように意図しない結果は、原因になります。 `YES`0 に評価するためには、定義されません。 式`#if``CONSTANT_NAME`が false になり、コードで使用される`YES`はプリプロセッサによって削除されます。 `NO`定義されていない (ゼロ)。 このため`#elif``CONSTANT_NAME==NO`を true に評価 (`0 == 0`)、内のコードのままにするプリプロセッサの原因、 `#elif` 、ステートメントの部分 — 正反対が意図した動作です。  
  
```  
// C1017c.cpp  
// compile with: /c  
#define CONSTANT_NAME YES  
#if CONSTANT_NAME  
   // Code to use on YES...  
#elif CONSTANT_NAME==NO  
   // Code to use on NO...  
#endif  
```  
  
 プリプロセッサ ディレクティブの処理方法正確にコンパイラを表示する[/P](../../build/reference/p-preprocess-to-a-file.md)、 [/E](../../build/reference/e-preprocess-to-stdout.md)、または[/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)です。
