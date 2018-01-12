---
title: "コンパイラ エラー C2668 |Microsoft ドキュメント"
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2668
dev_langs: C++
helpviewer_keywords: C2668
ms.assetid: 041e9627-1c76-420e-a653-cfc83f933bd3
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e45bff3173013e7a26f9682bb10ec4cc1fda9364
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2668"></a>コンパイラ エラー c2668 を発行
'function': オーバー ロードされた関数のあいまいな呼び出し  
  
 指定されたオーバー ロードされた関数の呼び出しを解決できませんでした。 1 つ以上の実際のパラメーターを明示的にキャストすることがあります。  
  
 このエラーは、テンプレートを使用して取得することもできます。 同じクラスである場合は、通常のメンバー関数と同じシグネチャを持つ template 宣言されたメンバー関数場合、テンプレートのいずれかが先にする必要があります。 これは、Visual C の現在の実装の制限です。  
  
 関数テンプレートの部分的な順序付けの詳細については、サポート技術情報資料 Q240869 を参照してください。  
  
 サポートする COM オブジェクトを格納している ATL プロジェクトをビルドするかどうかは`ISupportErrorInfo`、サポート技術情報の記事 Q243298 を参照してください。  
  
## <a name="example"></a>例  
 次の例では C2668 が生成されます。  
  
```  
// C2668.cpp  
struct A {};  
struct B : A {};  
struct X {};  
struct D : B, X {};  
  
void func( X, X ){}  
void func( A, B ){}  
D d;  
int main() {  
   func( d, d );   // C2668 D has an A, B, and X   
   func( (X)d, (X)d );   // OK, uses func( X, X )  
}  
```  
  
## <a name="example"></a>例  
 このエラーを解決する別の方法は、[宣言を使用して](../../cpp/using-declaration.md):  
  
```  
// C2668b.cpp  
// compile with: /EHsc /c  
// C2668 expected  
#include <iostream>  
class TypeA {  
public:  
   TypeA(int value) {}  
};  
  
class TypeB {  
   TypeB(int intValue);  
   TypeB(double dbValue);  
};  
  
class TestCase {  
public:  
   void AssertEqual(long expected, long actual, std::string  
                    conditionExpression = "");  
};  
  
class AppTestCase : public TestCase {  
public:  
   // Uncomment the following line to resolve.  
   // using TestCase::AssertEqual;  
   void AssertEqual(const TypeA expected, const TypeA actual,  
                    std::string conditionExpression = "");  
   void AssertEqual(const TypeB expected, const TypeB actual,  
                    std::string conditionExpression = "");  
};  
  
class MyTestCase : public AppTestCase {  
   void TestSomething() {  
      int actual = 0;  
      AssertEqual(0, actual, "Value");  
   }  
};  
```  
  
## <a name="example"></a>例  
 このエラーは、Visual Studio .NET 2003 で行ったコンパイラ準拠作業の結果として生成することもできます: 定数 0 のキャストであいまいな変換です。  
  
 Int では、時間、および void * を両方への変換が必要なために、定数 0 を使用してキャストの変換があいまいです。 このエラーを解決するには、0 に変換する必要がありますされません (このコードが有効になります、Visual Studio .NET 2003 バージョンと Visual Studio .NET バージョンの Visual C で) 実行されるようには、使用されている関数のパラメーターの正確な型をキャストします。  
  
```  
// C2668c.cpp  
#include "stdio.h"  
void f(long) {  
   printf_s("in f(long)\n");  
}  
void f(void*) {  
   printf_s("in f(void*)\n");  
}  
int main() {  
   f((int)0);   // C2668  
  
   // OK  
   f((long)0);  
   f((void*)0);  
}  
```  
  
## <a name="example"></a>例  
 このエラーは、CRT は float 型とすべての数値演算関数の 2 つのフォームを持つために発生することができます。  
  
```  
// C2668d.cpp  
#include <math.h>  
int main() {  
   int i = 0;  
   float f;  
   f = cos(i);   // C2668  
   f = cos((float)i);   // OK  
}  
```  
  
## <a name="example"></a>例  
 Pow (int, int) は、CRT で math.h から削除されたために、このエラーが発生することができます。  
  
```  
// C2668e.cpp  
#include <math.h>  
int main() {  
   pow(9,9);   // C2668  
   pow((double)9,9);   // OK  
}  
```

## <a name="example"></a>例  
このコードは、Visual Studio 2015 では成功しますが、c2668 を発行の後で使用して、Visual Studio 2017 では失敗します。 Visual Studio 2015 では、コンパイラは、誤って copy-list-initialization を通常の copy-initialization と同じ方法で処理しました。これは、単なるオーバーロードの解決のためのコンストラクターの変換と見なされます。 

```
C++
struct A {
    explicit A(int) {}
};

struct B {
    B(int) {}
};

void f(const A&) {}
void f(const B&) {}

int main()
{
    f({ 1 }); // error C2668: 'f': ambiguous call to overloaded function
}
```