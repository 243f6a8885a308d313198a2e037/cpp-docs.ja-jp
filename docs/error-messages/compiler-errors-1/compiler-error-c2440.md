---
title: "コンパイラ エラー C2440 |Microsoft ドキュメント"
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2440
dev_langs:
- C++
helpviewer_keywords:
- C2440
ms.assetid: 36e6676c-f04f-4715-8ba1-f096c4bf3b44
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 0789875fee672856dbc0eff429d2363a43963940
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2440"></a>コンパイラ エラー C2440
'変換' : 'type1' から 'type2' に変換できません。  
  
コンパイラがからキャストできません。`type1`に`type2`です。  
  
## <a name="example"></a>例  
C2440 は非 const を初期化しようとする場合に発生することができます`char*`(または`wchar_t*`) C++ コードには、リテラル文字列を使用してときにコンパイラ準拠オプション[/Zc:strictStrings](../../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md)が設定されています。 C では、文字列リテラルの型が配列の`char`が、C++ では、配列の`const char`します。 次の例では C2440 エラーが生成されます。  
  
```cpp  
// C2440s.cpp  
// Build: cl /Zc:strictStrings /W3 C2440s.cpp  
// When built, the compiler emits:  
// error C2440: 'initializing' : cannot convert from 'const char [5]'   
// to 'char *'  
//        Conversion from string literal loses const qualifier (see  
// /Zc:strictStrings)  
  
int main() {  
   char* s1 = "test"; // C2440  
   const char* s2 = "tests"; // OK  
}  
```  
  
## <a name="example"></a>例  
 C2440 は、メンバーへのポインターを void* に変換しようとして発生することもあります。 次の例では C2440 が生成されます。  
  
```cpp  
// C2440.cpp  
class B {  
public:  
   void  f(){;}  
  
   typedef void (B::*pf)();  
  
   void f2(pf pf) {  
       (this->*pf)();  
       void* pp = (void*)pf;   // C2440  
   }  
  
   void f3() {  
      f2(f);  
   }  
};  
```  
  
## <a name="example"></a>例  
 C2440 は、事前宣言するだけで定義されていない型をキャストしようとした場合にも発生することがあります。 次の例では C2440 エラーが生成されます。  
  
```cpp  
// c2440a.cpp   
struct Base { }; // Defined  
  
struct Derived; // Forward declaration, not defined  
  
Base * func(Derived * d) {  
    return static_cast<Base *>(d); // error C2440: 'static_cast' : cannot convert from 'Derived *' to 'Base *'  
}  
  
```  
  
## <a name="example"></a>例  
 次の例の 15 行目と 16 行目の C2440 エラーには、"`Incompatible calling conventions for UDT return value` (UDT 戻り値の呼び出し規約に互換性がありません)" というメッセージが表示されます。 A *UDT*クラス、構造体、共用体などのユーザー定義の型です。 このような種類の非互換性エラーが発生するのは、事前宣言の戻り値の型で指定された UDT の呼び出し規約が UDT の実際の呼び出し規約と競合する場合や、関数ポインターが関連する場合です。  
  
 この例では、最初に、構造体およびその構造体を返す関数の事前宣言があります。コンパイラでは、この構造体で C++ 呼び出し規約が使用されると仮定します。 次に、構造体の定義があります。既定では、この定義は C 呼び出し規約を使用します。 コンパイラでは、構造体全体の読み込みが完了するまでは、その構造体の呼び出し規約がわからないため、`get_c2` の戻り値の型での構造体の呼び出し規約も C++ であると仮定します。  
  
 構造体の後には構造体を返す別の関数宣言が続きますが、この時点では、コンパイラは構造体の呼び出し規約が C++ であることを認識しています。 同様に、構造体を返す関数ポインターは構造体定義の後に定義されているため、コンパイラはその構造体で C++ 呼び出し規約が使用されることを認識します。  
  
 互換性のない 2 つの呼び出し規則が原因で発生する C2440 エラーを解決するには、UDT の定義の後にその UDT を返す関数を宣言します。  
  
```cpp  
// C2440b.cpp  
struct MyStruct;  
  
MyStruct get_c1();  
  
struct MyStruct {  
   int i;  
   static MyStruct get_C2();  
};  
  
MyStruct get_C3();  
  
typedef MyStruct (*FC)();  
  
FC fc1 = &get_c1;   // C2440, line 15  
FC fc2 = &MyStruct::get_C2;   // C2440, line 16  
FC fc3 = &get_C3;  
  
class CMyClass {  
public:  
   explicit CMyClass( int iBar)  
      throw()   {  
   }  
  
   static CMyClass get_c2();  
};  
  
int main() {  
   CMyClass myclass = 2;   // C2440  
   // try one of the following  
   // CMyClass myclass{2};  
   // CMyClass myclass(2);  
  
   int *i;  
   float j;  
   j = (float)i;   // C2440, cannot cast from pointer to int to float  
}  
```  
  
## <a name="example"></a>例  
 C2440 は、内部ポインターに 0 を割り当てた場合にも発生することがあります。  
  
```cpp  
// C2440c.cpp  
// compile with: /clr  
int main() {  
   array<int>^ arr = gcnew array<int>(100);  
   interior_ptr<int> ipi = &arr[0];  
   ipi = 0;   // C2440  
   ipi = nullptr;   // OK  
}  
```  
  
