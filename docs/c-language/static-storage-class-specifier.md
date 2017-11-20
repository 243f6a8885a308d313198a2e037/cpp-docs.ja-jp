---
title: "static ストレージ クラス指定子 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- static variables, specifier
- storage classes, static
- static storage class specifiers
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0a51dfc10ac0ae05a67a280b4b76c2c92eb57a0b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="static-storage-class-specifier"></a>static ストレージ クラス指定子
**static** のストレージ クラス指定子により内部レベルで宣言された変数には、グローバル有効期間がありますが、宣言されたブロック内でのみ表示されます。 定数文字列の場合、**static** を使用すると、頻繁に呼び出される関数で頻度の高い初期化のオーバーヘッドを軽減するのに役立ちます。  
  
## <a name="remarks"></a>コメント  
明示的に**静的**変数を初期化しない場合、既定で 0 に初期化されます。 関数内で、**static** はストレージを割り当てますが、定義として動作します。 内部静的変数は、1 つの関数にのみプライベートの永続ストレージ変数を提供します。  
  
## <a name="see-also"></a>関連項目  
[C ストレージ クラス](c-storage-classes.md)  
[ストレージ クラス (C++)](../cpp/storage-classes-cpp.md)  