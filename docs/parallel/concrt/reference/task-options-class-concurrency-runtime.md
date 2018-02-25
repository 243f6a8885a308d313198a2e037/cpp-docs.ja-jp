---
title: "task_options クラス (同時実行ランタイム) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ppltasks/concurrency::task_options
dev_langs:
- C++
ms.assetid: f93d146b-70f7-46ec-8c2f-c33b8bb0af69
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6ad83e9e0a871ddc2d8f2c767cb0690da1e6f349
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="taskoptions-class-concurrency-runtime"></a>task_options クラス (同時実行ランタイム)
タスクの作成に使用できるオプションを表します。  
  
## <a name="syntax"></a>構文  
  
```
class task_options;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[task_options::task_options コンス トラクター (同時実行ランタイム)](#ctor)|オーバーロードされます。 タスクの作成オプションに関する既定の一覧|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[task_options::get_cancellation_token メソッド (同時実行ランタイム)](#get_cancellation_token)|キャンセル トークンを返します|  
|[task_options::get_continuation_context メソッド (同時実行ランタイム)](#get_continuation_context)|継続コンテキストを返します|  
|[task_options::get_scheduler メソッド (同時実行ランタイム)](#get_scheduler)|スケジューラを返します|  
|[task_options::has_cancellation_token メソッド (同時実行ランタイム)](#has_cancellation_token)|キャンセル トークンがユーザーによって指定されているかどうかを示します|  
|[task_options::has_scheduler メソッド (同時実行ランタイム)](#has_scheduler)|スケジューラがユーザーによって指定されているかどうかを示します|  
|[task_options::set_cancellation_token メソッド (同時実行ランタイム)](#set_cancellation_token)|指定されたトークンをオプションに設定します|  
|[task_options::set_continuation_context メソッド (同時実行ランタイム)](#set_continuation_context)|指定された継続コンテキストをオプションに設定します|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `task_options`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** ppltasks.h  
  
 **名前空間:** concurrency  
  
##  <a name="get_cancellation_token">task_options::get_cancellation_token メソッド (同時実行ランタイム)</a>  
 キャンセル トークンを返します  
  
```
cancellation_token get_cancellation_token() const;
```  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="get_continuation_context"></a>  task_options::get_continuation_context Method (Concurrency Runtime)  
 継続コンテキストを返します  
  
```
task_continuation_context get_continuation_context() const;
```  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="get_scheduler">task_options::get_scheduler メソッド (同時実行ランタイム)</a>  
 スケジューラを返します  
  
```
scheduler_ptr get_scheduler() const;
```  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="has_cancellation_token">task_options::has_cancellation_token メソッド (同時実行ランタイム)</a>  
 キャンセル トークンがユーザーによって指定されているかどうかを示します  
  
```
bool has_cancellation_token() const;
```  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="has_scheduler">task_options::has_scheduler メソッド (同時実行ランタイム)</a>  
 スケジューラがユーザーによって指定されているかどうかを示します  
  
```
bool has_scheduler() const;
```  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="set_cancellation_token">task_options::set_cancellation_token メソッド (同時実行ランタイム)</a>  
 指定されたトークンをオプションに設定します  
  
```
void set_cancellation_token(cancellation_token _Token);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Token`  
  
##  <a name="set_continuation_context"></a>  task_options::set_continuation_context Method (Concurrency Runtime)  
 指定された継続コンテキストをオプションに設定します  
  
```
void set_continuation_context(task_continuation_context _ContinuationContext);
```  
  
### <a name="parameters"></a>パラメーター  
 `_ContinuationContext`  
  
##  <a name="ctor">task_options::task_options コンス トラクター (同時実行ランタイム)</a>  
 タスクの作成オプションに関する既定の一覧  
  
```
task_options();

task_options(
    cancellation_token _Token);

task_options(
    task_continuation_context _ContinuationContext);

task_options(
    cancellation_token _Token,
    task_continuation_context _ContinuationContext);

template<typename _SchedType>
task_options(
    std::shared_ptr<_SchedType> _Scheduler);

task_options(
    scheduler_interface& _Scheduler);

task_options(
    scheduler_ptr _Scheduler);

task_options(
    const task_options& _TaskOptions);
```  
  
### <a name="parameters"></a>パラメーター  
 `_SchedType`  
 `_Token`  
 `_ContinuationContext`  
 `_Scheduler`  
 `_TaskOptions`  
  
## <a name="see-also"></a>参照  
 [concurrency 名前空間](concurrency-namespace.md)
