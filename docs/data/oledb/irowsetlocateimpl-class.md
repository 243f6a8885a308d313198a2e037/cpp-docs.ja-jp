---
title: "IRowsetLocateImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IRowsetLocateImpl
dev_langs: C++
helpviewer_keywords:
- providers, bookmarks
- IRowsetLocateImpl class
- bookmarks, OLE DB
ms.assetid: a8aa3149-7ce8-4976-a680-2da193fd3234
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: da010f02ec29b4882ffeb1bdf1c5fa7fd67c8615
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetlocateimpl-class"></a>IRowsetLocateImpl クラス
OLE DB を実装する[IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx)インターフェイスで、行セットから任意の行をフェッチします。  
  
## <a name="syntax"></a>構文  
  
```  
template <  
   class T,   
   class RowsetInterface,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap < RowClass::KeyType, RowClass* >,   
   class BookmarkKeyType = LONG,   
   class BookmarkType = LONG,   
   class BookmarkMapClass = CAtlMap < RowClass::KeyType, RowClass* >  
>  
class ATL_NO_VTABLE IRowsetLocateImpl : public IRowsetImpl<  
   T,   
   RowsetInterface,   
   RowClass,   
   MapClass  
>  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス`IRowsetLocateImpl`です。  
  
 `RowsetInterface`  
 派生したクラス`IRowsetImpl`です。  
  
 `RowClass`  
 記憶域ユニットを**HROW**です。  
  
 `MapClass`  
 すべての行ハンドルの記憶域ユニットでは、プロバイダーによって保持されています。  
  
 `BookmarkKeyType`  
 長整数型または文字列など、ブックマークの型。 通常のブックマークには、少なくとも 2 バイトの長さが必要です。 (単一バイトの長さは、OLE DB 用に予約[標準ブックマーク](https://msdn.microsoft.com/en-us/library/ms712954.aspx)**DBBMK_FIRST**、 **DBBMK_LAST**、および**一方**)。  
  
 `BookmarkType`  
 ブックマークのデータ間の関係を維持するためのマッピング メカニズムです。  
  
 `BookmarkMapClass`  
 すべての行ハンドルの記憶域ユニットは、ブックマークを保持します。  
  
## <a name="members"></a>メンバー  
  
### <a name="interface-methods"></a>インターフェイス メソッド  
  
|||  
|-|-|  
|[Compare](../../data/oledb/irowsetlocateimpl-compare.md)|2 つのブックマークを比較します。|  
|[GetRowsAt](../../data/oledb/irowsetlocateimpl-getrowsat.md)|ブックマークからのオフセットによって指定された行で始まる行がフェッチされます。|  
|[GetRowsByBookmark](../../data/oledb/irowsetlocateimpl-getrowsbybookmark.md)|指定されたブックマークに一致する行をフェッチします。|  
|[ハッシュ](../../data/oledb/irowsetlocateimpl-hash.md)|指定されたブックマークの値のハッシュを返します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[m_rgBookmarks](../../data/oledb/irowsetlocateimpl-m-rgbookmarks.md)|ブックマークの配列。|  
  
## <a name="remarks"></a>コメント  
 `IRowsetLocateImpl`OLE DB テンプレートの実装、 [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx)インターフェイスです。 `IRowsetLocate`行セットからの任意の行のフェッチに使用されます。 このインターフェイスを実装していない行セットは、`sequential`行セット。 ときに`IRowsetLocate`存在は、行セットで列 0 行のブックマークです。 この列を読み取り、ブックマーク値を取得、同じ行に位置を変更するために使用できます。  
  
 `IRowsetLocateImpl`プロバイダーのブックマーク サポートの実装に使用します。 ブックマークは、プレース ホルダー (インデックス行セットで)、行にすばやく戻るコンシューマーを有効にするデータを高速アクセスを許可します。 プロバイダーをどのようなブックマークが一意に決定の行を識別します。 使用して`IRowsetLocateImpl`メソッド、ブックマークを比較する、行のフェッチは、オフセット、ブックマークによる行のフェッチされ、ブックマークのハッシュ値を返します。  
  
 OLE DB のブックマークを行セットをサポートするには、このクラスから継承行セットを確認します。  
  
 ブックマーク サポートを実装する方法については、次を参照してください[プロバイダーのブックマークをサポートして](../../data/oledb/provider-support-for-bookmarks.md)で、 *Visual C++ プログラマ ガイド*と[ブックマーク](https://msdn.microsoft.com/en-us/library/ms709728.aspx)、で*。OLE DB プログラマーズ リファレンス*Platform SDK でします。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー**: atldb.h  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [IRowsetLocate:IRowset](https://msdn.microsoft.com/en-us/library/ms721190.aspx)   
 [プロバイダーのブックマーク サポート](../../data/oledb/provider-support-for-bookmarks.md)   
 [ブックマーク](https://msdn.microsoft.com/en-us/library/ms709728.aspx)