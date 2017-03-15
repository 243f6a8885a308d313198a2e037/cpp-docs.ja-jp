---
title: "関数 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "宣言子, 関数"
  - "既定の引数"
  - "既定値, 引数"
  - "関数定義"
  - "関数定義, 関数定義の概要"
ms.assetid: 33ba01d5-75b5-48d2-8eab-5483ac7d2274
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 関数 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

関数とは、何らかの操作を実行するコードのブロックです。  関数には、呼び出し元が関数に引数を渡すのに使用する入力パラメーターを必要に応じて定義できます。  関数は、必要に応じて値を出力として返すことができます。  関数は、一般的な操作を 1 つの再利用可能なブロックでカプセル化するのに役立ちます。関数には、その動作を明確に説明する名前を付けることが理想的です。  次の関数は呼び出し元から 2 つの整数を受け取り、その合計を返します。`a` と `b` は `int` 型の*パラメーター*です。  
  
```  
int sum(int a, int b)  
{  
    return a + b;  
}  
```  
  
 関数は、プログラム内の任意の数の場所から起動する、もしくは*呼び出す*ことができます。  関数に渡される値は*引数*と呼ばれ、関数定義のパラメーターの型と互換性のある型を持つ必要があります。  
  
```  
int main()  
{  
    int i = sum(10, 32);  
    int j = sum(i, 66);  
    cout << "The value of j is" << j << endl; // 108  
}  
```  
  
 関数の長さに事実上制限はありませんが、優れた設計では、適切に定義された 1 つのタスクを実行する関数を目標にします。  複雑なアルゴリズムは、可能な場合は常に、理解しやすい簡潔な関数に分割することをお勧めします。  
  
 クラス スコープで定義されている関数はメンバー関数と呼ばれます。  C\+\+ では、他の言語とは異なり、名前空間スコープ \(暗黙的なグローバル名前空間を含む\) でも関数を定義できます。  このような関数は*フリー関数*、または*非メンバー関数*と呼ばれます。これらは標準ライブラリで広く使用します。  
  
## 関数宣言部分  
 最小限の関数*宣言*は、戻り値の型、関数名、およびパラメーター リスト \(空の場合があります\) で構成され、これにコンパイラに追加の指示を提供する省略可能なキーワードが付随します。  関数定義は、宣言と*本体*で構成されます。本体とは、中かっこで挟まれたコード全体です。  関数宣言の後にはセミコロンが続きます。1 つのプログラムの複数個所で、関数宣言がなされる場合があります。  関数宣言は、翻訳単位ごとに関数に対する呼び出しの前に記述される必要があります。  関数定義は、単一定義規則 \(ODR\) に従い、プログラム内で 1 回だけ記述する必要があります。  
  
 関数宣言に必要な部分は次のとおりです。  
  
1.  戻り値の型とは関数が返す値の型を指定するもので、値が返されない場合は `void` です。  C\+\+11 では、"auto" が有効な戻り値の型となっており、この型を指定するとコンパイラは return ステートメントから型を推論します。  C\+\+14 では、"decltype\(auto\)" も使用できます。  詳細については、以下の「戻り値の型の型推論」を参照してください。  
  
2.  関数名は文字かアンダースコアで始まる必要があり、スペースを含めることはできません。  一般に、標準ライブラリ関数名で先頭にアンダースコアがあるものは、プライベート メンバー関数であるか、コードでの使用が意図されていない非メンバー関数であることを意味しています。  
  
3.  パラメーター リストとは、中かっこに挟まれ、コンマで区切られた 0 個以上のパラメーターのセットです。パラメーターで、型を指定し、関数本体内で値にアクセスする際に使用するローカル名も必要に応じて指定できます。  
  
 関数宣言の省略可能な部分は次のとおりです。  
  
1.  `constexpr`。関数の戻り値がコンパイル時に計算できる定数値であることを示します。  
  
    ```  
  
                  constexpr float exp(float x, int n)  
    {  
        return n == 0 ? 1 :  
            n % 2 == 0 ? exp(x * x, n / 2) :  
            exp(x * x, (n - 1) / 2) * x;  
    };  
    ```  
  
