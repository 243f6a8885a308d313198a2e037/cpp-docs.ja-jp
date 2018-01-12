---
title: "コンパイラの警告 (レベル 2) C4250 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4250
dev_langs: C++
helpviewer_keywords: C4250
ms.assetid: d47f7249-6b5a-414b-b2d4-56e5d246a782
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d92a337e3ded4b958bb9d1dbb7359d21f28d619c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4250"></a>コンパイラの警告 (レベル 2) C4250
'class1': 'class2::member' 支配経由での継承  
  
 2 つ以上のメンバーは、同じ名前を持ちます。 `class2`これはこのメンバーが含まれているその他のクラスの基本クラスを継承します。  
  
 C4250 を抑制するのには、使用、[警告](../../preprocessor/warning.md)プラグマ。  
  
 仮想基底クラスは、複数の派生クラスの間で共有されるため、派生クラスで名前には、基底クラスの名前がよりも優位します。 たとえば、次のクラス階層を指定するには、次の 2 つの定義が func ひし形内で継承の: 脆弱なクラスと、クラスを基準となる主要な:: func() を通じて vbc::func() インスタンス。 用のひし形のクラス オブジェクトを通じて func() の非修飾の呼び出しは、func() dominate:: インスタンスを常に呼び出します。  弱いクラスは、func() のインスタンスを導入するが場合、は、定義が圧迫は、どちらもし、呼び出しはあいまいとしてフラグがします。  
  
```  
// C4250.cpp  
// compile with: /c /W2  
#include <stdio.h>  
struct vbc {  
   virtual void func() { printf("vbc::func\n"); }  
};  
  
struct weak : public virtual vbc {};  
  
struct dominant : public virtual vbc {  
   void func() { printf("dominant::func\n"); }  
};  
  
struct diamond : public weak, public dominant {};  
  
int main() {  
   diamond d;  
   d.func();   // C4250  
}  
```  
  
## <a name="example"></a>例  
 次の例では、C4250 を生成します。  
  
```  
// C4250_b.cpp  
// compile with: /W2 /EHsc  
#include <iostream>  
using namespace std;  
class A {  
public:  
   virtual operator int () {  
      return 2;  
   }  
};  
  
class B : virtual public A {  
public:  
   virtual operator int () {  
      return 3;  
   }  
};  
  
class C : virtual public A {};  
  
class E : public B, public C {};   // C4250  
  
int main() {  
   E eObject;  
   cout << eObject.operator int() << endl;  
}  
```  
  
## <a name="example"></a>例  
 このサンプルより複雑な状況を示します。 次の例では、C4250 を生成します。  
  
```  
// C4250_c.cpp  
// compile with: /W2 /EHsc  
#include <iostream>  
using namespace std;  
  
class V {  
public:  
   virtual int f() {  
      return 1024;  
   }  
};  
  
class B : virtual public V {  
public:  
   int b() {  
      return f(); // B::b() calls V::f()  
   }  
};  
  
class M : virtual public V {  
public:  
   int f() {  
      return 7;  
   }  
};  
  
// because of dominance, f() is M::f() inside D,  
// changing the meaning of B::b's f() call inside a D  
class D : public B, public M {};   // C4250  
  
int main() {  
   D d;  
   cout << "value is: " << d.b();   // invokes M::f()  
}  
```