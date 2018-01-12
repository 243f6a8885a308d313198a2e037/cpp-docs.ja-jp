---
title: "コンパイラの警告 (レベル 1) C4002 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4002
dev_langs: C++
helpviewer_keywords: C4002
ms.assetid: 6bda1dfe-e2e4-4771-9794-5a404c466dd5
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c11b40f29ccbd0e58afdce08463a87dc71181d6a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4002"></a>コンパイラの警告 (レベル 1) C4002
マクロ 'identifier' に指定された実引数の数が多すぎます  
  
 マクロの実引数の数が、マクロ定義の仮引数の数を超えています。 余分な引数はプリプロセッサによって収集されますが、マクロの展開時には無視されます。  
  
 C4002 は、 [Variadic Macros](../../preprocessor/variadic-macros.md)が正しく使用されていない場合に発生する可能性があります。  
  
 次の例では C4002 が生成されます。  
  
```  
// C4002.cpp  
// compile with: /W1  
#define test(a) (a)  
  
int main() {  
   int a = 1;  
   int b = 2;  
   a = test(a,b);   // C4002  
   // try..  
   a = test(a);  
}  
```  
  
 このエラーは、マクロで余分なコンマを使用できない Visual Studio .NET 2003 でコンパイラ準拠作業が実施された結果、生成されることもあります。  
  
 コンパイラでは、マクロ内の余分なコンマが使用できなくなります。 Visual Studio .NET 2003 と Visual Studio .NET の両方のバージョンの Visual C++ でコードを有効にするには、余分なコンマを削除します。  
  
```  
// C4002b.cpp  
// compile with: /W1  
#define F(x,y)  
int main()  
{  
   F(2,,,,,,3,,,,,,)   // C4002  
   // Try the following line instead:  
   // F(2,3)  
}  
```