---
title: "デストラクター (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- objects [C++], destroying
- Visual C++, destructors
- destroying objects, destructors
- ~ operator [C++], specifying destructors
- destructors, about destructors
- destructors, C++
ms.assetid: afa859b0-f3bc-4c4d-b250-c68b335b6004
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 37aa5ab5cad2367bfc37e2e1b6fd886540eada8e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="destructors-c"></a>デストラクター (C++)
デストラクターは、オブジェクトがスコープ外に出るかへの呼び出しによって明示的に破棄されるときに自動的に呼び出されるメンバー関数`delete`です。 デストラクターが、クラスと同じ名前の前にティルダ (`~`)。 たとえば、クラス `String` のデストラクターを宣言するには、`~String()` とします。 コンパイラが表示されます。 既定値を提供デストラクターを定義していない場合多くのクラスこれで十分です。 クラスは、解放する必要があるシステム リソースへのハンドルを格納する場合は、カスタムのデストラクターを定義するだけ済みます。 またはをポイントしているメモリを所有するポインター。

`String` クラスの次のような宣言があるとします。  
  
```  
// spec1_destructors.cpp  
#include <string.h>  
  
class String {  
public:  
   String( char *ch );  // Declare constructor  
   ~String();           //  and destructor.  
private:  
   char    *_text;  
   size_t  sizeOfText;  
};  
  
// Define the constructor.  
String::String( char *ch ) {  
   sizeOfText = strlen( ch ) + 1;  
  
   // Dynamically allocate the correct amount of memory.  
   _text = new char[ sizeOfText ];  
  
   // If the allocation succeeds, copy the initialization string.  
   if( _text )  
      strcpy_s( _text, sizeOfText, ch );  
}  
  
// Define the destructor.  
String::~String() {  
   // Deallocate the memory that was previously reserved  
   //  for this string.  
   if (_text)  
      delete[] _text;  
}  
  
int main() {  
   String str("The piper in the glen...");  
}  
```  
  
 上の例では、デストラクター `String::~String` が `delete` 演算子を使用して、テキストの保存のために動的に割り当てられた領域を解放します。  
  
## <a name="declaring-destructors"></a>デストラクターの宣言  
 デストラクターはクラスと同じ名前の関数ですが、先頭にティルダ (`~`) が付きます。  
  
 デストラクターの宣言には以下の規則が適用されます 。  
  
-   デストラクタ―は引数を受け取りません。  
  
-   値は返されません (または`void`)。  
  
-   として宣言することはできません**const**、 `volatile`、または**静的**です。 ただし、呼び出すことができますとして宣言されているオブジェクトの破棄の**const**、 `volatile`、または**静的**です。  
  
-   として宣言できます**仮想**です。 仮想デストラクターを使用すると、型を知らなくてもオブジェクトを破棄できます。オブジェクトの正しいデストラクターが、仮想関数のメカニズムを使用して呼び出されます。 デストラクターは、抽象クラスの純粋仮想関数として宣言することもできます。  
  
## <a name="using-destructors"></a>デストラクターの使用  
 デストラクターは、次のいずれかのイベントが発生したときに呼び出されます。  

-   ブロック スコープを持つローカル (自動) オブジェクトがスコープから外れます。  

-   使用して割り当てられたオブジェクト、**新しい**演算子が明示的に割り当て解除を使用して**削除**です。   
  
-   一時オブジェクトの有効期間は終了します。  
  
-   プログラムは終了し、グローバルまたはスタティック オブジェクトが存在します。  
  
-   デストラクターは、デストラクター関数の完全修飾名を使用して明示的に呼び出されます 
  
 デストラクターは、自由にクラス メンバー関数を呼び出したり、クラス メンバーのデータにアクセスしたりできます。
  
 これにはデストラクターの使用は、2 つの制限があります。
 - そのアドレスを取得することはできません。
-  派生クラスでは、その基本クラスのデストラクターは継承されません。
  
## <a name="order-of-destruction"></a>破棄の順序  
 オブジェクトがスコープ外になるとき、または削除されるとき、完全な破棄のイベントの順序は次のとおりです。  
  
1.  クラスのデストラクターが呼び出され、デストラクター関数の本体が実行されます。  
  
2.  非静的メンバー オブジェクトのデストラクターは、クラス宣言での出現順序の逆順で呼び出されます。 これらのメンバーの構築に使用される省略可能なメンバー初期化リストでは、構築または破棄の順序は影響しません。   
  
3.  非仮想基底クラスのデストラクターは、宣言の逆順で呼び出されます。  
  
4.  仮想基底クラスのデストラクターは、宣言の逆順で呼び出されます。  
  
