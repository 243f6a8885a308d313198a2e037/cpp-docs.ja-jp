---
title: "C++ ビット フィールド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- bitfields [C++]
- fields [C++], bit
- bit fields
ms.assetid: 6f4b62e3-cc1d-4e5d-bf34-05904104f71a
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 71f70995cf1a59153a380f0e22f0321fd59abee0
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="c-bit-fields"></a>C++ ビット フィールド
クラスと構造体には、整数型よりも記憶領域の占有率が少ないメンバーを含めることができます。 これらのメンバーは、ビット フィールドとして指定されます。 ビット フィールドの構文*メンバー宣言子*仕様に従います。  
  
## <a name="syntax"></a>構文  
  
```  
  
declarator  : constant-expression  
```  
  
## <a name="remarks"></a>コメント  
 `declarator` (省略可能) は、プログラム内でメンバーにアクセスするために使用される名前です。 整数型 (列挙型を含む) である必要があります。 *定数式*構造体のメンバーが占有するビット数を指定します。 匿名ビット フィールド (つまり、識別子のないビット フィールド メンバー) はパディング用に使用できます。  
  
> [!NOTE]
>  名前のない幅 0 のビット フィールドは、次のビット フィールドの割り当てが次の `type` 境界になるように強制します。`type` はメンバーの型です。  
  
 次の例では、ビット フィールドを持つ構造体を宣言します。  
  
```  
// bit_fields1.cpp  
// compile with: /LD  
struct Date {  
   unsigned short nWeekDay  : 3;    // 0..7   (3 bits)  
   unsigned short nMonthDay : 6;    // 0..31  (6 bits)  
   unsigned short nMonth    : 5;    // 0..12  (5 bits)  
   unsigned short nYear     : 8;    // 0..100 (8 bits)  
};  
```  
  
 `Date` 型のオブジェクトの概念的なメモリ レイアウトを次の図に示します。  
  
 ![Date オブジェクトのメモリ レイアウト](../cpp/media/vc38uq1.png "vc38UQ1")  
データ オブジェクトのメモリ レイアウト  
  
 なお`nYear`8 ビット長は、宣言された型の単語の境界をオーバーフローする**unsigned short**です。 新しいの先頭から開始されたため、 **unsigned short**です。 すべてのビット フィールドが基になる型の 1 つのオブジェクトに収まる必要はありません。宣言で要求されたビット数に従って、ストレージの新しい単位が割り当てられます。  
  
 **Microsoft 固有の仕様**  
  
 ビット フィールドとして宣言されたデータの順序は、上の図に示すように、下位から上位のビットへ向います。  
  
 **Microsoft 固有の仕様はここまで**  
  
 構造体の宣言に、次の例のように、名前の付いていない長さが 0 のフィールドが含まれている場合、  
  
```  
// bit_fields2.cpp  
// compile with: /LD  
struct Date {  
   unsigned nWeekDay  : 3;    // 0..7   (3 bits)  
   unsigned nMonthDay : 6;    // 0..31  (6 bits)  
   unsigned           : 0;    // Force alignment to next boundary.  
   unsigned nMonth    : 5;    // 0..12  (5 bits)  
   unsigned nYear     : 8;    // 0..100 (8 bits)  
};  
```  
  
 メモリ レイアウトは次の図のようになります。  
  
 ![0 & #45 を持つデータ オブジェクトのレイアウト; ビット フィールドの長さ](../cpp/media/vc38uq2.png "vc38UQ2")  
長さ 0 のビット フィールドを持つデータ オブジェクトのレイアウト  
  
 ビット フィールドの基になる型」の説明に従って、整数型である必要があります[基本的な型](../cpp/fundamental-types-cpp.md)です。  
  
## <a name="restrictions-on-bit-fields"></a>ビット フィールドの制約  
 次の一覧は、ビット フィールドの不適切な操作を詳述します。  
  
1.  ビット フィールドのアドレスの取得。  
  
2.  ビット フィールドでの参照の初期化。  
  
## <a name="see-also"></a>関連項目  
 [クラスと構造体](../cpp/classes-and-structs-cpp.md)
