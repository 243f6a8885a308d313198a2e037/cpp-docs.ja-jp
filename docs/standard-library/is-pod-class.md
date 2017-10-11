---
title: "is_pod クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::is_pod
dev_langs:
- C++
helpviewer_keywords:
- is_pod class
- is_pod
ms.assetid: d73ebdee-746b-4082-9fa4-2db71432eb0e
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: efe54ef10c8ab8102e17efdbf8e38f217ec2e0df
ms.contentlocale: ja-jp
ms.lasthandoff: 10/03/2017

---
# <a name="ispod-class"></a>is_pod クラス
型が POD かどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>
struct is_pod;
```  
  
#### <a name="parameters"></a>パラメーター  
*T*  
照会する型。  
  
## <a name="remarks"></a>コメント  
型 *T* が POD (Plain Old Data) である場合、`is_pod<T>::value` は `true` です。 それ以外の場合は `false` です。  
  
演算型、列挙型、ポインター型、およびメンバーへのポインター型は、POD です。  
  
POD 型の cv-qualified バージョンは、それ自体が POD 型です。  
  
POD の配列は、それ自体が POD です。  
  
すべての非静的データ メンバーが POD である構造体または共用体は、次に該当する場合、それ自体が POD です。  
  
-   ユーザーが宣言したコンストラクターを持たない。  
  
-   非静的なプライベートまたはプロテクト データ メンバーを持たない。  
  
-   基底クラスを持たない。  
  
-   仮想関数を持たない。  
  
-   参照型の非静的データ メンバーを持たない。  
  
-   ユーザー定義のコピー代入演算子を持たない。  
  
-   ユーザー定義のデストラクターを持たない。  
  
したがって、POD 型の構造体や配列を含む POD 型の構造体や配列を再帰的に構築できます。  
  
## <a name="example"></a>例  
  
```cpp  
// std__type_traits__is_pod.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial {   
    int val;   
};   
  
struct throws {   
    throws() {}  // User-declared ctor, so not POD
  
    int val;   
};   
  
int main() {   
    std::cout << "is_pod<trivial> == " << std::boolalpha   
        << std::is_pod<trivial>::value << std::endl;   
    std::cout << "is_pod<int> == " << std::boolalpha   
        << std::is_pod<int>::value << std::endl;   
    std::cout << "is_pod<throws> == " << std::boolalpha   
        << std::is_pod<throws>::value << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
is_pod<trivial> == true  
is_pod<int> == true  
is_pod<throws> == false  
```  
  
## <a name="requirements"></a>要件  
**ヘッダー:** \<type_traits>  
  
**名前空間:** std  
  
## <a name="see-also"></a>関連項目  
[<type_traits>](../standard-library/type-traits.md)




