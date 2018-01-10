---
title: "宣言の概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: declarators, about declarators
ms.assetid: 0f2e2312-80bd-4154-8345-718bd9ed2173
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 18a3f12ac87f0165c74aaa487913f679f1a9941e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="overview-of-declarators"></a>宣言の概要
宣言子は、オブジェクトまたは関数の名前を指定する宣言の構成要素です。 また、宣言子は、名前付きオブジェクトがオブジェクト、ポインター、参照、または配列であるかどうかも指定します。  宣言子は基本型を指定しませんが、ポインター、参照、配列などの派生型を指定するために、基本型の型情報を変更します。  関数に適用されると、宣言子は型指定子と組み合わせて、関数の戻り値の型がオブジェクト、ポインター、または参照であるかを完全に指定します  (指定子は、後ほど[宣言と定義](declarations-and-definitions-cpp.md)型やストレージ クラスなどの特質します。 修飾子は、このセクションで説明されている[Microsoft 固有の修飾子](../cpp/microsoft-specific-modifiers.md)、宣言子を変更します)。次の図は、`MyFunction` の宣言全体と宣言の構成要素を示します。  
  
 ![修飾子、指定子、および宣言子](../cpp/media/vc38qy1.gif "vc38QY1")  
指定子、修飾子、および宣言子  
  
 **Microsoft 固有の仕様**  
  
 ほとんどの Microsoft 拡張キーワードは派生型を作成する修飾子として使用できます。指定子または宣言子ではありません  (を参照してください[Microsoft 固有の修飾子](../cpp/microsoft-specific-modifiers.md))。  
  
 **Microsoft 固有の仕様はここまで**  
  
 宣言子は、宣言構文では、省略可能な指定子のリストの後に記述されます。 これらの指定子は、後ほど[宣言します。](declarations-and-definitions-cpp.md) 宣言には複数の宣言子を含めることができますが、各宣言子は 1 つの名前だけを宣言します。  
  
 次の宣言例は、指定子と宣言子を組み合わせて完全な宣言を作成する方法を示します。  
  
```  
const char *pch, ch;  
```  
  
 上記の宣言では、キーワードで**const**と`char`指定子のリストを構成します。 `*pch` および `ch` という 2 つの宣言子が並べられています。  複数のエンティティを宣言する場合、宣言は、型指定子の後に宣言子のコンマ区切りリストが続き、セミコロンで終わります。  
  
 **単純なオブジェクトの宣言子**  
  
 int や double のような単純なオブジェクトの宣言子は単なる名前であり、かっこは省略可能です。  
  
 `int i; // declarator is i`  
  
 `int (i); // declarator is (i)`  
  
 **ポインター、参照および配列の宣言子**  
  
 名前の前に挿入されたポインター演算子により、オブジェクトはポインターまたは参照になります。   **\*** 演算子をポインターとして名前を宣言する、  **&** 演算子は、参照として宣言します。  
  
```  
int *i; // declarator is *i  
int **i; // declarator is **i;  
int &i = x; // declaratory is &i  
```  
  
 後ろに `const` または `volatile` を付けると、ポインターに特殊な特質が与えられます。  型指定子ではなく宣言子でこれらの指定子を使用すると、ポイントされるオブジェクトではなく、ポインターの特質が変更されます。  
  
```  
char *const cpc; // const pointer to char   
const char *pcc; // pointer to const char   
const char *const cpcc; // const pointer to const char  
```  
  
 詳細については、「 [const ポインターと volatile ポインター](../cpp/const-and-volatile-pointers.md)です。  
  
 クラスまたは構造体のメンバーへのポインターは、適切な入れ子になった名前指定子で宣言されます。  
  
```  
int X::* pIntMember;   
int ::X::* pIntMember; // the initial :: specifies X is in global scope  
char Outer::Inner::* pIntMember; // pointer to char in a nested class  
```  
  
 名前の後に省略可能な定数式を囲む角かっこがあると、オブジェクトは配列になります。  連続する角かっこは、配列への追加の次元を宣言します。  
  
```  
int i[5]; // array with five elements of type int numbered from 0 to 4  
int i[]; // array of unknown size  
char *s[4]; // array of pointers to char  
int i[2][2]; // two dimensional array  
```  
  
 **関数の宣言子**  
  
 引数リストを囲むかっこは、関数を宣言する名前の後に使用されます。  次の例は、戻り値の型が `int` の関数と、`int` 型の 3 つの引数を宣言します。  
  
```  
int f(int a, int b, int c);  
```  
  
 関数へのポインターおよび参照は、次に示すように、関数名の前にポインター演算子または参照演算子を付けることによって宣言します。  かっこ (通常は省略可能) は、ポインターを返す関数と関数へのポインターを区別するために必要です。  
  
