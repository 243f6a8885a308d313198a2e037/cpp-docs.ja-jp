---
title: "Crowsetimpl::getcolumninfo |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetColumnInfo
- CRowsetImpl.GetColumnInfo
- CRowsetImpl::GetColumnInfo
dev_langs:
- C++
helpviewer_keywords:
- GetColumnInfo method
ms.assetid: 9ef76525-f996-4c6f-81b9-68eb260350ef
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3cbcc7c25983680f32f1d5982188a853d8215358
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="crowsetimplgetcolumninfo"></a>CRowsetImpl::GetColumnInfo
特定のクライアント要求の列情報を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      static ATLCOLUMNINFO* CRowsetBaseImpl::GetColumnInfo(T* pv,  
   ULONG* pcCols);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pv`  
 [in]ユーザーへのポインター`CRowsetImpl`クラスを派生します。  
  
 `pcCols`  
 [in]返される列の数を (出力) のポインター。  
  
## <a name="return-value"></a>戻り値  
 静的なへのポインター **ATLCOLUMNINFO**構造体。  
  
## <a name="remarks"></a>コメント  
 このメソッドは、高度なオーバーライドです。  
  
 このメソッドは、特定のクライアント要求の列情報を取得するいくつかの基本実装クラスによって呼び出されます。 このメソッドが呼び出されます通常、`IColumnsInfoImpl`です。 このメソッドをオーバーライドする場合は、メソッドでのバージョンを配置する必要があります、 `CRowsetImpl`-クラスを派生します。 変更する必要がありますので、メソッドは、テンプレート化以外のクラスに配置することも、`pv`を適切な`CRowsetImpl`-クラスを派生します。  
  
 次の例で**GetColumnInfo の**使用します。 この例では**CMyRowset**は、 `CRowsetImpl`-クラスを派生します。 オーバーライドするために`GetColumnInfo`をこのクラスのすべてのインスタンスの配置では、次のメソッド、 **CMyRowset**クラス定義。  
  
 [!code-cpp[NVC_OLEDB_Provider#1](../../data/oledb/codesnippet/cpp/crowsetimpl-getcolumninfo_1.h)]  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [CRowsetImpl クラス](../../data/oledb/crowsetimpl-class.md)