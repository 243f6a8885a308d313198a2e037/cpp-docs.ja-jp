---
title: "コンパイラ エラー C3206 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3206
dev_langs:
- C++
helpviewer_keywords:
- C3206
ms.assetid: d62995b5-e349-4418-bbe8-8a5e776ca7b0
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 69e6fcd77916af3defc29dfb12381d3491e478e6
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3206"></a>コンパイラ エラー C3206
'function': 'param' の型引数が無効です。クラス型 'typename' の型引数リストがありません  
  
 テンプレート関数は、テンプレート型引数を取るものと定義されています。 しかし、テンプレート template 引数が渡されました。  
  
 次の例では C3206 が生成されます。  
  
```  
// C3206.cpp  
template <class T>  
void f() {}  
  
template <class T>  
struct S {};  
  
void f1() {  
   f<S>();   // C3206  
   // try the following line instead  
   // f<S<int> >();  
}  
```  
  
 考えられる解決策:  
  
```  
// C3206b.cpp  
// compile with: /c  
template <class T>  
void f() {}  
  
template <class T>  
struct S {};  
  
void f1() {  
   f<S<int> >();  
}  
```  
  
 C3206 は、ジェネリックを使用しているときも発生します。  
  
```  
// C3206c.cpp  
// compile with: /clr  
generic <class GT1>  
void gf() {}  
  
generic <class T>  
value struct GS {};  
  
int main() {  
   gf<GS>();   // C3206  
}  
```  
  
 考えられる解決策:  
  
```  
// C3206d.cpp  
// compile with: /clr  
generic <class GT1>  
void gf() {}  
  
generic <class T>  
value struct GS {};  
  
int main() {  
   gf<GS<int> >();  
}  
```  
  
 このエラーは、クラス テンプレートがテンプレート型引数として許可されていない Visual C++ .NET 2003 でコンパイラ準拠作業が実施された結果、生成されることもあります。  
  
 クラス テンプレートは、テンプレート型引数として許可されません。 これは、Visual C++ .NET 2003 では動作しましたが、C++ では無効です。  
  
 次の例は Visual C++ .NET 2002 ではコンパイルされますが、Visual C++ .NET 2003 では失敗します。  
  
```  
// C3206e.cpp  
template <class T>  
struct S {};  
  
template <class T>  
void func() {   // takes a type  
   T<int> t;  
}  
  
int main() {  
   func<S>();   // C3206 S is not a type.  
}  
```  
  
 考えられる解決策:  
  
```  
// C3206f.cpp  
template <class T>  
struct S {};  
  
template <class T>  
void func() {   // takes a type  
   T t;  
}  
  
int main() {  
   func<S<int> >();  
}  
```  
  
 テンプレート template パラメーターが必要な場合、Visual C++ .NET 2003 バージョンと Visual C++ .NET 2002 バージョンの両方で有効にエラーを解決するには、テンプレート template パラメーターを受け取るテンプレート クラスに関数をラップする必要があります。  
  
```  
// C3206g.cpp  
template <class T>  
struct S {};  
  
template<template<class> class TT>  
struct X {  
   static void func() {  
      TT<int> t1;  
      TT<char> t2;  
   }  
};  
  
int main() {  
   X<S>::func();  
}  
```