```  
// order_of_destruction.cpp  
#include <stdio.h>  
  
struct A1      { virtual ~A1() { printf("A1 dtor\n"); } };  
struct A2 : A1 { virtual ~A2() { printf("A2 dtor\n"); } };  
struct A3 : A2 { virtual ~A3() { printf("A3 dtor\n"); } };  
  
struct B1      { ~B1() { printf("B1 dtor\n"); } };  
struct B2 : B1 { ~B2() { printf("B2 dtor\n"); } };  
struct B3 : B2 { ~B3() { printf("B3 dtor\n"); } };  
  
int main() {  
   A1 * a = new A3;  
   delete a;  
   printf("\n");  
  
   B1 * b = new B3;  
   delete b;  
   printf("\n");  
  
   B3 * b2 = new B3;  
   delete b2;  
}  
  
Output: A3 dtor  
A2 dtor  
A1 dtor  
  
B1 dtor  
  
B3 dtor  
B2 dtor  
B1 dtor  
  
```  
  
### <a name="virtual-base-classes"></a>仮想基底クラス  
 仮想基底クラスのデストラクターが有向非循環グラフ (深さ優先、左から右、後順走査) で外観の逆の順序で呼び出されます。 次の図は、継承グラフを示しています。  
  
 ![仮想基底クラスを示す継承グラフ](../cpp/media/vc392j1.gif "vc392J1")  
仮想基底クラスを示す継承グラフ  
  
 図に示されているクラスの先頭を次に示します。  
  
```  
class A  
class B  
class C : virtual public A, virtual public B  
class D : virtual public A, virtual public B  
class E : public C, public D, virtual public B  
```  
  
 コンパイラは、`E` 型のオブジェクトの仮想基底クラスの破棄の順序を決定するため、次のアルゴリズムを適用してリストを作成します。  
  
1.  グラフを左に走査し、グラフの最も深いポイント (この場合は `E`) で開始します。  
  
2.  すべてのノードが表示されるまで左方向への走査を実行します。 現在のノードの名前を確認します。  
  
3.  保持するノードが仮想基底クラスであるかどうかを確認するために、前のノード (右下隅) を再表示します。  
  
4.  保持するノードが仮想基底クラスである場合は、既に構成されているかどうかを参照するために、リストを確認します。 仮想基底クラスでない場合は無視します。  
  
5.  保持するノードがリストにない場合は、リストの末尾に追加します。  
  
6.  上方向および次のパスに沿って右へグラフを走査します。  
  
7.  手順 2. に進みます。  
  
8.  最後の上方向のパスが使い果たされたら、現在のノードの名前を確認します。  
  
9. 手順 3. に進みます。  
  
10. 下部のノードが再び現在のノードになるまで、このプロセスを続行します。  
  
 したがって、クラス `E` の場合、破棄の順序は次のようになります。  
  
1.  非仮想基底クラス `E`。  
  
2.  非仮想基底クラス `D`。  
  
3.  非仮想基底クラス `C`。  
  
4.  仮想基底クラス `B`。  
  
5.  仮想基底クラス `A`。  
  
 このプロセスにより、一意のエントリの順序付きリストが作成されます。 いずれのクラス名も、2 回表示されることはありません。 リストが構築されると、逆順で走査され、リストの各クラスのデストラクターが最後から最初まで呼び出されます。  
  
 構築または破棄の順序は、1 つのクラスのコンストラクターまたはデストラクターが、初めて作成されるか、より長く保持されている他のコンポーネントに依存する場合に、特に重要になります。たとえば、コードが実行されたときに (上記の図に示す) `A` のデストラクター (上記の図に示す) がまだ存在している `B` に依存している場合や、その逆の場合です。  
  
 継承グラフでのクラス間のこのような依存関係は、後で派生するクラスが左端のパスを変更し、それによって構築と破棄の順序を変更できるため、本質的に危険です。  
  
### <a name="nonvirtual-base-classes"></a>非仮想基底クラス  
 非仮想基底クラスのデストラクターは、基底クラスの名前を宣言した順序と逆の順序で呼び出されます。 クラス宣言の例を次に示します。  
  
```  
class MultInherit : public Base1, public Base2  
...  
```  
  
 前の例では、`Base2` のデストラクターは、`Base1` のデストラクターの前に呼び出されます。  
  
## <a name="explicit-destructor-calls"></a>明示的なデストラクター呼び出し  
 デストラクターを明示的に呼び出す必要はほとんどありません。 ただし、絶対アドレスにあるオブジェクトのクリーンアップを実行すると便利な場合があります。 これらのオブジェクトは、ユーザー定義を使用して割り当てられている一般的**新しい**配置引数を受け取る演算子。 **削除**フリー ストアからが割り当てられないために、演算子はこのメモリを解放できません (詳細については、次を参照してください。[新しい演算子と delete 演算子](../cpp/new-and-delete-operators.md))。 ただし、デストラクターへの呼び出しは適切なクリーンアップを実行できます。 オブジェクトのデストラクターを明示的に呼び出すには、`s` (`String` クラス) で次のいずれかのステートメントを使用します。  
  
```  
s.String::~String();     // Nonvirtual call  
ps->String::~String();   // Nonvirtual call  
  
s.~String();       // Virtual call  
ps->~String();     // Virtual call  
```  
  
 先に示したデストラクターへの明示的な呼び出しの表記は、型がデストラクターを定義するかどうかにかかわらず使用できます。 これにより、デストラクターが型に対して定義されているかどうかを確認せずにこのような明示的な呼び出しを行うことができます。 何も定義されていないデストラクターへの明示的な呼び出しは無効です。  
