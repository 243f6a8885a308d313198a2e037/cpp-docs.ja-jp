---
title: コンパイラ エラー C3161 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3161
dev_langs:
- C++
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f2d7aff3eb41c03f5be774704922340ac54126fc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33250704"
---
# <a name="compiler-error-c3161"></a>コンパイラ エラー C3161
'interface': クラスを入れ子構造体、共用体、またはインターフェイスのインターフェイスは無効です。クラス、構造体または共用体でインターフェイスを入れ子は無効です。  
  
 [_ _Interface](../../cpp/interface.md)グローバル スコープまたは名前空間内でのみ使用できます。 クラス、構造体、または共用体は、インターフェイスに表示できません。  
  
## <a name="example"></a>例  
 次の例では、C3161 を生成します。  
  
```  
// C3161.cpp  
// compile with: /c  
__interface X {  
   __interface Y {};   // C3161 A nested interface  
};  
```