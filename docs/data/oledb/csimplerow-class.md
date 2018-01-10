---
title: "CSimpleRow クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CSimpleRow
- ATL::CSimpleRow
- ATL.CSimpleRow
dev_langs: C++
helpviewer_keywords: CSimpleRow class
ms.assetid: 06d9621d-60cc-4508-8b0c-528d1b1a809b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8a5d8777a1219e204e0db1a16858ef30009dc67d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="csimplerow-class"></a>CSimpleRow クラス
使用されている行ハンドルの既定の実装を提供、 [IRowsetImpl](../../data/oledb/irowsetimpl-class.md)クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CSimpleRow  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[AddRefRow](../../data/oledb/csimplerow-addrefrow.md)|既存の行ハンドルに参照カウントを追加します。|  
|[Compare](../../data/oledb/csimplerow-compare.md)|同じ行インスタンスを参照しているかを参照してください。 2 つの行を比較します。|  
|[CSimpleRow](../../data/oledb/csimplerow-csimplerow.md)|コンストラクターです。|  
|[ReleaseRow](../../data/oledb/csimplerow-releaserow.md)|行を解放します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[m_dwRef](../../data/oledb/csimplerow-m-dwref.md)|既存の行ハンドルへの参照カウント。|  
|[m_iRowset](../../data/oledb/csimplerow-m-irowset.md)|カーソルを表す行セットのインデックスです。|  
  
## <a name="remarks"></a>コメント  
 行ハンドルは、結果の行の一意のタグで、論理的にします。 `IRowsetImpl`新たに作成`CSimpleRow`で要求されているすべての行の[irowsetimpl::getnextrows](../../data/oledb/irowsetimpl-getnextrows.md)です。 `CSimpleRow`既定のテンプレート引数にはも行ハンドルの独自の実装に置き換えることが`IRowsetImpl`です。 このクラスを交換する唯一の要件は、型の 1 つのパラメーターを受け取るコンス トラクターを指定の置換クラスこと**長い**です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [IRowsetImpl クラス](../../data/oledb/irowsetimpl-class.md)