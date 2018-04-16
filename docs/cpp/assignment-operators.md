---
title: "代入演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '>>='
- xor_eq
- '&='
- <<=
- -=
- and_eq
- ^=
- '|='
- /=
- '%='
- or_eq
- +=
- '*='
dev_langs:
- C++
helpviewer_keywords:
- or_eq operator
- '&= operator'
- operators [C++], assignment
- assignment operators [C++], C++
- xor_eq operator
- += operator
- and_eq operator
- '>>= operator'
- '|= operator'
- operator>>=
- '*= operator'
- '%= operator'
- ^= operator
- operator >>=
- = operator
- assignment operators [C++]
- -= operator
- /= operator
- <<= operator
ms.assetid: b028cf35-2ff1-4f14-9027-fd53ebec8aa0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c84244a619873dcd61b52dee317a751ff28ec3ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="assignment-operators"></a>代入演算子
## <a name="syntax"></a>構文  
  
```  
  
      expression assignment-operator expression   
assignment-operator : one of  
   =   *=   /=   %=   +=   -=   <<=   >>=   &=   ^=   |=  
```  
  
## <a name="remarks"></a>コメント  
 代入演算子は、左側のオペランドによって指定されたオブジェクトに値を格納します。 代入演算には、2 種類あります。単純代入では、2 番目のオペランドの値が 1 番目のオペランドで指定されたオブジェクトに格納されます。複合代入では、結果を格納する前に、算術、シフト、またはビットごとの演算が行われます。 次の表の代入演算子は、= 演算子を除いて、すべてが複合代入演算子です。  
  
### <a name="assignment-operators"></a>代入演算子  
  
|演算子|説明|  
|--------------|-------------|  
|**=**|1 番目のオペランドで指定されたオブジェクトに、2 番目のオペランドの値を格納します (単純代入)。|  
|**\*=**|1 番目のオペランドの値に 2 番目のオペランドの値を乗算します。結果を 1 番目のオペランドで指定されたオブジェクトに格納します。|  
|`/=`|1 番目のオペランドの値を 2 番目のオペランドの値で除算します。結果を 1 番目のオペランドで指定されたオブジェクトに格納します。|  
|`%=`|2 番目のオペランドの値による 1 番目のオペランドの剰余を得ます。結果を 1 番目のオペランドで指定されたオブジェクトに格納します。|  
|`+=`|2 番目のオペランドの値を 1 番目のオペランドの値に加算します。結果を 1 番目のオペランドで指定されたオブジェクトに格納します。|  
|**-=**|1 番目のオペランドの値から 2 番目のオペランドの値を減算します。結果を 1 番目のオペランドで指定されたオブジェクトに格納します。|  
|**<\<=**|1 番目のオペランドの値を 2 番目のオペランドの値で指定されたビット数の分だけ左にシフトします。結果を 1 番目のオペランドで指定されたオブジェクトに格納します。|  
|**>>=**|1 番目のオペランドの値を 2 番目のオペランドの値で指定されたビット数の分だけ右にシフトします。結果を 1 番目のオペランドで指定されたオブジェクトに格納します。|  
|**&=**|1 番目と 2 番目のオペランドのビットごとの AND を取得します。結果を 1 番目のオペランドで指定されたオブジェクトに格納します。|  
|`^=`|1 番目と 2 番目のオペランドのビットごとの排他的 OR を取得します。結果を 1 番目のオペランドで指定されたオブジェクトに格納します。|  
|`&#124;=`|1 番目と 2 番目のオペランドのビットごとの包括的 OR を取得します。結果を 1 番目のオペランドで指定されたオブジェクトに格納します。|  
  
 **演算子のキーワード**  
  
 複合代入演算子の 3 つには、相当するテキスト表記があります。 それらは次のとおりです。  
  
|演算子|同等の表記|  
|--------------|----------------|  
|**&=**|`and_eq`|  
|`&#124;=`|`or_eq`|  
|`^=`|`xor_eq`|  
  
 プログラムでこれらの演算子キーワードにアクセスする 2 つの方法があります: ヘッダー ファイルをインクルード`iso646.h`、コンパイル時に、または、 [/Za](../build/reference/za-ze-disable-language-extensions.md) (言語の拡張機能を無効にする) コンパイラ オプション。  
  
## <a name="example"></a>例  
  
