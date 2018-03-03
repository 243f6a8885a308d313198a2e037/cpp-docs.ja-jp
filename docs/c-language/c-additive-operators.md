---
title: "C 加法演算子 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- usual arithmetic conversions
- operators [C], addition
- + operator, additive operators
- additive operators
- arithmetic operators [C++], additive operators
ms.assetid: bb8ac205-b061-41fc-8dd4-dab87c8b900c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 340aac3d3aab6951af43b824f1c8d0dd866f7a39
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="c-additive-operators"></a>C 加法演算子
加法演算子は加算 (**+**) と減算 (**-**) を実行します。  
  
## <a name="syntax"></a>構文  
 *additive-expression*:  
 *multiplicative-expression*  
  
 *additive-expression*  **+**  *multiplicative-expression*  
  
 *additive-expression*  **-**  *multiplicative-expression*  
  
> [!NOTE]
>  *additive-expression* の構文に *multiplicative-expression* が含まれてますが、乗算を使用する式が必要なわけではありません。 「[C 言語の構文概要](../c-language/c-language-syntax-summary.md)」で、*multiplicative-expression*、*cast-expression*、および *unary-expression* の構文を参照してください。  
  
 オペランドは整数値または浮動小数点値になります。 各演算子の説明に記載されているように、一部の加算演算はポインター値に対しても実行できます。  
  
 加算演算子は、整数および浮動小数点のオペランドに対して通常の算術変換を実行します。 結果の型は、変換後のオペランドの型です。 加算演算子によって実行される変換にはオーバーフロー条件やアンダーフロー条件が用意されていないため、加算演算の結果を変換後のオペランドの型で表すことができない場合、情報が失われる可能性があります。  
  
## <a name="see-also"></a>参照  
 [加法演算子: + および -](../cpp/additive-operators-plus-and.md)