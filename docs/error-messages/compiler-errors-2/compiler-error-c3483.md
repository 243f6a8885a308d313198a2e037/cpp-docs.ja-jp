---
title: コンパイラ エラー C3483 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3483
dev_langs:
- C++
helpviewer_keywords:
- C3483
ms.assetid: 18b3a2c5-dfc9-4661-9653-08a5798474cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e2605674ff701f70f7be6ea1b4158c9f8f0c6ad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33258738"
---
# <a name="compiler-error-c3483"></a>コンパイラ エラー C3483
'var' は既にラムダ キャプチャ リストに含まれています  
  
 ラムダ式のキャプチャ リストに同じ変数を複数回渡しました。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   キャプチャ リストから変数のすべての追加インスタンスを削除します。  
  
## <a name="example"></a>例  
 次の例では、変数 `n` がラムダ式のキャプチャ リストに複数回出現するため、C3483 が生成されます。  
  
```  
// C3483.cpp  
  
int main()  
{  
   int m = 6, n = 5;  
   [m,n,n] { return n + m; }(); // C3483  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)