```  
// expre_Assignment_Operators.cpp  
// compile with: /EHsc  
// Demonstrate assignment operators  
#include <iostream>  
using namespace std;  
int main() {  
   int a = 3, b = 6, c = 10, d = 0xAAAA, e = 0x5555;  
  
   a += b;      // a is 9  
   b %= a;      // b is 6  
   c >>= 1;      // c is 5  
   d |= e;      // Bitwise--d is 0xFFFF   
  
   cout  << "a = 3, b = 6, c = 10, d = 0xAAAA, e = 0x5555" << endl  
         << "a += b yields " << a << endl  
         << "b %= a yields " << b << endl  
         << "c >>= 1 yields " << c << endl  
         << "d |= e yields " << hex << d << endl;  
}  
```  
  
## <a name="simple-assignment"></a>単純代入  
 簡単な代入演算子 (=) では、第 1 のオペランドによって指定されたオブジェクトに、第 2 のオペランドの値が保存されます。 両方のオブジェクトが数値型である場合、値を保存する前に、右側のオペランドが左側の型に変換されます。  
  
 const 型および volatile 型のオブジェクトは、単純な volatile 型の左辺値、または const、volatile のいずれでもない型の左辺値に代入できます。  
  
 クラス型 (struct 型、union 型、および class 型) のオブジェクトへの代入は、operator= という名前の関数によって行われます。 この演算子関数の既定の動作は、ビットごとのコピーです。ただしこの動作は、オーバーロードした演算子により変更できます  (を参照してください[オーバー ロードされた演算子](../cpp/operator-overloading.md)詳細についてはします)。  
  
 特定の基底クラスからの任意の明確な派生クラスのオブジェクトは、その基底クラスのオブジェクトに代入できます。 派生クラスから基底クラスへの暗黙の変換は存在しますが、基底クラスから派生クラスへの暗黙の変換は存在しないため、逆は当てはまりません。 例:  
  
```  
// expre_SimpleAssignment.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
class ABase  
{  
public:  
    ABase() { cout << "constructing ABase\n"; }  
};  
  
class ADerived : public ABase  
{  
public:  
    ADerived() { cout << "constructing ADerived\n"; }  
};  
  
int main()  
{  
    ABase aBase;  
    ADerived aDerived;  
  
    aBase = aDerived; // OK  
    aDerived = aBase; // C2679  
}  
```  
  
 参照型への代入は、参照先のオブジェクトに対する代入であるかのように動作します。  
  
 クラス型オブジェクトでは、代入は初期化とは異なります。 代入と初期化がどのように異なるかを理解するために、次のコードを考えます  
  
```  
UserType1 A;  
UserType2 B = A;  
```  
  
 前のコードは初期化子を示すもので、型 `UserType2` の引数をとる `UserType1` のコンストラクターを呼び出します。 次のコードでは  
  
```  
UserType1 A;  
UserType2 B;  
  
B = A;  
```  
  
 代入ステートメント  
  
```  
B = A;   
```  
  
 には、次のいずれかの影響が考えられます。  
  
-   `UserType2` に対して operator= 関数を呼び出します。operator= には、`UserType1` 引数を提供します。  
  
-   明示的な変換関数 `UserType1::operator UserType2` を呼び出します (そのような関数が存在する場合)。  
  
-   `UserType2::UserType2` 引数を取り、結果をコピーする `UserType1` コンストラクターを呼び出します (そのようなコンストラクターが存在する場合)。  
  
## <a name="compound-assignment"></a>複合代入。  
 複合代入演算子での表に示す[代入演算子](../cpp/assignment-operators.md)、フォームで指定された*e1* `op` =  *e2*ここで、 *e1*は const の種類の変更可能な左辺値および*e2*は、次のいずれか。  
  
-   数値型  
  
-   ポインターで場合`op`が + または -  
  
 *E1* `op` =  *e2*フォームと同様に動作*e1* *= e1* `op` *e2*が*e1*は 1 回だけ評価されます。  
  
 列挙型への複合代入によってエラー メッセージが生成されます。 左のオペランドがポインター型である場合、右のオペランドはポインター型であるか、0 に評価される定数式でなければなりません。 左のオペランドが整数型である場合、右のオペランドをポインター型にすることはできません。  
  
## <a name="result-of-assignment-operators"></a>代入演算子の結果  
 代入演算子は、代入後に、左のオペランドで指定されているオブジェクトの値を返します。 結果の型は左側のオペランドの型です。 代入式の結果は常に左辺値です。 これらの演算子の結合規則は、右から左方向です。 左のオペランドは、変更可能な左辺値である必要があります。  
  
 ANSI C では、代入式の結果は左辺値ではありません。 したがって、有効な C++ の式 `(a += b) += c` は C では無効です。  
  
## <a name="see-also"></a>参照  
 [二項演算子を含む式](../cpp/expressions-with-binary-operators.md)   
 [C++ 組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C の代入演算子](../c-language/c-assignment-operators.md)