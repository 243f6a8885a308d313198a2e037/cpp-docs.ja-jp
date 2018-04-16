---
title: "単項演算子を含む式 |Microsoft ドキュメント"
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
- expressions [C++], unary operators
- unary operators [C++], expressions with
- expressions [C++], operators
ms.assetid: 1217685b-b85d-4b48-9ff4-d90f56a26c1b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 44485f0c5749db36ececd2061955f9956cb49ece
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="expressions-with-unary-operators"></a>単項演算子を含む式
単項演算子は、式の中で 1 つのオペランドに対してのみ作用します。 単項演算子は、次のとおりです。  
  
-   [間接演算子 (*)](../cpp/indirection-operator-star.md)  
  
-   [Address-of 演算子 (&)](../cpp/address-of-operator-amp.md)  
  
-   [単項プラス演算子 (+)](../cpp/unary-plus-and-negation-operators-plus-and.md)  
  
-   [単項否定演算子 (-)](../cpp/unary-plus-and-negation-operators-plus-and.md)  
  
-   [論理否定演算子 (!)](../cpp/logical-negation-operator-exclpt.md)  
  
-   [1 の補数演算子 (~)](../cpp/one-s-complement-operator-tilde.md)  
  
-   [前置インクリメント演算子 (+ +)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)  
  
-   [前置デクリメント演算子 (-)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)  
  
-   [キャスト演算子)](../cpp/cast-operator-parens.md)  
  
-   [sizeof 演算子](../cpp/sizeof-operator.md)  
  
-   [_ _uuidof 演算子](../cpp/uuidof-operator.md)  
  
-   [_ _alignof 演算子](../cpp/alignof-operator.md)  
  
-   [new 演算子](../cpp/new-operator-cpp.md)  
  
-   [delete 演算子](../cpp/delete-operator-cpp.md)  
  
 これらの演算子の結合規則は、右から左方向です。 単項式は構文では一般に後置式または 1 次式より優先されます。  
  
 以下は単項式の可能な形式です。  
  
-   *postfix-expression*  
  
-   `++`*単項式*  
  
-   `--`*単項式*  
  
-   *単項演算子**キャスト式*  
  
-   `sizeof`*単項式*  
  
-   `sizeof(`*型名*`)`  
  
-   `decltype(`*式*`)`  
  
-   *割り当て式*  
  
-   *割り当て解除式*  
  
 任意*後置式*と見なされます、*単項式*、および任意の主な式と見なされるため、*後置式*、すべて一次式は、見なされます、*単項式*もします。 詳細については、次を参照してください。[後置式](../cpp/postfix-expressions.md)と[一次式](../cpp/primary-expressions.md)です。  
  
 A*単項演算子*次の記号の 1 つ以上で構成されます。`* & + - ! ~`  
  
 *キャスト式*型を変更する省略可能なキャストを単項式です。 詳細については、次を参照してください。[キャスト演算子: ()](../cpp/cast-operator-parens.md)です。  
  
 *式*任意の式を指定できます。 詳細については、次を参照してください。[式](../cpp/expressions-cpp.md)です。  
  
 *割り当て式*を指す、`new`演算子。 *解放式*を指す、`delete`演算子。 詳細については、このトピックで前述したリンクを参照してください。  
  
## <a name="see-also"></a>参照  
 [式の型](../cpp/types-of-expressions.md)