2.  その `linkage` 指定。`extern`、または `static` です。  
  
    ```  
    Declare printf with C linkage.  
    extern "C" int printf( const char *fmt, ... );  
  
    ```  
  
     詳細については、「[プログラムとリンケージ](../cpp/program-and-linkage-cpp.md)」を参照してください。  
  
3.  `inline`。関数の呼び出しをそれぞれの関数コード自体で置き換えるよう、コンパイラに対して指示します。  パフォーマンスが重要なコード セクションで関数が迅速に実行され、繰り返し呼び出されるシナリオでは、インライン展開を使用すると、パフォーマンスが向上します。  
  
    ```  
    inline double Account::GetBalance()  
    {  
        return balance;  
    }  
    ```  
  
     詳細については、「[インライン関数](../Topic/Inline%20Functions%20\(C++\).md)」を参照してください。  
  
4.  `noexcept`。関数が例外をスローできるかどうかを指定します。  次の例では、`is_pod` 式が `true` と評価されない場合、関数は例外をスローしません。  
  
    ```  
    #include <type_traits>  
  
    template <typename T>  
    T copy_object(T& obj) noexcept(std::is_pod<T>) {...}  
    ```  
  
     詳細については、「[noexcept](../Topic/noexcept%20\(C++\).md)」を参照してください。  
  
5.  \(メンバー関数のみ\) cv 修飾子。関数が `const` か `volatile` かを指定します。  
  
6.  \(メンバー関数のみ\) `virtual`、`override`、または `final`。  `virtual` を指定すると、関数が派生クラスでオーバーライドできるようになります。  `override` は、派生クラス内の関数が仮想関数をオーバーライドすることを意味します。  `final` は、いかなる派生クラス内でも関数がオーバーライドされないことを意味します。  詳細については、「[仮想関数](../cpp/virtual-functions.md)」を参照してください。  
  
7.  \(メンバー関数のみ\) メンバー関数に適用される `static` は、関数がクラスのどのオブジェクト インスタンスにも関連付けられていないことを意味します。  
  
8.  \(非静的メンバー関数のみ\) ref 修飾子。暗黙的オブジェクト パラメーター \(\*this\) が右辺値参照と  左辺値参照の対になっている場合、関数のどのオーバーロードを選択すべきかをコンパイラに指定します。  
  
 次の図では、関数定義の一部を示しています。  網かけされた部分は関数本体です。  
  
 ![関数定義部分](../cpp/media/vc38ru1.png "vc38RU1")  
関数定義部分  
  
## 関数定義  
 本体内で宣言された変数は、ローカル変数またはローカルと呼ばれます。  これらは関数の終了時にスコープ外に出るため、関数がローカルに参照を返すことはありません。  
  
## 関数テンプレート  
 関数テンプレートはクラス テンプレートに似ており、テンプレート引数に基づく具体的な関数を生成します。  多くの場合、テンプレートは型の引数を推測できるので、型の引数を明示的に指定する必要はありません。  
  
```  
template<typename Lhs, typename Rhs>  
auto Add2(const Lhs& lhs, const Rhs& rhs)  
{  
    return lhs + rhs;  
}  
  
auto a = Add2(3.13, 2.895); // a is a double  
auto b = Add2(string{ "Hello" }, string{ " World" }); // b is a std::string  
```  
  
 詳細については、「[関数テンプレート](../cpp/function-templates.md)」を参照してください。  
  
## 関数のパラメーターと引数  
 関数にはコンマで区切られた 0 個以上の型のパラメーター リストがあり、それぞれに関数本体内でアクセスする際に使用する名前があります。  関数テンプレートで、追加の型や値のパラメーターを指定できます。  呼び出し元は引数を渡します。引数は、パラメーター リストと互換性のある型を持つ具体的な値です。  
  
 既定では、引数は関数に値渡しで渡されます。このことは、関数が渡されるオブジェクトのコピーを受け取ることを意味します。  大きなオブジェクトの場合、コピーの作成は負荷が高く、必ずしも必要ではありません。  引数を参照渡し \(具体的には左辺値参照\) で渡すようにするには、パラメーターに参照修飾子を追加します。  
  
