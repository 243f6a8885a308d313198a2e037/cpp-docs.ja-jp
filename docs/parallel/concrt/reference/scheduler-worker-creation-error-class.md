---
title: "scheduler_worker_creation_error クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- scheduler_worker_creation_error
- CONCRT/concurrency::scheduler_worker_creation_error
- CONCRT/concurrency::scheduler_worker_creation_error::scheduler_worker_creation_error
dev_langs:
- C++
helpviewer_keywords:
- scheduler_worker_creation_error class
ms.assetid: 4aec1c3e-c32a-41b2-899d-2d898f23b3c7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c04a6b3c55920739a8c9bce70a147951edbf935a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="schedulerworkercreationerror-class"></a>scheduler_worker_creation_error クラス
このクラスは、同時実行ランタイムでワーカー実行コンテキストを作成できないためにスローされる例外を表します。  
  
## <a name="syntax"></a>構文  
  
```
class scheduler_worker_creation_error : public scheduler_resource_allocation_error;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[scheduler_worker_creation_error](#ctor)|オーバーロードされます。 `scheduler_worker_creation_error` オブジェクトを構築します。|  
  
## <a name="remarks"></a>コメント  
 同時実行ランタイムの内部から実行コンテキストを作成するには、オペレーティング システムに呼び出しが失敗したときに、この例外はスロー通常。 実行コンテキストは、同時実行ランタイムでタスクを実行するスレッドです。 通常は Win32 メソッドへの呼び出しから返されるエラー コード`GetLastError`型の値に変換されます`HRESULT`と基本クラスのメソッドを使用して取得できる`get_error_code`です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md)  
  
 `scheduler_worker_creation_error`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="ctor"></a> scheduler_worker_creation_error 

 `scheduler_worker_creation_error` オブジェクトを構築します。  
  
```
scheduler_worker_creation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_worker_creation_error(
    HRESULT _Hresult) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 エラーの説明メッセージ。  
  
 `_Hresult`  
 `HRESULT`例外の原因となったエラーの値。  
  
## <a name="see-also"></a>参照  
 [concurrency 名前空間](concurrency-namespace.md)
