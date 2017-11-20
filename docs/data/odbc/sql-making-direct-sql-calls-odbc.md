---
title: "SQL: 直接 SQL 呼び出し (ODBC) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- SQL, direct calls from ODBC
- SQL, calling directly from ODBC
- ODBC, SQL calls
- SQL calls
- direct SQL calls from ODBC
ms.assetid: 091988d2-f5a5-4c2d-aa09-8779a9fb9607
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cac2844c64bf2157a9984a29b8885434eb07b811
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="sql-making-direct-sql-calls-odbc"></a>SQL: SQL の直接呼び出し (ODBC)
このトピックでは、次の内容について説明します。  
  
-   SQL の直接を使用するときに呼び出されます。  
  
-   [データ ソースへの呼び出し方法を行う SQL を直接](#_core_making_direct_sql_function_calls)です。  
  
> [!NOTE]
>  この情報は、MFC ODBC クラスに適用されます。 MFC DAO クラスを使用する場合は、"比較の Microsoft Jet データベース エンジン SQL と ANSI SQL"DAO ヘルプのトピックを参照してください。  
  
##  <a name="_core_when_to_call_sql_directly"></a>SQL を直接呼び出すときに  
 新しいテーブルを作成する (削除) のテーブルを削除、既存のテーブルを変更、インデックスを作成および変更を他の SQL 関数を実行、[データ ソース (ODBC)](../../data/odbc/data-source-odbc.md)スキーマ、データベースを使用してデータ ソースに直接 SQL ステートメントを実行する必要があります定義言語 (DDL) です。 (デザイン時)、テーブルのレコード セットを作成するウィザードを使用する場合は、レコード セットを表すテーブルの列を選択できます。 や他のユーザー データ ソースの追加列をテーブルに、後で、プログラムがコンパイルされた後にこれはできません。 データベース クラスは、直接サポートしていない DDL が実行時に動的に、レコード セットに新しい列をバインドするコードを記述することもできます。 このバインディングを行う方法については、次を参照してください。[レコード セット: 動的にバインディングのデータ列 (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)です。  
  
 DBMS 自体を使用するには、スキーマ、または DDL 関数を実行できるようにする別のツールを変更します。 レコードを返さない定義済みクエリ (ストアド プロシージャ) を呼び出すなどの SQL ステートメントを送信するための ODBC 関数呼び出しを使用することもできます。  
  
##  <a name="_core_making_direct_sql_function_calls"></a>SQL 関数の呼び出しを直接  
 SQL 呼び出しを使用して、直接実行できる、 [CDatabase クラス](../../mfc/reference/cdatabase-class.md)オブジェクト。 SQL ステートメントの文字列を設定 (通常の`CString`) に渡すと、 [:executesql](../../mfc/reference/cdatabase-class.md#executesql)のメンバー関数、`CDatabase`オブジェクト。 通常のレコードを返す SQL ステートメントを送信する ODBC 関数呼び出しを使用する場合、レコードは無視されます。  
  
## <a name="see-also"></a>関連項目  
 [SQL](../../data/odbc/sql.md)