```  
void DoSomething(std::string& input){...}  
```  
  
 関数が参照によって渡される引数を変更すると、ローカル コピーではなく元のオブジェクトが変更されます。  関数がこのような引数を変更しないようにするには、パラメーターを const& として修飾します。  
  
```  
void DoSomething(const std::string& input){...}  
```  
  
 **C\+\+ 11:**  右辺値参照または左辺値参照によって渡される引数を明示的に処理するには、パラメーターで二重アンパサンドを使用して、汎用参照を指定します。  
  
```  
void DoSomething(const std::string&& input){...}  
```  
  
 パラメーターの宣言リストの 1 つのキーワード `void` で宣言された関数は、キーワード `void` が引数の宣言リストの最初で唯一のメンバーである限り、引数を受け取りません。  リスト内の他の場所で、`void` 型の引数がエラーを生成します。  例:  
  
```  
  
// OK same as GetTickCount()  
long GetTickCount( void );   
```  
  
 ここに記載されている以外の `void` 引数の指定は無効ですが、`void` 型から派生した型 \(`void` へのポインターや `void` の配列など\) は引数宣言リスト内に指定できることに注意してください。  
  
### 既定の引数  
 関数のシグネチャの最後のパラメーターに既定の引数を割り当てることができます。このことは、他の値を指定する必要がない場合は、関数を呼び出すときに呼び出し元が引数を省略できることを意味します。  
  
```  
int DoSomething(int num,   
    string str,   
    Allocator& alloc = defaultAllocator)  
{ ... }  
  
// OK both parameters are at end  
int DoSomethingElse(int num,   
    string str = string{ "Working" },   
    Allocator& alloc = defaultAllocator)  
{ ... }  
  
// C2548: 'DoMore': missing default parameter for parameter 2  
int DoMore(int num = 5, // Not a trailing parameter!  
    string str,  
    Allocator& = defaultAllocator)  
{...}  
```  
  
 詳細については、「[既定の引数](../Topic/Default%20Arguments.md)」および「[クラス テンプレートの既定の引数](../Topic/Default%20Arguments%20for%20Class%20Templates.md)」を参照してください。  
  
## 関数の戻り値の型  
 関数が別の関数、あるいは組み込み配列を返さない場合があります。ただし、そのような関数であってもこれらの型へのポインター、あるいは*ラムダ*を返すことができ、ラムダによって関数オブジェクトが生成されます。  このような場合を除き、関数はスコープ内にある任意の型の値を返すことができます。"値なし" を返す場合、戻り値の型は `void` です。  
  
### 後続の戻り値の型  
 "通常" の戻り値の型は、関数のシグネチャの左側にあります。  *後続の戻り値の型*は、シグネチャの一番右端にあり、その前に "\-\>" 演算子があります。  後続の戻り値の型は、関数テンプレートにおいて、戻り値の種類がテンプレート パラメーターに依存する場合、特に便利です。  
  
```  
template<typename Lhs, typename Rhs>  
auto Add(const Lhs& lhs, const Rhs& rhs) -> decltype(lhs + rhs)  
{  
    return lhs + rhs;   
}  
```  
  
 後続の戻り値の型と組み合わせて `auto` が使用される場合、decltype 式によって生成される値のプレース ホルダーとしてのみ機能します。それ自体は型の推論を実行しません。  
  
###  <a name="type_deduction"></a> 戻り値の型の推論 \(C\+\+14\)  
 C\+\+14 では、`auto` を使用して、後続の戻り値の型を指定しない場合でも、関数本体からの戻り値の型を推論するようにコンパイラに対して指示できます。  `auto` の推測結果は常に値渡しの戻り値になることに注意してください。  `auto&&` を使用すると、参照を推測するようにコンパイラに指示できます。  
  
 この例で、`auto` は lhs と rhs の合計の非定数値のコピーとして推測されます。  
  
