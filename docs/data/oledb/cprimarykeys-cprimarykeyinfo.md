---
title: "CPrimaryKeys、CPrimaryKeyInfo |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- m_nOrdinal
- m_szTableSchema
- m_nColumnPropID
- CPrimaryKeys
- COLUMN_GUID
- CPrimaryKeyInfo
- m_szColumnName
- m_szTableCatalog
- COLUMN_PROPID
- m_guidColumn
- ORDINAL
- m_szTableName
dev_langs: C++
helpviewer_keywords:
- COLUMN_PROPID
- m_szTableSchema
- TABLE_CATALOG
- ORDINAL data member
- CPrimaryKeys typedef class
- TABLE_NAME
- m_nColumnPropID
- TABLE_SCHEMA
- m_szColumnName
- COLUMN_NAME
- m_szTableCatalog
- m_szTableName
- m_nOrdinal
- CPrimaryKeyInfo parameter class
- COLUMN_GUID
- m_guidColumn
ms.assetid: c27b97a4-a156-4f66-89e3-95f85d7d6281
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 98eaa6c7f9eb215959ce2e189d98acc7feee8101
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cprimarykeys-cprimarykeyinfo"></a>CPrimaryKeys、CPrimaryKeyInfo
Typedef クラスを呼び出す**CPrimaryKeys**そのパラメーター クラスを実装する**CPrimaryKeyInfo**です。  
  
## <a name="remarks"></a>コメント  
 参照してください[スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)typedef クラスの使用に関する詳細についてはします。  
  
 このクラスは、特定のユーザーによってカタログで定義されている主キー列を識別します。  
  
 次の表には、クラスのデータ メンバーとその対応する OLE DB 列が一覧表示します。 参照してください[PRIMARY_KEYS 行セット](https://msdn.microsoft.com/en-us/library/ms714362.aspx)で、 *OLE DB プログラマーズ リファレンス*スキーマと列の詳細についてはします。  
  
|データ メンバー|OLE DB 列|  
|------------------|--------------------|  
|m_szTableCatalog|TABLE_CATALOG|  
|m_szTableSchema|TABLE_SCHEMA|  
|m_szTableName|TABLE_NAME|  
|m_szColumnName|COLUMN_NAME|  
|m_guidColumn|COLUMN_GUID|  
|m_nColumnPropID|COLUMN_PROPID|  
|m_nOrdinal|序数|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbsch.h  
  
## <a name="see-also"></a>参照  
 [CRestrictions クラス](../../data/oledb/crestrictions-class.md)