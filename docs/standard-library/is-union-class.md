---
title: "is_union クラス | Microsoft Docs"
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
  - "is_union"
  - "std::tr1::is_union"
  - "std.tr1.is_union"
  - "std.is_union"
  - "std::is_union"
  - "type_traits/std::is_union"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_union クラス [TR1]"
  - "is_union"
ms.assetid: 80eda256-40b8-4db5-9ac1-d58bb8032a3e
caps.latest.revision: 19
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_union クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型が共用体であるかどうかをテストします。  
  
## 構文  
  
```  
template<class Ty>  
    struct is_union;  
```  
  
#### パラメーター  
 `Ty`  
 照会する型。  
  
## 解説  
 型 `Ty` が共用体型または共用体型の `cv-qualified` 形式である場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。  
  
## 使用例  
  
```  
// std_tr1__type_traits__is_union.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
union ints   
    {   
    int in;   
    long lo;   
    };   
  
int main()   
    {   
    std::cout << "is_union<trivial> == " << std::boolalpha   
        << std::is_union<trivial>::value << std::endl;   
    std::cout << "is_union<int> == " << std::boolalpha   
        << std::is_union<int>::value << std::endl;   
    std::cout << "is_union<ints> == " << std::boolalpha   
        << std::is_union<ints>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_union\<trivial\> \=\= false**  
**is\_union\<int\> \=\= false**  
**is\_union\<ints\> \=\= true**   
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_class クラス](../standard-library/is-class-class.md)