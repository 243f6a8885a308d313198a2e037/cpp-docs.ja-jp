---
title: "コンパイラ エラー C2299 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2299
dev_langs: C++
helpviewer_keywords: C2299
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8190511605a7f01dc399e1d8a8b4af96477fa407
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2299"></a>コンパイラ エラー C2299
'function': 動作変更: 明示的な特殊化することはできません、コピー コンス トラクターまたはコピー代入演算子  
  
 このエラーは、Visual C 2005 で行ったコンパイラ準拠作業の結果として生成することもできます。 Visual c の以前のバージョンがコピー コンス トラクターまたはコピー代入演算子の明示的な特殊化を許可します。  
  
 C2299 を解決するのにはしないでください、コピー コンス トラクターまたは代入演算子、テンプレート関数がクラス型を受け取る非テンプレート関数ではなく。 テンプレート引数を明示的に指定して、コピー コンス トラクターまたは代入演算子を呼び出すコードでは、テンプレート引数を削除する必要があります。  
  
 次の例では、C2299 が生成されます。  
  
```  
// C2299.cpp  
// compile with: /c  
class C {  
   template <class T>  
   C (T t);  
  
   template <> C (const C&);   // C2299  
   C (const C&);   // OK  
};  
```