```  
int (*pf)(int); // pointer to function returning int  
int *f(int i); // function returning pointer to int  
int (&pf)(int); // reference to function   
```  
  
 メンバー関数へのポインターは、入れ子になった名前指定子によって区別されます。  
  
```  
int (X::* pmf)(); // pointer to member function of X returning int  
int* (X::* pmf)(); // pointer to member function returning pointer to int  
```  
  
 関連項目[メンバーへのポインター](../cpp/pointers-to-members.md)です。  
  
 **関数と同じ宣言内のオブジェクト**  
  
 関数とオブジェクトは、次のように同じ宣言内で宣言できます。  
  
```  
int i, *j, f(int k);  // int, pointer to int, function returning int  
```  
  
 この構文は状況によっては誤解を招く可能性があります。  次の宣言  
  
```  
int* i, f(int k);  // pointer to int, function returning int (not int*)  
```  
  
 は、`int` ポインターと `int*` を返す関数の宣言のように見えますが、違います。  これは、* が `i` の宣言子の一部であり、`f` の宣言子の一部ではないためです。  
  
 **Typedef による宣言子構文の簡略化**  
  
 ただし、もっと適切な手法は `typedef` キーワード、または、かっこと `typedef` キーワードの組み合わせを使用することです。 関数へのポインターの配列を宣言する場合を考えます。  
  
```  
//  Function returning type int that takes one   
//   argument of type char *.  
typedef int (*PIFN)( char * );  
//  Declare an array of 7 pointers to functions   
//   returning int and taking one argument of type   
//   char *.  
PIFN pifnDispatchArray[7];  
```  
  
 `typedef` 宣言を使用しなくても同等の宣言を記述できますが、非常に複雑となるためエラーを生む危険性が利点を上回ります。  
  
```  
int ( *pifnDispatchArray[7] )( char * );  
```  
  
 Typedef の詳細については、次を参照してください。[エイリアスと typedef](aliases-and-typedefs-cpp.md)です。  
  
 単一の基本型のポインター、参照、配列は、次のように (コンマで区切って) 1 つの宣言にまとめることができます。  
  
```  
int a, *b, c[5], **d, &e=a;  
```  
  
 **複雑な宣言子構文**  
  
-   ポインター、参照、配列、および関数の宣言子を組み合わせて、関数へのポインターの配列や配列へのポインターのようなオブジェクトを指定できます。  
  
-   以下の再帰的な文法は、ポインターの宣言子の構文を完全に記述しています。  
  
-   `declarator` は次のいずれかとして定義されます。  
  
```  
1. identifier   
2. qualified-name   
3. declarator ( argument-list ) [cv-qualfiers] [exception-spec]  
4. declarator [ [ constant-expression ] ]   
  
5. pointer-operatordeclarator   
6. ( declarator )  
```  
  
-   および*ポインター演算子*の 1 つです。  
  
```  
  
      * [cv-qualifiers]  
& [cv-qualifiers]  
::nested-name-specifier * [cv-qualfiers]  
```  
  
 宣言子は宣言子を含んでもよいため、上記の規則を使用して、ポインターの配列、関数ポインターの配列を返す関数など、さらに複雑な派生型を構築することもできます。  構築の各ステップを実行するには、まず、基本データ型を表す識別子を作成し、前の式を `declarator` として上記の構文規則を適用します。  構文規則を適用する順序は、式を日本語で説明するときと同じ順序にする必要があります。  適用する場合、*ポインター演算子*する場合は、配列または次の表の最後の行と同様に、関数へのポインター、配列または関数の式の構文規則はかっこを使用します。  
  
 次の例は、「int へのポインターを 10 個含む配列へのポインター」の構造を示します。  
  
|言葉による表現|宣言子|適用される構文規則|  
|-----------------------|----------------|-------------------------|  
||`i`|1|  
|int へのポインターを|`*i`|5|  
|10 個含む配列への|`(*i)[10]`|4|  
|ポインター|`*((*i)[10])`|6、続いて 5|  
  
 複数のポインター、参照、配列、または関数の修飾子を使用するときは、宣言子がかなり複雑になる場合があります。  トピック[詳細複雑な宣言子の解釈](../c-language/interpreting-more-complex-declarators.md)より複雑な宣言子構文の解釈方法について説明します。  C++ では、任意の場所、このトピックは C と C++ の両方に該当する、* ポインター、MyClass などの修飾名を指定するためです::\*クラスのメンバーへのポインターを指定するために使用可能性があります。