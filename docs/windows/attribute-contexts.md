---
title: "属性コンテキスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], contexts
ms.assetid: 3086351f-77a8-4048-99e9-3b6b041b9437
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 662b540548c0594364bf11087c3b52420d29cf0c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="attribute-contexts"></a>属性コンテキスト
C++ 属性は、次の 4 つの基本的なフィールドを使用して記述できます: ターゲットに適用できます (**適用先**) 場合は、反復可能かどう (**Repeatable**) では、その他の属性 (の存在が必要**必要な属性**)、およびその他の属性を持つ非互換性 (**無効な属性**)。 これらのフィールドは、各属性の参照トピックの表に表示されます。 これらの各フィールドは、以下について説明します。  
  
## <a name="applies-to"></a>対象  
 このフィールドでは、指定した属性の有効な対象になっている別の C++ 言語要素について説明します。 たとえば、属性で"class"を指定する場合、**適用先**フィールドに、このことを示します属性は、有効な C++ クラスにのみ適用できます。 属性がクラスのメンバー関数に適用されている場合、構文エラーが発生します。  
  
 詳細については、次を参照してください。[属性を使用して](../windows/attributes-by-usage.md)です。  
  
## <a name="repeatable"></a>反復可能  
 このフィールドは、同じターゲットに属性を繰り返し適用するかどうかを示します。 属性の過半数が反復可能です。  
  
## <a name="required-attributes"></a>必要な属性  
 このフィールドに表示する必要があるその他の属性を正常に機能の指定した属性のある (つまり、同じターゲットに適用される)。 このフィールドのすべてのエントリが存在する属性の一般的なことはできません。  
  
## <a name="invalid-attributes"></a>無効な属性  
 このフィールドは、指定した属性と互換性がないその他の属性を一覧表示します。 このフィールドのすべてのエントリが存在する属性の一般的なことはできません。  
  
## <a name="see-also"></a>参照  
 [C++ 属性リファレンス](../windows/cpp-attributes-reference.md)