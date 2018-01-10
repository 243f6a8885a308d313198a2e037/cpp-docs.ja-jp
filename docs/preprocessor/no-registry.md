---
title: "no_registry |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: no_registry
dev_langs: C++
helpviewer_keywords: no_registry attribute
ms.assetid: d30de4e2-551c-428c-98fd-951330d578d3
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9d2b4b34a4ebf266f4ae8062bb2fff0f80060a22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="noregistry"></a>no_registry
`no_registry` は、`#import` でインポートされたタイプ ライブラリをレジストリで検索しないようコンパイラに指示します。  
  
## <a name="syntax"></a>構文  
  
```  
  
#import filename no_registry  
```  
  
#### <a name="parameters"></a>パラメーター  
 *ファイル名*  
 タイプ ライブラリ。  
  
## <a name="remarks"></a>コメント  
 インクルード ディレクトリの参照されたタイプ ライブラリが見つからない場合は、タイプ ライブラリがレジストリにある場合、コンパイルは失敗します。  `no_registry`暗黙的に、インポートは他のタイプ ライブラリに反映される`auto_search`です。  
  
 ファイル名で指定され、`#import` に直接渡されるタイプ ライブラリの場合、コンパイラはレジストリを検索しません。  
  
 `auto_search` を指定すると、追加の `#import` が、初期 `no_registry` の `#import` 設定で生成されます (初期 `#import` ディレクティブが `no_registry` であった場合は、`auto_search` で生成される `#import` も `no_registry`)。  
  
 `no_registry`レジストリでファイルの古いバージョンを検索するコンパイラのリスクなし間の参照されるタイプ ライブラリをインポートする場合に便利です。  `no_registry`タイプ ライブラリが登録されていない場合に便利です。  
  
## <a name="see-also"></a>参照  
 [#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)