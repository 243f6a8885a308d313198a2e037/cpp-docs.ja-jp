---
title: "関数テンプレートの明示的特殊化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- overriding, functions
- function templates, specialization
- explicit specialization of function templates
- declaring functions [C++], specialization of function template
- specialization of function templates
ms.assetid: eb0fcb73-eaed-42a1-9b83-14b055a34bf8
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: f460497071445cff87308fa9bf6e0d43c6f13a3e
ms.openlocfilehash: c5caabae41383edbdc92806249026ce8a0daa5d5
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="explicit-specialization-of-function-templates"></a>関数テンプレートの明示的特殊化
関数テンプレートを使用すると、特定の型のために関数テンプレートの明示的な特殊化 (オーバーライド) を提供することによって、その型の特別な動作を定義できます。 例:  
  
```cpp
template<> void MySwap(double a, double b);  
```  
  
 この宣言では、別の関数を定義できます。**二重**変数。 などの非テンプレート関数、標準的な型変換 (型の変数を昇格させるなど**float**に**二重**) 適用されます。  
  
## <a name="example"></a>例  
  
```cpp
// explicit_specialization.cpp  
template<class T> void f(T t)  
{  
};  
  
// Explicit specialization of f with 'char' with the  
// template argument explicitly specified:  
//  
template<> void f<char>(char c)  
{  
}  
  
// Explicit specialization of f with 'double' with the  
// template argument deduced:  
//  
template<> void f(double d)  
{  
}  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [関数テンプレート](../cpp/function-templates.md)

