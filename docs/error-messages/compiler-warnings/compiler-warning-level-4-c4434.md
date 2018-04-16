---
title: "コンパイラの警告 (レベル 4) C4434 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4434
dev_langs:
- C++
helpviewer_keywords:
- C4434
ms.assetid: 24b8785e-353a-4c37-8bed-ed61001a871d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a9499d145263c3bbb1bd5aac948c6be9e4db48d2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4434"></a>コンパイラの警告 (レベル 4) C4434
クラス コンストラクターはプライベート アクセシビリティを含んでいなければなりません。プライベート アクセスに変更します  
  
 C4434 は、コンパイラが静的コンストラクターのアクセシビリティを変更したことを示します。 静的コンストラクターは共通言語ランタイムからのみ呼び出されるものであるため、専用のアクセシビリティが必要です。 詳細については、次を参照してください。[静的コンス トラクター](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Static_constructors)です。  
  
## <a name="example"></a>例  
 次の例では、C4434 を生成します。  
  
```  
// C4434.cpp  
// compile with: /W4 /c /clr  
public ref struct R {  
   static R(){}   // C4434  
};  
```