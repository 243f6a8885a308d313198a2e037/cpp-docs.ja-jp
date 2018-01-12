---
title: "COLUMN_NAME_EX |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: COLUMN_NAME_EX
dev_langs: C++
helpviewer_keywords: COLUMN_NAME_EX macro
ms.assetid: 4f916a85-f6ae-464a-9cbe-0a56dbb274a6
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5658a2d0fb06f6bb9e9b8f2ab062f621b189cc75
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="columnnameex"></a>COLUMN_NAME_EX
行セットの特定の列を行セットのバインドを表します。 ような[COLUMN_NAME](../../data/oledb/column-name.md)ただし、このマクロは、データ型、サイズ、有効桁数、小数点以下桁数、列の長さ、および列の状態にも受け取ります。  
  
## <a name="syntax"></a>構文  
  
```  
  
COLUMN_NAME_EX(  
pszName  
,   
wType  
,   
nLength  
,   
nPrecision  
,   
nScale  
,   
data  
,   
length  
,   
status )  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pszName`  
 [in]列の名前へのポインター。 名前は、Unicode 文字列にする必要があります。 たとえば、名前の前に 'L' を設定することによってこれを実行できます:`L"MyColumn"`です。  
  
 `wType`  
 [in]データ型。  
  
 `nLength`  
 [in]バイト単位でデータのサイズ。  
  
 `nPrecision`  
 [in]データを取得するときに使用する最大有効桁数と`wType`は`DBTYPE_NUMERIC`します。 それ以外の場合、このパラメーターは無視されます。  
  
 `nScale`  
 [in]データを取得するときに使用する小数点以下桁数と`wType`は`DBTYPE_NUMERIC`または**DBTYPE_DECIMAL**です。  
  
 `data`  
 [in]ユーザー レコードに対応するデータ メンバーです。  
  
 *length*  
 [in]列の長さをバインドする変数です。  
  
 *status*  
 [in]列の状態にバインドする変数です。  
  
## <a name="remarks"></a>コメント  
 参照してください[COLUMN_NAME](../../data/oledb/column-name.md)場所について、 **COLUMN_NAME_\*** マクロを使用します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [マクロと OLE DB コンシューマー テンプレート用グローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN_NAME](../../data/oledb/column-name.md)   
 [COLUMN_NAME_LENGTH](../../data/oledb/column-name-length.md)   
 [COLUMN_NAME_LENGTH_STATUS](../../data/oledb/column-name-length-status.md)   
 [COLUMN_NAME_STATUS](../../data/oledb/column-name-status.md)   
 [COLUMN_NAME_PS](../../data/oledb/column-name-ps.md)   
 [COLUMN_NAME_PS_LENGTH](../../data/oledb/column-name-ps-length.md)   
 [COLUMN_NAME_PS_STATUS](../../data/oledb/column-name-ps-status.md)   
 [COLUMN_NAME_PS_LENGTH_STATUS](../../data/oledb/column-name-ps-length-status.md)   
 [COLUMN_NAME_TYPE](../../data/oledb/column-name-type.md)   
 [COLUMN_NAME_TYPE_PS](../../data/oledb/column-name-type-ps.md)   
 [COLUMN_NAME_TYPE_SIZE](../../data/oledb/column-name-type-size.md)   
 [COLUMN_NAME_TYPE_STATUS](../../data/oledb/column-name-type-status.md)