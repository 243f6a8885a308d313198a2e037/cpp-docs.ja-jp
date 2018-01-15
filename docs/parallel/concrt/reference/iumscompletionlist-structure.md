---
title: "IUMSCompletionList 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList::IUMSCompletionList::GetUnblockNotifications
dev_langs: C++
helpviewer_keywords: IUMSCompletionList structure
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 50fd2381174e947e243ad6aa40516be5fd728902
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="iumscompletionlist-structure"></a>IUMSCompletionList 構造体
UMS の完了リストを表します。 UMS スレッドがブロックされると、基になる仮想プロセッサ ルートでスケジュールする内容を決定するためにスケジューラで指定されているスケジュールのコンテキストがディスパッチされ、元のスレッドがブロックされます。 元のスレッドがブロックされない場合、オペレーション システムは、このインターフェイスからアクセスできる完了リストのキューにそれを配置します。 スケジューラは指定されたスケジュール コンテキスト、または作業を検索するその他の場所にある完了リストを照会できます。  
  
## <a name="syntax"></a>構文  
  
```
struct IUMSCompletionList;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Iumscompletionlist::getunblocknotifications](#getunblocknotifications)|チェーンを取得`IUMSUnblockNotification`プロキシは、このメソッドの前回にブロック解除が関連付けられているスレッドを持つが呼び出された実行コンテキストを表すインターフェイス。|  
  
## <a name="remarks"></a>コメント  
 スケジューラは、コンプリート リストから項目をキューから削除するには、このインターフェイスを使用して後で実行される操作について十分に注意する必要があります。 項目は、実行可能なコンテキストのうち、スケジューラのリストに配置する必要があり、できるだけ早く一般的にアクセスできるようにします。 デキューされる項目のいずれかを設定した任意のロックの所有権ことができます。 スケジューラはできますがブロックされ、通常からアクセスできるスケジューラ内で、リストでこれらのアイテムの配置と項目をデキューする呼び出しの間の任意の関数呼び出しを行いません。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IUMSCompletionList`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="getunblocknotifications"></a>Iumscompletionlist::getunblocknotifications メソッド  
 チェーンを取得`IUMSUnblockNotification`プロキシは、このメソッドの前回にブロック解除が関連付けられているスレッドを持つが呼び出された実行コンテキストを表すインターフェイス。  
  
```
virtual IUMSUnblockNotification *GetUnblockNotifications() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 チェーン`IUMSUnblockNotification`インターフェイスです。  
  
### <a name="remarks"></a>コメント  
 実行コンテキストが再スケジュールされると、返された通知は無効です。  
  
## <a name="see-also"></a>参照  
 [同時実行 Namespace](concurrency-namespace.md)   
 [IUMSScheduler 構造体](iumsscheduler-structure.md)   
 [IUMSUnblockNotification 構造体](iumsunblocknotification-structure.md)
