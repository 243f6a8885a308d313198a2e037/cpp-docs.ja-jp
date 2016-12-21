---
title: "Compiler Error C2921 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2921"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2921"
ms.assetid: 323642a0-bfc4-4942-9f41-c3adf5c54296
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Compiler Error C2921
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

再定義 : 'class' : クラス テンプレートまたはジェネリックは 'type' として宣言されます。  
  
 ジェネリックまたはクラス テンプレートに複数の等しくない宣言が存在します。  このエラーを修正するには、型ごとに異なる名前を使用するか、型名の再定義を削除します。  
  
 次の例では、C2921 エラーが生成されます。  
  
```  
// C2921.cpp  
// compile with: /c  
template <class T> struct TC2 {};  
typedef int TC2;   // C2921  
// try the following line instead  
// typedef struct TC2<int> x;   // OK - declare a template instance   
```  
  
 C2921 は、ジェネリックを使用する場合にも発生することがあります。  
  
```  
// C2921b.cpp  
// compile with: /clr /c  
generic <class T> ref struct GC2 {};  
typedef int GC2;   // C2921  
// try the following line instead  
// typedef ref struct GC2<int> x;  
```