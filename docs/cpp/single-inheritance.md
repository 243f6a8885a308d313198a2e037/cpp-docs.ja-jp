---
title: "単一継承 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "single inheritance_cpp"
  - "single inheritance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "基本クラス, 間接"
  - "派生クラス, 単一基本クラス"
  - "継承, single"
  - "演算子 [C++], スコープ解決"
  - "スコープ解決演算子"
  - "スコープ, スコープ解決演算子"
  - "単一継承"
ms.assetid: 1cb946ed-8b1b-4cf1-bde0-d9cecbfdc622
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# 単一継承
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

継承の一般的な形態である "単一継承" では、クラスの持つ基底クラスは 1 つだけです。  次の図に示す関係を考えます。  
  
 ![基本 Single&#95;Inheritance グラフ](../cpp/media/vc38xj1.png "vc38XJ1")  
単純な単一継承のグラフ  
  
 図における一般から特殊への流れに注意してください。  ほとんどのクラス階層のデザインにあるもう 1 つの一般的な属性は、派生クラスが基底クラスと "kind of" \(種類\) 関係を持つことです。  図では、`Book` は `PrintedDocument` の 1 種であり、`PaperbackBook` は `book` の 1 種です。  
  
 図でもう 1 つ注意する必要があるのは、`Book` が派生クラス \(`PrintedDocument` から派生\) であると同時に基底クラス \(`PaperbackBook` は `Book` から派生\) でもあるという点です。  このようなクラス階層の骨格となる宣言を次の例に示します。  
  
```  
// deriv_SingleInheritance.cpp  
// compile with: /LD  
class PrintedDocument {};  
  
// Book is derived from PrintedDocument.  
class Book : public PrintedDocument {};  
  
// PaperbackBook is derived from Book.  
class PaperbackBook : public Book {};  
```  
  
 `PrintedDocument` は `Book` の "直接基底" クラスと見なされます。これは `PaperbackBook` の "間接基底" クラスです。  違いは、直接基底クラスがクラス宣言の基底クラスのリストに記述され、間接基底クラスはそうでないことです。  
  
 各クラスが派生される基底クラスは、派生クラスを宣言する前に宣言されています。  基底クラスについて前方参照の宣言を指定するだけでは十分ではありません。完全な宣言である必要があります。  
  
 前の例では、アクセス指定子 **public** が使用されています。  public、protected、および private の継承の意味は、「[メンバー アクセス コントロール](../cpp/member-access-control-cpp.md)」で説明します。  
  
 クラスは、次の図に示すように、多くの特定のクラスの基底クラスとして機能します。  
  
 ![有向非循環グラフ](../Image/vc38XJ2.gif "vc38XJ2")  
有向非循環グラフの例  
  
 "有向非循環グラフ" \("DAG"\) と呼ばれる上記の図では、一部のクラスが複数の派生クラスの基底クラスになっています。  ただし、その逆は正しくありません。どの派生クラスにも直接基底クラスは 1 つしかありません。  図のグラフは、"単一継承" 構造を示しています。  
  
> [!NOTE]
>  有向非循環グラフは、単一継承に特有のものではありません。  多重継承グラフを記述するためにも使用されます。  このトピックは「[複数継承](http://msdn.microsoft.com/ja-jp/3b74185e-2beb-4e29-8684-441e51d2a2ca)」で取り上げます。  
  
 継承の場合、派生クラスは、基底クラスのメンバーと、追加した新しいメンバーを含みます。  その結果、派生クラスは基底クラスのメンバーを参照できます \(それらのメンバーが派生クラスで再定義されていない限り\)。  直接または間接基底クラスのメンバーが派生クラスで再定義された場合は、スコープ解決演算子 \(`::`\) を使用してそれらのメンバーを参照できます。  次の例について考えます。  
  
```  
// deriv_SingleInheritance2.cpp  
// compile with: /EHsc /c  
#include <iostream>  
using namespace std;  
class Document {  
public:  
   char *Name;   // Document name.  
   void PrintNameOf();   // Print name.  
};  
  
// Implementation of PrintNameOf function from class Document.  
void Document::PrintNameOf() {  
   cout << Name << endl;  
}  
  
class Book : public Document {  
public:  
   Book( char *name, long pagecount );  
private:  
   long  PageCount;  
};  
  
// Constructor from class Book.  
Book::Book( char *name, long pagecount ) {  
   Name = new char[ strlen( name ) + 1 ];  
   strcpy_s( Name, strlen(Name), name );  
   PageCount = pagecount;  
};  
```  
  
 `Book` のコンストラクター \(`Book::Book`\) はデータ メンバー `Name` にアクセスできることに注意してください。  プログラムでは、`Book` 型のオブジェクトは次のように作成して使用できます。  
  
```  
//  Create a new object of type Book. This invokes the  
//   constructor Book::Book.  
Book LibraryBook( "Programming Windows, 2nd Ed", 944 );  
  
...  
  
//  Use PrintNameOf function inherited from class Document.  
LibraryBook.PrintNameOf();  
```  
  
 前の例で示したように、クラス メンバーおよび継承されたデータと関数は同じように使用されます。  `Book` クラスの実装で `PrintNameOf` 関数の再実装が必要である場合、`Document` クラスに属する関数はスコープ解決演算子 \(`::`\) を使用することによってのみ呼び出すことができます。  
  
```  
// deriv_SingleInheritance3.cpp  
// compile with: /EHsc /LD  
#include <iostream>  
using namespace std;  
  
class Document {  
public:  
   char *Name;          // Document name.  
   void  PrintNameOf() {}  // Print name.  
};  
  
class Book : public Document {  
   Book( char *name, long pagecount );  
   void PrintNameOf();  
   long  PageCount;  
};  
  
void Book::PrintNameOf() {  
   cout << "Name of book: ";  
   Document::PrintNameOf();  
}  
```  
  
 アクセス可能であいまいでない基底クラスが存在している場合、派生クラスへのポインターと参照は、その基底クラスへのポインターと参照に暗黙的に変換できます。  次のコードは、ポインターを使用して、この概念を示しています \(同じ原則が参照にも適用されます\)。  
  
```  
// deriv_SingleInheritance4.cpp  
// compile with: /W3  
struct Document {  
   char *Name;  
   void PrintNameOf() {}  
};  
  
class PaperbackBook : public Document {};  
  
int main() {  
   Document * DocLib[10];   // Library of ten documents.  
   for (int i = 0 ; i < 10 ; i++)  
      DocLib[i] = new Document;  
}  
```  
  
 前の例では、異なる型が作成されます。  ただし、これらの型はすべて `Document` クラスから派生しているため、`Document *` への暗黙の型変換が実行されます。  その結果、`DocLib` は、異なる種類のオブジェクトを含む "異種混在リスト" \(すべてのオブジェクトが同じ型ではないリスト\) です。  
  
 `Document` クラスには `PrintNameOf` 関数があるため、ライブラリの各ブックの名前を出力できますが、ドキュメントの型に固有の情報の一部 \(`Book` のページ番号、`HelpFile` のバイト数など\) が省略される可能性があります。  
  
> [!NOTE]
>  基底クラスで `PrintNameOf` のような関数の実装を強制するのは、多くの場合、最適なデザインではありません。  「[仮想関数](../cpp/virtual-functions.md)」でその他のデザイン方法が説明されています。  
  
## 参照  
 [派生クラスの概要](../misc/overview-of-derived-classes.md)   
 [\(NOTINBUILD\) Multiple Inheritance](http://msdn.microsoft.com/ja-jp/3b74185e-2beb-4e29-8684-441e51d2a2ca)