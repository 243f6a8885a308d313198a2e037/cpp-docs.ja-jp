---
title: "後置式 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "式 [C++], 後置"
  - "演算子 [C++], 後置"
  - "後置式"
ms.assetid: 7ac62a57-06df-422f-b012-a75b37d7cb9b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 後置式
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

後置式は、1 次式、または後置演算子が 1 次式に続く式で構成されます。  次の表は、後置演算子の一覧です。  
  
### 後置演算子  
  
|演算子名|演算子表記|  
|----------|-----------|  
|[添字演算子](../Topic/Subscript%20Operator:.md)|**\[ \]**|  
|[関数呼び出し演算子](../cpp/function-call-operator-parens.md)|**\( \)**|  
|[明示的な型変換演算子](../Topic/Explicit%20Type%20Conversion%20Operator:%20\(\).md)|*type\-name* **\( \)**|  
|[メンバー アクセス演算子](../Topic/Member%20Access%20Operators:%20.%20and%20-%3E.md)|**.** または **–\>**|  
|[後置インクリメント演算子](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|`++`|  
|[後置デクリメント演算子](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)|**––**|  
  
 次の構文は、可能な後置式について説明しています。  
  
```  
  
          primary-expression   
postfix-expression [ expression ]  
postfix-expression ( expression-list)  
simple-type-name ( expression-list)  
postfix-expression . name  
postfix-expression –> name  
postfix-expression ++  
postfix-expression ––  
cast-keyword < typename > (expression ) typeid ( typename )  
```  
  
 上の *postfix\-expression* は、1 次式または別の後置式である可能性があります。  「**1 次式**」を参照してください。  後置式は左から右へグループ化されるため、次のように式を連結できます。  
  
```  
func(1)->GetValue()++  
```  
  
 上の式では、func は 1 次式で、func\(1\) は関数後置式です。func\(1\)\-\>GetData は、クラスのメンバーを指定する後置式です。func\(1\)\-\>GetData\(\) は、もう 1 つの関数後置式です。式全体は GetData の戻り値をインクリメントする後置式です。  全体として式の意味は、「引数として 1 を渡す関数を呼び出し、戻り値としてクラスへのポインターを取得します。  次に、そのクラスで GetValue\(\) を呼び出し、返される値をインクリメントします。  
  
 前の式は、代入式です。つまり、これらの式の結果が右辺値である必要があります。  
  
 後置式のフォーム  
  
```  
simple-type-name ( expression-list )  
```  
  
 コンストラクターの呼び出しを示します。  単純型名が基本型である場合、式リストは 1 つの式である必要があります。また、この式は、基本型への式の値のキャストを示します。  この型のキャスト式はコンストラクターを模倣します。  この形式は同じ構文を使用して構築されている基本型とクラスを使用するため、この形式はテンプレート クラスを定義する場合に特に便利です。  
  
 *cast\-keyword* は、`dynamic_cast`、`static_cast`、または `reinterpret_cast` です。  詳細については、「**dynamic\_cast**」、「**static\_cast**」、および「**reinterpet\_cast**」を参照してください。  
  
 `typeid` 演算子は、後置式と見なされます。  「**typeid 演算子**」を参照してください。  
  
## 仮引数と実引数  
 呼び出し元のプログラムは "実引数" の呼び出された関数に情報を渡します。 呼び出された関数は、対応する "仮引数" を使用して情報にアクセスします。  
  
 関数が呼び出されると、次のタスクが実行されます。  
  
-   すべての実際の引数 \(呼び出し元で指定されている\) が評価されます。  これらの引数が評価される順序は決まっていませんが、すべての引数が評価され、関数に入る前にすべての副作用が完了します。  
  
-   それぞれの仮引数は、式リストの対応する実引数で初期化されます   \(仮引数は、関数ヘッダーで宣言され、関数の本体で使用される引数です\)。 変換は、初期化の場合と同じように行われます。標準変換とユーザー定義変換は、実引数を正しい型に変換する際に行われます。  実行された初期化を次のコードによって概念的に説明します。  
  
    ```  
    void Func( int i ); // Function prototype  
    ...  
    Func( 7 );          // Execute function call  
    ```  
  
     呼び出しの前の概念的な初期化は次のとおりです。  
  
    ```  
    int Temp_i = 7;  
    Func( Temp_i );  
    ```  
  
     かっこ構文ではなく、等号構文を使用しているように初期化が実行されることに注意してください。  `i` のコピーは、関数に値を渡す前に作成されます   \(詳細については、「[初期化子](../cpp/initializers.md)」と「[変換](../cpp/user-defined-type-conversions-cpp.md)」、「[特殊なメンバー関数を使用した初期化](http://msdn.microsoft.com/ja-jp/82223d73-64cb-4923-b678-78f9568ff3ca)」、および「[明示的な初期化](http://msdn.microsoft.com/ja-jp/c89724f8-ddd3-4d77-b86d-77fcd8bd8595)」を参照\)。  
  
     したがって、関数プロトタイプ \(宣言\) が型 **long** の引数を呼び出す場合、および呼び出し元のプログラムが型 `int` の実引数を提供する場合、実引数は、型 **long** への標準の型変換を使用して昇格されます \(「[標準変換](../cpp/standard-conversions.md)」を参照\)。  
  
     仮引数の型への標準変換またはユーザー定義変換がない実際の引数を指定するとエラーになります。  
  
     クラス型の実引数では、仮引数はクラスのコンストラクターを呼び出すことによって初期化されます   \(これらの特殊クラス メンバー関数に関する詳細については、「[コンストラクター](../cpp/constructors-cpp.md)」を参照\)。  
  
-   関数呼び出しが実行されます。  
  
 次のプログラムは関数呼び出しを示します。  
  
```  
// expre_Formal_and_Actual_Arguments.cpp  
void func( long param1, double param2 );  
  
int main()  
{  
    long i = 1;  
    double j = 2;  
  
    // Call func with actual arguments i and j.  
    func( i, j );  
}  
  
// Define func with formal parameters param1 and param2.  
void func( long param1, double param2 )  
{  
}  
```  
  
 `func` が main から呼び出されるとき、仮引数 `param1` は `i` の値で初期化され \(`i` は正しい型に対応するように標準の変換を使用して **long** 型に変換されます\)、仮引数 `param2` は `j` の値で初期化されます \(`j` は標準の変換を使用して **double** 型に変換されます\)。  
  
## 引数の型の処理  
 const 型として宣言された仮引数は、関数の本体内で変更できません。  関数が変更できるのは **const** 型以外の引数です。  ただし、実際の引数が **const** 型以外のオブジェクトへの参照でない限り、変更は関数に対してローカルであるため、実際の引数の値に影響しません。  
  
 次の関数はこれらの概念を示しています。  
  
```  
// expre_Treatment_of_Argument_Types.cpp  
int func1( const int i, int j, char *c ) {  
   i = 7;   // C3892 i is const.  
   j = i;   // value of j is lost at return  
   *c = 'a' + j;   // changes value of c in calling function  
   return i;  
}  
  
double& func2( double& d, const char *c ) {  
   d = 14.387;   // changes value of d in calling function.  
   *c = 'a';   // C3892 c is a pointer to a const object.  
    return d;  
}  
```  
  
## 省略記号と既定の引数  
 関数が関数定義で指定されているよりも少ない数の引数を受け取るには、省略記号 \(`...`\) を使用するか、既定の引数を使用します。  
  
 省略記号は、引数が必要だが、宣言で数と型を指定しないことを示します。  この方法は、C\+\+ の利点の 1 つであるタイプ セーフが活用できないため、C\+\+ のプログラミングとしてお勧めできません。  省略記号を使用して宣言された関数と、正式な実引数の型が指定された関数とでは適用される変換方式が異なります。  
  
-   実引数が **float** 型の場合、関数呼び出しの前に、引数が **double** 型に昇格します。  
  
-   符号付きまたは符号なしの `char`、**short**、列挙型、またはビット フィールドは、整数の上位変換を使用して、符号付きまたは符号なしの `int` に変換されます。  
  
-   クラス型のすべての引数は、データ構造体として値渡しされます。またクラスのコピー コンストラクター \(存在する場合\) を起動するのではなく、バイナリのコピーによってコピーが作成されます。  
  
 省略記号を使用する場合、省略記号は引数リストの最後に宣言する必要があります。  可変個の引数を渡す方法の詳細については、「ランタイム ライブラリ リファレンス[](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md "va_arg, va_copy, va_end, va_start")」の *va\_arg、va\_start、および va\_list* の説明を参照してください。  
  
 CLR プログラミングの既定の引数については、「[Variable Argument Lists \(...\) \(C\+\+\/CLI\)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)」を参照してください。  
  
 既定の引数では、関数呼び出しで引数を指定しない場合に、自動的に使用される引数の値を指定できます。  次のコード片では、既定の引数がどのように機能するかを示します。  既定の引数を指定する際の制限の詳細については、「[Default Arguments \(既定の引数\)](../Topic/Default%20Arguments.md)」を参照してください。  
  
```  
// expre_Ellipses_and_Default_Arguments.cpp  
// compile with: /EHsc  
#include <iostream>  
  
// Declare the function print that prints a string,  
// then a terminator.  
void print( const char *string,  
            const char *terminator = "\n" );  
  
int main()  
{  
    print( "hello," );  
    print( "world!" );  
  
    print( "good morning", ", " );  
    print( "sunshine." );  
}  
  
using namespace std;  
// Define print.  
void print( const char *string, const char *terminator )  
{  
    if( string != NULL )  
        cout << string;  
  
    if( terminator != NULL )  
        cout << terminator;  
}  
```  
  
 上のプログラムでは 2 個の引数を受け取る関数、`print` を宣言します。  ただし、2 番目の引数 `terminator` には既定値 `"\n"` が指定されます。  **main** では、`print` を最初の 2 回呼び出すと、既定の 2 番目の引数によって、改行して印刷文字列が出力されます。  3 番目の呼び出しでは、2 番目の引数の明示的な値が指定されます。  このプログラムによる出力は次のとおりです。  
  
```  
hello,  
world!  
good morning, sunshine.  
```  
  
## 参照  
 [式の型](../cpp/types-of-expressions.md)