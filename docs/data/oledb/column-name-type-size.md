---
title: "COLUMN_NAME_TYPE_SIZE |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- COLUMN_NAME_TYPE_SIZE
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_NAME_TYPE_SIZE macro
ms.assetid: b10f8ef9-78ce-4ec9-b4cc-4278271a46dd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d771a505aeabbf7096ad4bdafa967025927fa8ab
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="columnnametypesize"></a>COLUMN_NAME_TYPE_SIZE
行セットの特定の列を行セットのバインドを表します。 ような[COLUMN_NAME](../../data/oledb/column-name.md)ただし、このマクロは、データ型とサイズにも受け取ります。  
  
## <a name="syntax"></a>構文  
  
```cpp
COLUMN_NAME_TYPE_SIZE(pszName, wType, nLength, data)  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pszName`  
 [in]列の名前へのポインター。 名前は、Unicode 文字列にする必要があります。 たとえば、名前の前に 'L' を設定することによってこれを実行できます:`L"MyColumn"`です。  
  
 `wType`  
 [in]データ型。  
  
 `nLength`  
 [in]バイト単位でデータのサイズ。  
  
 `data`  
 [in]ユーザー レコードに対応するデータ メンバーです。  
  
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
 [COLUMN_NAME_EX](../../data/oledb/column-name-ex.md)   
 [COLUMN_NAME_LENGTH](../../data/oledb/column-name-length.md)   
 [COLUMN_NAME_LENGTH_STATUS](../../data/oledb/column-name-length-status.md)   
 [COLUMN_NAME_STATUS](../../data/oledb/column-name-status.md)   
 [COLUMN_NAME_PS](../../data/oledb/column-name-ps.md)   
 [COLUMN_NAME_PS_LENGTH](../../data/oledb/column-name-ps-length.md)   
 [COLUMN_NAME_PS_STATUS](../../data/oledb/column-name-ps-status.md)   
 [COLUMN_NAME_PS_LENGTH_STATUS](../../data/oledb/column-name-ps-length-status.md)   
 [COLUMN_NAME_TYPE](../../data/oledb/column-name-type.md)   
 [COLUMN_NAME_TYPE_PS](../../data/oledb/column-name-type-ps.md)   
 [COLUMN_NAME_TYPE_STATUS](../../data/oledb/column-name-type-status.md)