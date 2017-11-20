---
title: "#<a name=\"import-attributes-c--microsoft-docs\"></a>インポート属性 (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: '#import directive, attributes'
ms.assetid: 2a5085e3-82ee-4f83-892b-0aa6cc13863b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fd11326e33ff783b3868215794f9803e97d41c55
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="import-attributes-c"></a>#import の属性 (C++)
#import ディレクティブと共に使用される属性のリンクを示します。  
  
 **Microsoft 固有の仕様**  
  
 次の属性は、#import ディレクティブで使用できます。  
  
|属性|説明|  
|---------------|-----------------|  
|[auto_rename](../preprocessor/auto-rename.md)|潜在的な名前の競合を解決するため、変数名に 2 つのアンダースコア (__) を追加して C++ の予約語の名前を変更します。|  
|[auto_search](../preprocessor/auto-search.md)|タイプ ライブラリが #import を使用して参照され、自身が別のタイプ ライブラリを参照している場合、コンパイラが他のタイプ ライブラリに対して暗黙の #import を実行できることを指定します。|  
|[embedded_idl](../preprocessor/embedded-idl.md)|属性が生成されたコードを保持して、タイプ ライブラリを .tlh ファイルに書き込むことを指定します。|  
|[除外します。](../preprocessor/exclude-hash-import.md)|生成されるタイプ ライブラリのヘッダー ファイルから項目を除外します。|  
|[high_method_prefix](../preprocessor/high-method-prefix.md)|高レベルのプロパティおよびメソッドの名前付けで使用されるプレフィックスを指定します。|  
|[high_property_prefixes](../preprocessor/high-property-prefixes.md)|3 つのプロパティ メソッドの代替プレフィックスを指定します。|  
|[implementation_only](../preprocessor/implementation-only.md)|.tlh ヘッダー ファイル (プライマリ ヘッダー ファイル) の生成を抑制します。|  
|[include()](../preprocessor/include-parens.md)|自動除外を無効にします。|  
|[inject_statement](../preprocessor/inject-statement.md)|タイプ ライブラリ ヘッダーに引数をソース テキストとして挿入します。|  
|[named_guids](../preprocessor/named-guids.md)|定義し、旧スタイルの形式の GUID 変数を初期化するようにコンパイラに指示**LIBID_MyLib**、 **CLSID_MyCoClass**、 **IID_MyInterface**、および**DIID_MyDispInterface**です。|  
|[no_auto_exclude](../preprocessor/no-auto-exclude.md)|自動除外を無効にします。|  
|[no_dual_interfaces](../preprocessor/no-dual-interfaces.md)|コンパイラがデュアル インターフェイス メソッドのラッパー関数を生成する方法を変更します。|  
|[no_implementation](../preprocessor/no-implementation.md)|ラッパー メンバー関数の実装を含む .tli ヘッダーの生成を抑制します。|  
|[no_namespace](../preprocessor/no-namespace.md)|名前空間名がコンパイラによって生成されないことを指定します。|  
|[no_registry](../preprocessor/no-registry.md)|タイプ ライブラリのレジストリを検索しないようコンパイラに指示します。|  
|[no_search_namespace](../preprocessor/no-search-namespace.md)|同じ機能を持つ、 [no_namespace](../preprocessor/no-namespace.md)属性は、#import ディレクティブを使用するタイプ ライブラリで使用される、 [auto_search](../preprocessor/auto-search.md)属性。|  
|[no_smart_pointers](../preprocessor/no-smart-pointers.md)|タイプ ライブラリのすべてのインターフェイスに対して、スマート ポインターの作成を抑制します。|  
|[raw_dispinterfaces](../preprocessor/raw-dispinterfaces.md)|ディスパッチインターフェイス メソッドおよびプロパティを呼び出すための低レベルのラッパー関数を生成するようにコンパイラに指示**idispatch::invoke**を返すと、`HRESULT`エラー コード。|  
|[raw_interfaces_only](../preprocessor/raw-interfaces-only.md)|エラー処理ラッパー関数の生成を抑制し、[プロパティ](../cpp/property-cpp.md)ラッパー関数を使用して宣言します。|  
|[raw_method_prefix](../preprocessor/raw-method-prefix.md)|名前の衝突を避けるために異なるプレフィックスを指定します。|  
|[raw_native_types](../preprocessor/raw-native-types.md)|高レベルのラッパー関数の COM サポート クラスの使用を無効にし、代わりに低レベルのデータ型の使用を強制します。|  
|[raw_property_prefixes](../preprocessor/raw-property-prefixes.md)|3 つのプロパティ メソッドの代替プレフィックスを指定します。|  
|[rename](../preprocessor/rename-hash-import.md)|名前の衝突の問題を回避します。|  
|[rename_namespace](../preprocessor/rename-namespace.md)|タイプ ライブラリの内容を含む名前空間の名前を変更します。|  
|[rename_search_namespace](../preprocessor/rename-search-namespace.md)|同じ機能を持つ、 [rename_namespace](../preprocessor/rename-namespace.md)属性は、#import ディレクティブを使用するタイプ ライブラリで使用される、 [auto_search](../preprocessor/auto-search.md)属性。|  
|[tlbid](../preprocessor/tlbid.md)|プライマリ タイプ ライブラリ以外のライブラリの読み込みを許可します。|  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)