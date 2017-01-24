---
title: "コンパイラ エラー C3390 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3390"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3390"
ms.assetid: 84800a87-c8e6-45aa-82ae-02f816dc8d97
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3390
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type\_arg' : ジェネリック 'generic\_type' のジェネリック パラメーター 'param' の型引数が無効です。参照型でなければなりません  
  
 ジェネリック型のインスタンス化が正しく行われませんでした。  型定義を確認してください。  詳細については、「[Generics](../../windows/generics-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
 次の例では、C\# を使用してジェネリック型を含むコンポーネントを作成していますが、[!INCLUDE[vcprvclong](../../error-messages/compiler-errors-2/includes/vcprvclong_md.md)] でジェネリック型を作成するときにはサポートされない特定の制約があります。 詳細については、「[型パラメーターの制約](../Topic/Constraints%20on%20Type%20Parameters%20\(C%23%20Programming%20Guide\).md)」を参照してください。  
  
```  
// C3390.cs // compile with: /target:library // a C# program public class GR<C, V, N> where C : class where V : struct where N : new() {}  
```  
  
## 使用例  
 次の例では C3390 が生成されます。  
  
```  
// C3390_b.cpp // compile with: /clr #using <C3390.dll> ref class R { R(int) {} }; value class V {}; ref struct N { N() {} }; int main () { GR<V, V, N^>^ gr2;   // C3390 first type must be a ref type GR<R^, V, N^>^ gr2b;   // OK }  
```