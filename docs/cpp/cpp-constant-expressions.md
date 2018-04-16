---
title: "C++ 定数式 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: b07245a5-4c21-4589-b503-e6ffd631996f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0cd30dd51b3d87b7d82b917734d187ae2278837a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="c-constant-expressions"></a>C++ 定数式
A*定数*値は変更されません。 C++ には、あるオブジェクトを変更しないという意思表示をして、その意志を行使するための 2 つのキーワードが用意されています。  
  
 C++ では、次の宣言に定数式 (定数に評価される式) が必要です。  
  
-   配列の境界  
  
-   case ステートメントのセレクター  
  
-   ビット フィールドの長さの指定  
  
-   列挙型の初期化子  
  
 定数式で有効なのは、次のオペランドのみです。  
  
-   リテラル  
  
-   列挙定数  
  
-   定数式で初期化され、const として宣言される値  
  
-   `sizeof` 式  
  
 定数式で有効にするには、非整数型の定数を (明示的または暗黙的に) 整数型に変換する必要があります。 したがって、次のコードは有効です。  
  
```  
const double Size = 11.0;  
char chArray[(int)Size];  
```  
  
 定数式では、整数型への明示的な変換は有効です。`sizeof` 演算子へのオペランドとして使用する場合を除き、他のすべての型とその派生型は無効です。  
  
 コンマ演算子および代入演算子は定数式では使用できません。  
  
## <a name="see-also"></a>参照  
 [式の型](../cpp/types-of-expressions.md)