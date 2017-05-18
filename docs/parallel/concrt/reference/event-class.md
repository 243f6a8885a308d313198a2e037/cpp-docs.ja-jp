---
title: "event クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- event
- CONCRT/concurrency::event
- CONCRT/concurrency::event::reset
- CONCRT/concurrency::event::set
- CONCRT/concurrency::event::wait
- CONCRT/concurrency::event::wait_for_multiple
- CONCRT/concurrency::event::timeout_infinite
dev_langs:
- C++
helpviewer_keywords:
- event class
ms.assetid: fba35a53-6568-4bfa-9aaf-07c0928cf73d
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: f858bfad08ca8d62c42556c54b505908b7122569
ms.contentlocale: ja-jp
ms.lasthandoff: 03/17/2017

---
# <a name="event-class"></a>event クラス
同時実行ランタイムを明示的に認識する手動リセット イベントです。  
  
## <a name="syntax"></a>構文  
  
```
class event;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[~ event デストラクター](#dtor)|イベントを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[reset](#reset)|イベントを非シグナル状態にリセットします。|  
|[set](#set)|イベントを通知します。|  
|[待機](#wait)|イベントがシグナル状態になるのを待機します。|  
|[wait_for_multiple](#wait_for_multiple)|複数のイベントがシグナル状態になるのを待機します。|  
  
### <a name="public-constants"></a>パブリック定数  
  
|名前|説明|  
|----------|-----------------|  
|[timeout_infinite](#timeout_infinite)|待機がタイムアウトしないことを示す値。|  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[同期データ構造](../../../parallel/concrt/synchronization-data-structures.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `event`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="ctor"></a>イベント 

 新しいイベントを構築します。  
  
```
_CRTIMP event();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="dtor"></a>~ イベント 

 イベントを破棄します。  
  
```
~event();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターが実行されるとイベントで待機するスレッドがなくなると想定されます。 まだ待機しているスレッドと共にイベントが破棄されるようにすると、未定義の動作が発生します。  
  
##  <a name="reset"></a>リセット 

 イベントを非シグナル状態にリセットします。  
  
```
void reset();
```  
  
##  <a name="set"></a>設定 

 イベントを通知します。  
  
```
void set();
```  
  
### <a name="remarks"></a>コメント  
 イベントを通知すると、イベントを待機している任意の数のコンテキストが実行できるようになります。  
  
##  <a name="timeout_infinite"></a>timeout_infinite 

 待機がタイムアウトしないことを示す値。  
  
```
static const unsigned int timeout_infinite = COOPERATIVE_TIMEOUT_INFINITE;
```  
  
##  <a name="wait"></a>待機 

 イベントがシグナル状態になるのを待機します。  
  
```
size_t wait(unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Timeout`  
 待機がタイムアウトするまでのミリ秒数。 この値が `COOPERATIVE_TIMEOUT_INFINITE` である場合、タイムアウトが存在しないことを意味します。  
  
### <a name="return-value"></a>戻り値  
 待機条件が満たされた場合は、値 `0` を返します。それ以外の場合は、イベントがシグナル状態になることなく待機がタイムアウトしたことを示す `COOPERATIVE_WAIT_TIMEOUT` 値を返します。  
  
> [!IMPORTANT]
>  [!INCLUDE[win8_appname_long](../../../build/includes/win8_appname_long_md.md)] アプリケーションでは、この呼び出しが現在のスレッドをブロックし、アプリケーションが応答しなくなる場合があるため、ASTA スレッドで `wait` を呼び出さないでください。  
  
##  <a name="wait_for_multiple"></a>wait_for_multiple 

 複数のイベントがシグナル状態になるのを待機します。  
  
```
static size_t __cdecl wait_for_multiple(
    _In_reads_(count) event** _PPEvents,
    size_t count,
    bool _FWaitAll,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PPEvents`  
 待機するイベントの配列。 配列内のイベントの数は、`count` パラメーターによって指定されます。  
  
 `count`  
 配列内のイベントの数は、`_PPEvents` パラメーターで指定されます。  
  
 `_FWaitAll`  
 この値を `true` に設定した場合、`_PPEvents` パラメーターに指定された配列内のすべてのイベントがシグナル状態になって初めて待機条件が満たされたと判断されます。 この値を `false` に設定した場合、`_PPEvents` パラメーターに指定された配列内のイベントが&1; つでもシグナル状態になれば待機条件が満たされたと判断されます。  
  
 `_Timeout`  
 待機がタイムアウトするまでのミリ秒数。 この値が `COOPERATIVE_TIMEOUT_INFINITE` である場合、タイムアウトが存在しないことを意味します。  
  
### <a name="return-value"></a>戻り値  
 待機条件が満たされた場合は、`_PPEvents` パラメーターに指定された配列内の、待機条件を満たしたインデックス。それ以外の場合は、条件が満たされることなく待機がタイムアウトしたことを示す `COOPERATIVE_WAIT_TIMEOUT` 値。  
  
### <a name="remarks"></a>コメント  
 `_FWaitAll` パラメーターの値を `true` に設定した場合は、すべてのイベントがシグナル状態になって初めて待機条件を満たしたことになります。その場合、この関数によって返されるインデックスには、`COOPERATIVE_WAIT_TIMEOUT` 値ではないという事実を除いて、特別な意味はありません。  
  
> [!IMPORTANT]
>  [!INCLUDE[win8_appname_long](../../../build/includes/win8_appname_long_md.md)] アプリケーションでは、この呼び出しが現在のスレッドをブロックし、アプリケーションが応答しなくなる場合があるため、ASTA スレッドで `wait_for_multiple` を呼び出さないでください。  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)

