---
title: "ODBC や SQL へのアクセス |Microsoft ドキュメント"
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
- API calls [C++], calling DAO or ODBC directly
- Windows API [C++], calling from MFC
- ODBC API functions [C++]
- ODBC API functions [C++], calling from MFC
- SQL [C++], calling ODBC API functions
- ODBC [C++], API functions
ms.assetid: 5613d7dc-00b7-4646-99ae-1116c05c52b4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 25e9533752e47e5cf3ea50e594a23b99e19355ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="access-to-odbc-and-sql"></a>ODBC や SQL へのアクセス
Microsoft Foundation Class ライブラリでは、Windows API 呼び出しの多くをカプセル化し、まだすべての Windows API 関数を直接呼び出すことができます。 データベース クラスでは、ODBC API に関しては高い柔軟性を付けます。 データベース クラスを使用すると、ODBC の複雑さの多くをシールド、中には、任意の場所から直接 ODBC API 関数を呼び出すことができます、プログラムでします。  
  
 同様に、操作ではあまりすることから、データベース クラスは、シールドする[SQL](../../data/odbc/sql.md)、直接する場合は、SQL を使用することができます。 レコード セット オブジェクトをカスタマイズするには、カスタムの SQL ステートメント (または既定のステートメントの一部を設定) を渡すことによって、レコード セットを開くとします。 使用して直接 SQL 呼び出しを行うことも、 [ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql)クラスのメンバー関数[CDatabase](../../mfc/reference/cdatabase-class.md)です。  
  
 詳細については、次を参照してください。 [ODBC: を呼び出す ODBC API 関数直接](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)と[SQL: を行う直接 SQL 呼び出し (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)です。  
  
## <a name="see-also"></a>参照  
 [ODBC と MFC](../../data/odbc/odbc-and-mfc.md)