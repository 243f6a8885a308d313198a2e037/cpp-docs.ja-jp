---
title: CNoAccessor クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CNoAccessor
- CNoAccessor
- ATL.CNoAccessor
dev_langs:
- C++
helpviewer_keywords:
- CNoAccessor class
ms.assetid: eb669ae5-0a56-49a3-9646-c4ae6239da31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0527f4b154b4b5d0dc07b2b152a3975f49746abf
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39336740"
---
# <a name="cnoaccessor-class"></a>CNoAccessor クラス
テンプレート引数として使用できます (`TAccessor`) のテンプレートのクラスなど`CCommand`と`CTable`、アクセサー クラスの引数を必要とします。  
  
## <a name="syntax"></a>構文

```cpp
class CNoAccessor  
```  
  
## <a name="remarks"></a>Remarks  
 使用`CNoAccessor`パラメーターをサポートまたは列を出力するクラスしたくない場合は、テンプレート引数として。  
  
 `CNoAccessor` 次のスタブ メソッドは、それぞれのメソッドに対応するその他のアクセサー クラスを実装します。  
  
-   `BindColumns` -列は、アクセサーにバインドします。  
  
-   `BindParameters` -列に作成されたパラメーターをバインドします。  
  
-   `Bind` -バインドを作成します。  
  
-   `Close` -アクセサーを閉じます。  
  
-   `ReleaseAccessors` -クラスによって作成されたアクセサーを解放します。  
  
-   `FreeRecordMemory` -解放する必要がある現在のレコード内の列を解放します。  
  
-   `GetColumnInfo` -開かれた行セットから列情報を取得します。  
  
-   `GetNumAccessors` -クラスによって作成されたアクセサーの数を取得します。  
  
-   `IsAutoAccessor` 移動操作中に、アクセサーのデータが自動的に取得される場合に true を返します。  
  
-   `GetHAccessor` -指定されたアクセサーのアクセサーのハンドルを取得します。  
  
-   `GetBuffer` -ブックマーク バッファーへのポインターを取得します。  
  
-   `NoBindOnNullRowset` -空の行セットのデータ バインディングをできないようにします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)