---
title: "ATL COM プロパティ ページ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- property pages, COM
- ATL COM objects
- COM property pages
- property pages, ATL
- COM objects, ATL
- ATL property pages
ms.assetid: 663c7caa-2e5e-4b5c-b8ea-fd434ceb1654
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 08b1c31aeaba25f4eadad5225dd2f5607cf7053c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="atl-com-property-pages"></a>ATL COM プロパティ ページ
COM プロパティ ページでは、ユーザー インターフェイスを提供、プロパティを設定する (またはメソッドの呼び出し) の 1 つまたは複数の COM オブジェクトです。 プロパティ ページが、デザイン時に設定するコントロールのプロパティをできる豊富なユーザー インターフェイスを提供するための ActiveX コントロールで広く使用されます。  
  
 プロパティ ページは、COM オブジェクトを実装する、 [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246)または[IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996)インターフェイスです。 これらのインターフェイスに関連付けられるページを処理するメソッドを提供する、 `site` (ページのコンテナーを表す COM オブジェクト) の数と*オブジェクト*変更への応答であるメソッドが呼び出されます (COM オブジェクトユーザーをによるプロパティ ページの)。 プロパティ ページのコンテナーは、メソッド、プロパティ ページのインターフェイスで呼び出すと、ユーザー インターフェイスおよび変更を適用する際に非表示を基になるオブジェクトにユーザーによって行われたときに、ページを確認します。  
  
 各プロパティ ページは、そのプロパティを設定するオブジェクトとは無関係に完全に構築できます。 すべてプロパティ ページは、特定のインターフェイス (または一連のインターフェイス) を理解して、そのインターフェイスのメソッドを呼び出すためのユーザー インターフェイスを提供するをニーズです。  
  
 詳細については、次を参照してください。[プロパティ シートとプロパティ ページ](http://msdn.microsoft.com/library/windows/desktop/ms686577)で、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]です。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [プロパティ ページの指定](../atl/specifying-property-pages.md)  
 コントロールのプロパティ ページを指定するための手順と、クラスの例を示します。  
  
 [プロパティ ページの実装](../atl/implementing-property-pages.md)  
 オーバーライドするメソッドを含めて、プロパティ ページを実装するための手順を一覧表示します。 ATLPages サンプル プログラムに基づく完全な例について説明します。  
  
## <a name="related-sections"></a>関連項目  
 [例](../visual-cpp-samples.md)  
 使用してプロパティ ページを実装する例のサンプルの概要`IPropertyPageImpl`です。  
  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Active Template Library を使用してプログラミングする方法に関する概念説明のトピックへのリンクを提供します。  
  
## <a name="see-also"></a>参照  
 [概念](../atl/active-template-library-atl-concepts.md)

