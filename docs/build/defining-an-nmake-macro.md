---
title: "NMAKE マクロの定義 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- macros, NMAKE
- defining NMAKE macros
- NMAKE macros, defining
ms.assetid: 45aae451-9d33-4a3d-8799-2e0cae17070d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 96799bbd10d442c50d66ac4e84169864b9b989ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="defining-an-nmake-macro"></a>NMAKE マクロの定義
## <a name="syntax"></a>構文  
  
```  
  
macroname=string  
```  
  
## <a name="remarks"></a>コメント  
 *Macroname*はアルファベット、数字、および最大 1,024 文字、アンダー スコア (_) の組み合わせ、ケースと小文字が区別されます。 *Macroname*呼び出されたマクロを含めることができます。 場合*macroname*は、呼び出されたマクロの完全、呼び出されているマクロを null または未定義することはできません。  
  
 `string` 0 個以上の文字のシーケンスを指定できます。 Null 文字列には、0 文字または空白またはタブだけが含まれています。 `string`マクロの呼び出しを含めることができます。  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
 [マクロの特殊文字](../build/special-characters-in-macros.md)  
  
 [Null と未定義マクロ](../build/null-and-undefined-macros.md)  
  
 [マクロを定義する場所](../build/where-to-define-macros.md)  
  
 [マクロ定義で優先順位](../build/precedence-in-macro-definitions.md)  
  
## <a name="see-also"></a>参照  
 [マクロと NMAKE](../build/macros-and-nmake.md)