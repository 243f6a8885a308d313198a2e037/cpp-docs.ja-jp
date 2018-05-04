---
title: 単項演算子のオーバー ロード |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- unary operators [C++], plus
- increment operators [C++], overloaded
- unary operators [C++], minus
- operators [C++], unary
- redefinable unary operators [C++]
- unary operators [C++]
- pointer dereference operator overloading
- plus operator
ms.assetid: 7683ef08-42a4-4283-928f-d3dd4f3ab4c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d7f242fac0d81c6d46c2d810bf07459fde2fb2ae
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="overloading-unary-operators"></a>単項演算子のオーバーロード
オーバーロードできる単項演算子は次のとおりです。  
  
1.  `!` ([論理 NOT](../cpp/logical-negation-operator-exclpt.md))  
  
2.  `&` ([アドレスの](../cpp/address-of-operator-amp.md))  
  
3.  `~` ([1 の補数](../cpp/one-s-complement-operator-tilde.md))  
  
4.  `*` ([ポインターが逆参照](../cpp/indirection-operator-star.md))  
  
5.  `+` ([単項プラス](../cpp/additive-operators-plus-and.md))  
  
6.  `-` ([単項マイナス符号](../cpp/additive-operators-plus-and.md))  
  
7.  `++` ([インクリメント](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))  
  
8.  `--` ([デクリメント](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))  
  
9. 変換演算子  
  
 後置インクリメントとデクリメント演算子 (`++`と**--**) で個別に扱われます[インクリメントおよびデクリメント](../cpp/increment-and-decrement-operator-overloading-cpp.md)です。  
  
 変換演算子は、別のトピックでは説明も参照してください[ユーザー定義型の変換](../cpp/user-defined-type-conversions-cpp.md)です。  
  
 次の規則は他のすべての単項演算子に適用されます。 単項演算子関数を非静的メンバーとして宣言するには、次の形式で宣言する必要があります。  
  
 `ret-type operator` `op` `()`  
  
 `ret-type` は戻り値の型であり、`op` は前の表に示している演算子の 1 つです。  
  
 単項演算子関数をグローバル関数として宣言するには、次の形式で宣言する必要があります。  
  
 `ret-type operator` `op` (`arg` )  
  
 `ret-type` と `op` はメンバー演算子関数での説明と同様です。`arg` は操作対象のクラス型の引数です。  
  
> [!NOTE]
>  単項演算子の戻り値の型に制限はありません。 たとえば、論理 NOT (`!`) が整数値を返すのは正しい使い方ですが、強制ではありません。  
  
## <a name="see-also"></a>関連項目  
 [演算子のオーバーロード](../cpp/operator-overloading.md)