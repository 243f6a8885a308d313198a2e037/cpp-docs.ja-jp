---
title: "SCHEMA_ENTRY |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SCHEMA_ENTRY
dev_langs:
- C++
helpviewer_keywords:
- SCHEMA_ENTRY macro
ms.assetid: e8bee479-80f3-417e-8f41-cdaddd49690c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4b1ddabb976cdf4897dbd414433f013a84825d01
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="schemaentry"></a>SCHEMA_ENTRY
GUID をクラスに関連付けます。  
  
## <a name="syntax"></a>構文  
  
```cpp
      SCHEMA_ENTRY(guid,  
   rowsetClass);   
```  
  
#### <a name="parameters"></a>パラメーター  
 `guid`  
 スキーマ行セットの GUID。 参照してください[IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx)で、 *OLE DB プログラマーズ リファレンス*スキーマ行セットとその Guid の一覧についてはします。  
  
 *rowsetClass*  
 このクラスは、スキーマ行セットを表すために作成されます。  
  
## <a name="remarks"></a>コメント  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)クエリ、Guid の一覧については、マップ、ことができます。 または、GUID が指定された場合、行セットを作成できます。 スキーマ行セット`IDBSchemaRowsetImpl`作成は、標準的なに似ています`CRowsetImpl`-派生クラスを除いて、それを提供する必要があります、 **Execute**を次のシグネチャを持つメソッド。  
  
```  
HRESULT Execute (LONG* pcRowsAffected,  
    ULONG cRestrictions,  
    const VARIANT* rgRestrictions);  
```  
  
 これは、 **Execute**関数は、行セットのデータを追加します。 ATL プロジェクト ウィザードを作成する」の説明に従って[IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx)で、 *OLE DB プログラマーズ リファレンス*、3 つの必須の OLE DB スキーマの各プロジェクトのスキーマ行セットの初期 3。  
  
-   `DBSCHEMA_TABLES`  
  
-   **DBSCHEMA_COLUMNS**  
  
-   **DBSCHEMA_PROVIDER_TYPES**  
  
 ウィザードでは、スキーマ マップに対応する 3 つのエントリも追加されます。 参照してください[OLE DB テンプレート プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)詳細については、ウィザードを使用してプロバイダーを作成します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレート用マクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [BEGIN_SCHEMA_MAP](../../data/oledb/begin-schema-map.md)   
 [END_SCHEMA_MAP](../../data/oledb/end-schema-map.md)