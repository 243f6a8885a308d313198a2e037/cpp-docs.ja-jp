---
title: "ATL のコレクションと列挙子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- enumerator interfaces
- collections, ATL classes
- enumerators, ATL classes
- collection interfaces
ms.assetid: b2d37119-3ab2-4e0a-b65b-f377f07e4098
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4738e3f5256fe654dd64541dfd021ba2b4fce090
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="atl-collections-and-enumerators"></a>ATL のコレクションと列挙子
A `collection` (生データやその他のオブジェクト) のデータ項目のグループにアクセスできるようにするインターフェイスを提供する COM オブジェクトです。 一定の基準に従ってと呼ばれますが、オブジェクトのグループへのアクセスを提供するインターフェイス、*コレクション インターフェイス*です。  
  
 コレクション インターフェイスを提供する必要がありますには、少なくとも、**カウント**プロパティをコレクション内の項目数を返す、**項目**をインデックスに基づくコレクションから項目を返すプロパティと`_NewEnum`コレクションの列挙子を返します。 コレクション インターフェイスを提供できます必要に応じて、**追加**と**削除**項目を挿入したり、コレクションから削除されるようにするメソッドと**クリア**を削除する方法すべての項目。  
  
 `enumerator`コレクション内の項目を反復処理するインターフェイスを提供する COM オブジェクトです。 4 つの必要なメソッドを使用してコレクションの要素へのシリアル アクセスを提供する列挙子インターフェイス: `Next`、 **Skip**、**リセット**、および`Clone`です。  
  
 典型的な (ただし、まったく虚数部) の説明を読むによって列挙子インターフェイスの詳細を学習できます[として](https://msdn.microsoft.com/library/ms680089.aspx)インターフェイスです。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [ATL のコレクションと列挙子クラス](../atl/atl-collection-and-enumerator-classes.md)  
 簡単な説明し、コレクションと列挙子を支援する ATL クラスへのリンクが実装を提供します。  
  
 [コレクションと列挙子インターフェイスのデザインの原則](../atl/design-principles-for-collection-and-enumerator-interfaces.md)  
 インターフェイスの種類ごとの背後にあるさまざまなデザインの原則について説明します。  
  
 [C++ 標準ライブラリに基づくコレクションの実装](../atl/implementing-an-stl-based-collection.md)  
 C++ 標準ライブラリ ベースのコレクションの実装の手順を説明する拡張例です。  
  
## <a name="related-sections"></a>関連項目  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Active Template Library を使用してプログラミングする方法に関する概念説明のトピックへのリンクを提供します。  
  
 [ATLCollections サンプル](../visual-cpp-samples.md)  
 使用方法を示すサンプル`ICollectionOnSTLImpl`と`CComEnumOnSTL`、およびカスタム コピー ポリシー クラスの実装です。  
  
## <a name="see-also"></a>関連項目  
 [概念](../atl/active-template-library-atl-concepts.md)