```  
template<typename Lhs, typename Rhs>  
auto Add2(const Lhs& lhs, const Rhs& rhs)  
{  
    return lhs + rhs; //returns a non-const object by value  
}  
```  
  
 `auto` も推測した型の const 性は保持されないことに注意してください。  引数の const 性または ref 性を維持する必要がある戻り値を返す転送関数の場合、`decltype` 型の推論規則を使用してすべての型情報を保持する `decltype(auto)` キーワードを使用できます。  `decltype(auto)` は、左側にある通常の戻り値としても、後続の戻り値としても使用できます。  
  
 次の例 \([N3493](http://www.open-std.org/JTC1/SC22/WG21/docs/papers/2013/n3493.html) のコードに基づく\) では、テンプレートがインスタンス化されてはじめて戻り値の型が判明する関数の引数を `decltype(auto)` を使用して完全に転送しています。  
  
```  
template<typename F, typename Tuple = tuple<T...>, int... I>  
decltype(auto) apply_(F&& f, Tuple&& args, index_sequence<I...>)   
{  
    return std::forward<F>(f)(std::get<I>(std::forward<Tuple>(args))...);  
}  
  
template<typename F, typename Tuple = tuple<T...>,  
    typename Indices = make_index_sequence<tuple_size<Tuple>::value >>  
   decltype( auto)  
    apply(F&& f, Tuple&& args)      
{  
    return apply_(std::forward<F>(f), std::forward<Tuple>(args), Indices());  
}  
}  
```  
  
## 関数のローカル変数  
 関数本体内で宣言される変数は、*ローカル変数*、または単に*ローカル*と呼ばれます。  非静的ローカルは関数本体内でのみ認識され、スタックで宣言されている場合は、関数の終了時にスコープ外に出ます。  ローカル変数を作成して値渡しで値を返す場合、通常、コンパイラで戻り値の最適化を実行し、不要なコピー操作を回避できます。  ローカル変数を参照渡しで返す場合、呼び出し元がその参照を使用するために実行する試行がローカルの破棄後に発生するため、コンパイラは警告を発行します。  
  
 ローカルな静的オブジェクトは、`atexit` によって指定された終了時に破棄されます。  プログラムの制御フローが宣言をバイパスしたために静的オブジェクトが構築されなかった場合、そのオブジェクトの破棄は試みられません。  
  
### 静的ローカル変数  
 C\+\+ では、ローカル変数を "静的" として宣言することがあります。  変数は関数本体内でのみ認識されますが、関数のすべてのインスタンスに対して変数の 1 つのコピーが存在します。  
  
## 関数ポインター  
 C\+\+ では、C 言語と同じ方法で、関数ポインターをサポートします。  ただし、通常、よりタイプ セーフな代替手段で関数オブジェクトが使用されます。  
  
 関数ポインター型を返す関数を宣言する場合は、`typedef` を使用して関数ポインター型のエイリアスを宣言することをお勧めします。  次に例を示します。  
  
```  
typedef int (*fp)(int);  
fp myFunction(char* s); // function returning function pointer  
```  
  
 このように記述していない場合でも、識別子 \(上の例では `fp`\) を関数名と引数リストで置き換えることで、関数ポインターの宣言構文から関数宣言の正しい構文を次のように導き出すことはできます。  
  
```  
int (*myFunction(char* s))(int);  
```  
  
 この宣言は、上記の typedef を使用した宣言と同等です。  
  
## 参照  
 [関数のオーバーロード](../cpp/function-overloading.md)   
 [可変個の引数リストを取る関数](../cpp/functions-with-variable-argument-lists-cpp.md)   
 [明示的に既定された関数および削除された関数](../Topic/Explicitly%20Defaulted%20and%20Deleted%20Functions.md)   
 [関数の引数依存名の参照 \(Koenig 参照\)](../Topic/Argument-Dependent%20Name%20\(Koenig\)%20Lookup%20on%20Functions.md)   
 [既定の引数](../Topic/Default%20Arguments.md)   
 [インライン関数](../Topic/Inline%20Functions%20\(C++\).md)