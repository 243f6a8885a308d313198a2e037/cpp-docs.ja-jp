---
title: CDBPropSet::SetGUID | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CDBPropSet.SetGUID
- CDBPropSet.SetGUID
- ATL::CDBPropSet::SetGUID
- SetGUID
- CDBPropSet::SetGUID
dev_langs:
- C++
helpviewer_keywords:
- SetGUID method
- AddProperty method
ms.assetid: a4cce036-cf1f-4897-9712-7b01eaf887ff
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: edf9720e0f116060a06ffa56bf5c3e6c4c8691e1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="cdbpropsetsetguid"></a>CDBPropSet::SetGUID
セット、**コンス トラクターは**フィールドで、 **DBPROPSET**構造体。  
  
## <a name="syntax"></a>構文  
  
```cpp
      void SetGUID(const GUID& guid) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `guid`  
 [in]設定に使用される GUID、**コンス トラクターは**のフィールド、 [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx)構造体。  
  
## <a name="remarks"></a>コメント  
 このフィールドを設定することができます、[コンス トラクター](../../data/oledb/cdbpropset-cdbpropset.md)もします。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDBPropSet クラス](../../data/oledb/cdbpropset-class.md)