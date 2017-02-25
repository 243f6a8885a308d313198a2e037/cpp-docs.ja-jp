---
title: "CLR 配列の宣言 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "array キーワード [C++]"
ms.assetid: 36a8883c-2663-43f0-a90c-28f27035e036
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CLR 配列の宣言
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

マネージ型配列の宣言、インスタンス化、および初期化は、[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] では C\+\+ マネージ拡張から変更されています。  
  
 マネージ拡張での CLR 配列オブジェクトの宣言は、標準的な配列宣言を拡張したもので、次の 2 つの例のように、配列オブジェクトの名前と多くの場合はコンマで満たされた次元との間に `__gc` キーワードが配置されていました。  
  
```  
void PrintValues( Object* myArr __gc[]);  
void PrintValues( int myArr __gc[,,]);  
```  
  
 新しい構文では宣言が単純化され、STL `vector` 宣言に似た、テンプレートのような宣言を使用します。  最初のパラメーターは要素型を示します。  2 番目のパラメーターは、配列の次元です \(既定値は 1 なので、複数次元の場合だけ 2 番目の引数が必要です\)。  配列自身はトラッキング ハンドルであるため、キャレットを付ける必要があります。  要素の型も参照型である場合、要素の型にもキャレットが必要です。  たとえば、上の例を新しい構文で表すと次のようになります。  
  
```  
void PrintValues( array<Object^>^ myArr );  
void PrintValues( array<int,3>^ myArr );  
```  
  
 参照型はオブジェクトではなく追跡ハンドルであるため、CLR 配列を関数の戻り値の型として指定できます \(これに対し、ネイティブ配列は関数の戻り値の型として指定できません\)。マネージ拡張でこれを行うと、少し直感的でない構文になります。  たとえば、次のようになります。  
  
```  
Int32 f() [];  
int GetArray() __gc[];  
```  
  
 [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] では、宣言が大幅に単純化されています。  次に例を示します。  
  
```  
array<Int32>^ f();  
array<int>^ GetArray();  
```  
  
 どちらの言語でも、ローカルなマネージ配列を簡単に初期化できます。  たとえば、次のようになります。  
  
```  
int GetArray() __gc[] {  
   int a1 __gc[] = { 1, 2, 3, 4, 5 };  
   Object* myObjArray __gc[] = {   
      __box(26), __box(27), __box(28), __box(29), __box(30)  
   };  
   return a1;  
}  
```  
  
 新しい構文では、かなり単純化されています \(新しい構文ではボックス化が暗黙で行われるため、`__box` 演算子がなくなっています。詳細については、「[値型とその動作 \(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)」を参照してください\)。  
  
```  
array<int>^ GetArray() {  
   array<int>^ a1 = {1,2,3,4,5};  
   array<Object^>^ myObjArray = {26,27,28,29,30};  
   return a1;  
}  
```  
  
 配列は CLR 参照型であるため、各配列オブジェクトの宣言は追跡ハンドルです。  したがって、配列オブジェクトは CLR ヒープに割り当てる必要があります\(略式の表記ではマネージ ヒープの割り当ては表示されません\)。次に、マネージ拡張で配列オブジェクトを明示的に初期化する方法を示します。  
  
```  
Object* myArray[] = new Object*[2];  
String* myMat[,] = new String*[4,4];  
```  
  
 新しい構文では、`new` 式の代わりに `gcnew` を使用します。  次元サイズは、次のようにパラメーターとして `gcnew` 式に渡されます。  
  
```  
array<Object^>^ myArray = gcnew array<Object^>(2);  
array<String^,2>^ myMat = gcnew array<String^,2>(4,4);  
```  
  
 新しい構文では、`gcnew` 式の後に明示的な初期化リストを含めることができます。これは、マネージ拡張ではサポートされていませんでした。  たとえば、次のようになります。  
  
```  
// explicit initialization list following gcnew   
// was not supported in Managed Extensions  
array<Object^>^ myArray =   
   gcnew array<Object^>(4){ 1, 1, 2, 3 };  
```  
  
## 参照  
 [マネージ型 \(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)   
 [Arrays](../windows/arrays-cpp-component-extensions.md)