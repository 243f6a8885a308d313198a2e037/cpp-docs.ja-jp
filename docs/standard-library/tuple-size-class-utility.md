---
title: "tuple_size クラス &lt;utility&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tuple_size"
  - "std::tr1::tuple_size"
  - "std.tr1.tuple_size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tuple_size クラス <utility> (TR1)"
ms.assetid: 36d04207-ed87-4c11-9875-150c59833b79
caps.latest.revision: 21
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# tuple_size クラス &lt;utility&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`pair` の要素数をラップします。  
  
## 構文  
  
```  
template<class Tuple>  
struct tuple_size;  
  
template<class T1, class T2>  
struct tuple_size<pair<T1, T2>>   : integral_constant<size_t, 2>  
  
// size of const tuple  
template<class Tuple>  
struct tuple_size<const Tuple>;  
  
// size of volatile tuple  
template<class Tuple>  
struct tuple_size<volatile Tuple>;  
  
// size of const volatile tuple  
template<class Tuple>  
struct tuple_size<const volatile Tuple>;  
```  
  
#### パラメーター  
 `T1`  
 1 番目の pair 要素の型。  
  
 `T2`  
 2 番目の pair 要素の型。  
  
## 解説  
 このテンプレートは、テンプレート クラス [tuple\_size クラス](../standard-library/tuple-size-class-tuple.md) を特化したクラスです。 このテンプレートにはメンバー `value` が含まれており、このメンバーは 2 という値を持つ整数定数式です。  
  
## 使用例  
  
```  
#include <utility>   
#include <iostream>   
  
using namespace std;  
  
typedef pair<int, double> MyPair;  
  
int main()  
{  
    MyPair c0(0, 1.1);  
  
    // display contents " 0 1.1"   
    cout << " " << get<0>(c0);  
    cout << " " << get<1>(c0) << endl;  
  
    // display size " 2"   
    cout << " " << tuple_size<MyPair>::value << endl;  
  
}  
  
/*  
Output:  
0 1.1  
2  
*/  
```  
  
## 必要条件  
 **ヘッダー:** \<utility\>  
  
 **名前空間:** std  
  
## 参照  
 [\<utility\>](../standard-library/utility.md)   
 [get 関数](../Topic/get%20Function%20%3Cutility%3E.md)   
 [tuple\_element クラス](../standard-library/tuple-element-class-utility.md)