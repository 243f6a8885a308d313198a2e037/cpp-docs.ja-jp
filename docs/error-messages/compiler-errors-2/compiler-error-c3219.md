---
title: コンパイラ エラー C3219 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3219
dev_langs:
- C++
helpviewer_keywords:
- C3219
ms.assetid: 9c9757b0-1256-4cdf-9d8c-a3a72f300ce5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 16341412ae5028753b2a542b45da4ea2b549c29e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33248646"
---
# <a name="compiler-error-c3219"></a>コンパイラ エラー C3219
'param': ジェネリック パラメーターを、インターフェイスでない複数の 'class' によって制限することはできません  
  
 2 つ以上のマネージ クラスでジェネリック パラメーターを制限することはできません。  
  
 次の例では、C3219 が生成されます。  
  
```  
// C3219.cpp  
// compile with: /clr  
ref class A {};  
ref class B {};  
  
generic <class T>  
where T : A, B  
ref class E {};   // C3219  
```  
  
 次の例では、考えられる解決策を示しています。  
  
```  
// C3219b.cpp  
// compile with: /clr /c  
ref class A {};  
  
interface struct C {};  
  
generic <class T>  
where T : A  
ref class E {};  
```