---
title: "キャスト演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], casting
- casting operators [C++]
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: a516297b687db349a6bcc867fc94dcd85118a8a5
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="casting-operators"></a>キャスト演算子
C++ 言語には、固有のキャスト演算子がいくつかあります。 これらの演算子は、以前のスタイルの C 言語のキャストが持つあいまいさと危険性の一部を取り除くことを目的としています。 このような演算子を次に示します。  
  
-   [dynamic_cast](../cpp/dynamic-cast-operator.md)ポリモーフィックな型の変換に使用します。  
  
-   [static_cast](../cpp/static-cast-operator.md)非ポリモーフィックな型の変換に使用します。  
  
-   [const_cast](../cpp/const-cast-operator.md)を削除するために使用、 `const`、 `volatile`、および`__unaligned`属性。  
  
-   [reinterpret_cast](../cpp/reinterpret-cast-operator.md)ビットの単純な再解釈に使用します。  
  
-   [safe_cast](../windows/safe-cast-cpp-component-extensions.md)検証可能な MSIL を生成するために使用します。  
  
 `const_cast` と `reinterpret_cast` には以前の形式と同じ危険性があるため、これらの演算子は最後の手段として使用してください。 それでも、これらは、以前のスタイルのキャストを完全に置き換えるために必要です。  
  
## <a name="see-also"></a>関連項目  
 [キャスト](../cpp/casting.md)
