---
title: "do-while ステートメント (C) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- do
- while
dev_langs:
- C++
helpviewer_keywords:
- do-while keyword [C]
ms.assetid: f2ac20a6-10c7-4a08-b5e3-c3b3639dbeaf
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 9ea9e9c4cfdf57709cd125f8269657d37393cc61
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="do-while-statement-c"></a>do-while ステートメント (C)
`do-while` ステートメントを使用して、指定した式が false になるまでステートメントまたは複合ステートメントを繰り返すことができます。  
  
## <a name="syntax"></a>構文  
 *iteration-statement*:  
 **do**  *statement*  **while (**  *expression*  **) ;**  
  
 `do-while` ステートメント内の *expression* は、ループの本体が実行された後で評価されます。 したがって、ループの本体は、常に少なくとも 1 回は実行されます。  
  
 *expression* は演算型またはポインター型であることが必要です。 次のように実行されます。  
  
1.  ステートメントの本体が実行されます。  
  
2.  次に、*expression* が評価されます。 *expression* が false の場合、`do-while` ステートメントが終了し、制御はプログラムの次のステートメントに渡されます。 *式*が true (0 以外) の場合、プロセスは手順 1 から繰り返されます。  
  
 `do-while` ステートメントは、**break**、`goto`、または `return` ステートメントがステートメント本体で実行されたときにも終了できます。  
  
 `do-while` ステートメントの例を次に示します。  
  
```  
do   
{  
    y = f( x );  
    x--;  
} while ( x > 0 );  
```  
  
 この `do-while` ステートメントでは、`y = f( x );` の初期値に関係なく、2 つのステートメント `x--;` および `x` が実行されます。 次に、`x > 0` が評価されます。 `x` が 0 より大きい場合、ステートメント本体が再度実行され、`x > 0` が再評価されます。 `x` が 0 より大きい間、ステートメント本体が繰り返し実行されます。 `do-while` ステートメントの実行は、`x` が 0 または負になると終了します。 ループの本体は、少なくとも 1 回は実行されます。  
  
## <a name="see-also"></a>関連項目  
 [do-while ステートメント (C++)](../cpp/do-while-statement-cpp.md)
