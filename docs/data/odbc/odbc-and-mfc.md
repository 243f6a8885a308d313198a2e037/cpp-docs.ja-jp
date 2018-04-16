---
title: "ODBC と MFC |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ODBC [C++], MFC
- connections [C++], databases
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- MFC [C++], ODBC and
- database connections [C++], MFC ODBC classes
ms.assetid: 98f02fd7-1235-437b-89a9-edfd0fc797f7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 48dd657d4cf1b315b29fda881b949dea29204f24
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="odbc-and-mfc"></a>ODBC と MFC
> [!NOTE]
>  MFC データベース クラスを使用するには、データ ソースの適切な ODBC ドライバーが必要です。 最新の Microsoft ODBC driver for SQL Server は[Microsoft ODBC Driver 13 for SQL Server](https://www.microsoft.com/en-us/download/details.aspx?id=50420)です。 データベース ベンダーのほとんどは、Windows 用の ODBC ドライバーを提供します。 
  
 このトピックでは、Microsoft Foundation Classes (MFC) ライブラリの ODBC ベースのデータベース クラスの主な概念を説明し、クラスの機能の概要を示します。 ODBC と MFC の詳細については、次のトピックを参照してください。  
  
-   [データ ソースへの接続](connecting-to-a-data-source.md)  
  
-   [レコードの選択と操作](selecting-and-manipulating-records.md)  
  
-   [フォームでのデータの表示と操作](displaying-and-manipulating-data-in-a-form.md)  
  
-   [ドキュメントとビューの操作](working-with-documents-and-views.md)  
  
-   [ODBC や SQL へのアクセス](access-to-odbc-and-sql.md)  
  
-   [MFC ODBC クラスに関する詳細情報](further-reading-about-the-mfc-odbc-classes.md)  
  
 ODBC に基づいて MFC データベース クラスは、ODBC ドライバーの使用可能な任意のデータベースにアクセスできるように設計されています。 クラスは、ODBC を使用するため、アプリケーションは多くのさまざまなデータ形式と異なるローカル/リモート構成内のデータにアクセスできます。 別のデータベース管理システム (Dbms) を処理する特別な大文字と小文字のコードを記述する必要はありません。 ユーザーにアクセスするデータの適切な ODBC ドライバーがある限り、プログラムを使用して格納されているテーブル内のデータを操作することができます。  
  
## <a name="see-also"></a>参照  
 [ODBC (Open Database Connectivity)](open-database-connectivity-odbc.md)