---
title: 基本クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- inheritance, multiple
- base classes [C++], virtual
- derived classes [C++], multiple bases
- multiple inheritance, base classes
- virtual base classes [C++]
- base classes [C++]
ms.assetid: 6e6d54d0-6f21-4a16-9103-22935d98f596
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f1375cee34266b8d751e9c8d88fb22ce56f6c044
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407989"
---
# <a name="base-classes"></a>基本クラス
継承プロセスは、基底クラス、および派生クラスによって追加された新しいメンバーで構成される、新しい派生クラスを作成します。 多重継承では、同じ基底クラスが複数の派生クラスの一部になる継承グラフが生成される場合があります。 次の図は、こうしたグラフを示しています。  
  
 ![基底クラスの複数のインスタンス](../cpp/media/vc38xn1.gif "vc38XN1")  
単一基底クラスの複数インスタンス  
  
 図では、`CollectibleString` と `CollectibleSortable` のコンポーネントのイメージ表現が表示されます。 ただし、基底クラス `Collectible` は、`CollectibleSortableString` パスと `CollectibleString` パスを経由した `CollectibleSortable` 内にあります。 この冗長性を取り除くために、継承されるときにこのようなクラスを仮想基底クラスとして宣言できます。  