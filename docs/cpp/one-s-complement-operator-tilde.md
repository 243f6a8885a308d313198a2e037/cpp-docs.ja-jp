---
title: '1 つ&#39;s 補数演算子: ~ |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- "~"
dev_langs:
- C++
helpviewer_keywords:
- tilde (~) one's complement operator
- one's complement operator
- bitwise-complement operator
- compl operator
- ~ operator [C++], syntax
ms.assetid: 4bf81967-34f7-4b4b-aade-fd03d5da0174
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 79d34a4057ccbe5c10a6d22a14eed4317e62c464
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39409157"
---
# <a name="one39s-complement-operator-"></a>1 つ&#39;s 補数演算子: ~
## <a name="syntax"></a>構文  
  
```  
~ cast-expression  
```  
  
## <a name="remarks"></a>Remarks  
 1 の補数演算子 (`~`) は、"ビット補数" 演算子とも呼ばれ、オペランドのビットごとの 1 の補数を生成します。 つまり、オペランドの各ビットが 1 である場合の結果は、0 になります。 逆に、オペランドの各ビットが 0 である場合の結果は、1 になります。 1 の補数演算子のオペランドは、整数型である必要があります。  
  
## <a name="operator-keyword-for-"></a>~ の演算子キーワード  
 **Compl**演算子と等価のテキストは、`~`します。 アクセスする 2 つの方法がある、 **compl**プログラムで演算子: ヘッダー ファイルをインクルード`iso646.h`、使用してコンパイル[/Za](../build/reference/za-ze-disable-language-extensions.md)します。  
  
## <a name="example"></a>例  
  
```cpp 
// expre_One_Complement_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main () {  
   unsigned short y = 0xFFFF;  
   cout << hex << y << endl;  
   y = ~y;   // Take one's complement  
   cout << hex << y << endl;  
}  
```  
  
 この例では、`y` に割り当てられた新しい値は、符号なしの値 0xFFFF の 1 の補数、つまり 0x0000 です。  
  
 整数の上位変換は、整数オペランドに対して実行され、結果の型は、そのオペランドが昇格される型になります。 参照してください[標準変換](standard-conversions.md)昇格を行う方法の詳細についてはします。  
  
## <a name="see-also"></a>関連項目  
 [単項演算子を含む式](../cpp/expressions-with-unary-operators.md)   
 [C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [単項算術演算子](../c-language/unary-arithmetic-operators.md)