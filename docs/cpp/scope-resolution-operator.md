---
title: "スコープ解決演算子: :: | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "::"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ":: 演算子"
  - "演算子 [C++], スコープ解決"
  - "スコープ解決演算子"
  - "スコープ, スコープ解決演算子"
ms.assetid: fd5de9d3-c716-4e12-bae9-03a16fd79a50
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# スコープ解決演算子: ::
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

スコープ解決演算子 `::` は異なるスコープで使用される識別子を特定し、あいまいさを解消するために使用されます。  スコープの詳細については、「[スコープ](../cpp/scope-visual-cpp.md)」を参照してください。  
  
## 構文  
  
```  
:: identifier class-name :: identifier namespace :: identifier enum class :: identifier enum struct :: identifier  
```  
  
## 解説  
 `identifier` は変数、関数、または列挙値になることがあります。  
  
## クラスと名前空間の使用  
 次の例は、スコープ解決演算子を名前空間およびクラスと共に使用する方法を示します。  
  
```cpp  
namespace NamespaceA{  
    int x;  
    class ClassA {  
    public:  
        int x;  
    };  
}  
  
int main() {  
  
    // A namespace name used to disambiguate  
    NamespaceA::x = 1;  
  
    // A class name used to disambiguate  
    NamespaceA::ClassA a1;  
    a1.x = 2;  
  
}  
  
```  
  
 スコープ修飾子を持たないスコープ解決演算子はグローバル名前空間を参照します。  
  
```cpp  
namespace NamespaceA{  
    int x;  
}  
  
int x;   
  
int main() {  
    int x;  
  
    // the x in main()  
    x = 0;   
    // The x in the global namespace  
    ::x = 1;   
  
    // The x in the A namespace  
    NamespaceA::x = 2;   
}  
```  
  
 スコープ解決演算子は、名前空間のメンバーの特定、または using ディレクティブでメンバーの名前空間をノミネートする名前空間の特定に使用できます。  下の例では、名前空間 `NamespaceB` で `ClassB` が宣言されていた場合でも、`NamespaceC` を使用して `ClassB` を修飾できます。これは、`NamespaceB` が using ディレクティブにより `NamespaceC` でノミネートされているからです。  
  
```cpp  
namespace NamespaceB {  
    class ClassB {  
    public:  
        int x;  
    };  
}  
  
namespace NamespaceC{  
    using namespace B;  
  
}  
int main() {  
    NamespaceB::ClassB c_b;  
    NamespaceC::ClassB c_c;  
  
    c_b.x = 3;  
    c_c.x = 4;  
}  
  
```  
  
 スコープ解決演算子のチェーンを使用できます。  次の例で、`NamespaceD::NamespaceD1` は入れ子になった名前空間 `NamespaceD1` を特定し、`NamespaceE::ClassE::ClassE1` は入れ子になったクラス `ClassE1` を特定します。  
  
```cpp  
namespace NamespaceD{  
    namespace NamespaceD1{  
        int x;  
    }  
}  
  
namespace NamespaceE{  
  
    class ClassE{  
    public:  
        class ClassE1{  
        public:  
            int x;  
        };  
    };  
}  
  
int main() {  
    NamespaceD:: NamespaceD1::x = 6;  
    NamespaceE::ClassE::ClassE1 e1;  
    e1.x = 7  ;  
}  
  
```  
  
## 静的メンバーの使用  
 スコープ解決演算子を使用してクラスの静的メンバーを呼び出すことができます。  
  
```cpp  
class ClassG {  
public:  
    static int get_x() { return x;}  
    static int x;  
};  
  
int ClassG::x = 6;  
  
int main() {  
  
    int gx1 = ClassG::x;  
    int gx2 = ClassG::get_x();   
}  
  
```  
  
## スコープを持つ列挙型の使用  
 次の例のように、スコープ解決演算子をスコープを持つ列挙型[列挙体の宣言](../cpp/enumerations-cpp.md)の値と共に使用することもできます。  
  
```cpp  
enum class EnumA{  
    First,  
    Second,  
    Third  
};  
  
int main() {  
  
    EnumA enum_value = EnumA::First;  
}  
  
```  
  
## 参照  
 [C\+\+ の演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [名前空間](../cpp/namespaces-cpp.md)   
 [名前と修飾名](../misc/names-and-qualified-names.md)