## <a name="example"></a>例  
 C2440 は、ユーザー定義の規約の使用方法が間違っている場合にも発生することがあります。 たとえば、ときに、変換演算子として定義されている`explicit`コンパイラが暗黙的な変換で使用できません。 ユーザー定義の変換の詳細については、次を参照してください。[ユーザー定義の変換 (C + + CLI)](../../dotnet/user-defined-conversions-cpp-cli.md))。 次の例では C2440 エラーが生成されます。  
  
```cpp  
// C2440d.cpp  
// compile with: /clr  
value struct MyDouble {  
   double d;  
   // convert MyDouble to Int32  
   static explicit operator System::Int32 ( MyDouble val ) {  
      return (int)val.d;  
   }  
};  
  
int main() {  
   MyDouble d;  
   int i;  
   i = d;   // C2440  
   // Uncomment the following line to resolve.  
   // i = static_cast<int>(d);  
}  
```  
  
## <a name="example"></a>例  
 C2440 は、 <xref:System.Array>。</xref:System.Array>である型が Visual C 配列のインスタンスを作成しようとする場合にも発生することができます。  詳細については、次を参照してください。[配列](../../windows/arrays-cpp-component-extensions.md)です。  次の例では C2440 が生成されます。  
  
```cpp  
// C2440e.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   array<int>^ intArray = Array::CreateInstance(__typeof(int), 1);   // C2440  
   // try the following line instead  
   // array<int>^ intArray = safe_cast<array<int> ^>(Array::CreateInstance(__typeof(int), 1));  
}  
```  
  
## <a name="example"></a>例  
 C2440 は、属性機能の変更が原因で発生することもあります。  次の例では C2440 エラーが生成されます。  
  
```cpp  
// c2440f.cpp  
// compile with: /LD  
[ module(name="PropDemoLib", version=1.0) ];   // C2440  
// try the following line instead  
// [ module(name="PropDemoLib", version="1.0") ];  
```  
  
## <a name="example"></a>例  
 Visual C コンパイラは、不要になった、 [const_cast 演算子](../../cpp/const-cast-operator.md)ダウン キャストするときにソース コードを使用する**/clr**プログラミングがコンパイルされました。  
  
 この C2440 エラーを解決するには、正しいキャスト演算子を使用します。 詳細については、次を参照してください。[キャスト演算子](../../cpp/casting-operators.md)です。  
  
 次の例では C2440 エラーが生成されます。  
  
```cpp  
// c2440g.cpp  
// compile with: /clr  
ref class Base {};  
ref class Derived : public Base {};  
int main() {  
   Derived ^d = gcnew Derived;  
   Base ^b = d;  
   d = const_cast<Derived^>(b);   // C2440  
   d = dynamic_cast<Derived^>(b);   // OK  
}  
```  
  
## <a name="example"></a>例  
C2440 を Visual Studio 2015 Update 3 でコンパイラ準拠の変更のために発生します。 以前は、コンパイラ正しくとして扱われましていない特定れる個別の式、同じ種類のテンプレートの一致を識別するときに、`static_cast`操作します。 これで、コンパイラは型を正しく区別し、コードを全面的に頼るで前の`static_cast`動作が中断します。 この問題を解決するため、テンプレート パラメーターの型を一致または使用するテンプレート引数を変更して、`reinterpret_cast`または C スタイル キャストが必要です。
  
次の例では C2440 エラーが生成されます。  
  
```cpp  
// c2440h.cpp

template<int *a>
struct S1 {};

int g;
struct S2 : S1<&g> {
};

int main()
{
    S2 s;
    static_cast<S1<&*&g>>(s); // C2440 in VS 2015 Update 3 
    // This compiles correctly:
    // static_cast<S1<&g>>(s);
}

This error can appear in ATL code that uses the SINK_ENTRY_INFO macro defined in <atlcom.h>.

```

## <a name="example"></a>例  
### <a name="copy-list-initialization"></a>Copy-list-initialization

2017 およびそれ以降の visual Studio が正しく初期化子リストが Visual Studio 2015 でキャッチされていないと、クラッシュする可能性がありますを使用してオブジェクトの作成に関連するコンパイラ エラーを発生させるか、実行時の動作は未定義です。 C++ 17 のコピーでリストの初期化、コンパイラはオーバー ロードの解決、明示的なコンス トラクターを考慮する必要しますが、そのオーバー ロードが実際選択される場合、エラーが発生する必要があります。

次の例では、Visual Studio 2015 ではなく Visual Studio 2017 をコンパイルします。

```cpp  
// C2440j.cpp  
struct A
{
    explicit A(int) {} 
    A(double) {}
};

int main()
{
    const A& a2 = { 1 }; // error C2440: 'initializing': cannot 
                         // convert from 'int' to 'const A &'
}
```  
  
このエラーを修正するには、直接の初期化を使用します。  
  
```cpp  
// C2440k.cpp  
struct A
{
    explicit A(int) {} 
    A(double) {}
};

int main()
{
    const A& a2{ 1 };
}  
```  

## <a name="example"></a>例
### <a name="cv-qualifiers-in-class-construction"></a>クラス コンストラクションの cv 修飾子

Visual Studio 2015 では、コンストラクターを呼び出してクラス オブジェクトを生成するときに、コンパイラが誤って cv 修飾子を無視することがあります。 これにより、クラッシュまたは予期しない実行時動作が発生する可能性があります。 次の例では、Visual Studio 2015 でコンパイルしますが、Visual Studio 2017 以降、コンパイラ エラーを発生させます。

```cpp
struct S 
{
    S(int);
    operator int();
};

int i = (const S)0; // error C2440
```

エラーを解決するには、operator int() を定数として宣言します。

