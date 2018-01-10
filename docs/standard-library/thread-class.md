---
title: "thread クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- thread/std::thread
- thread/std::thread::id Class
- thread/std::thread::thread
- thread/std::thread::detach
- thread/std::thread::get_id
- thread/std::thread::hardware_concurrency
- thread/std::thread::join
- thread/std::thread::joinable
- thread/std::thread::native_handle
- thread/std::thread::swap
dev_langs: C++
ms.assetid: df249bc7-ff81-4ff9-a6d6-5e3d9a8f56a1
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::thread [C++]
- std::thread [C++], thread
- std::thread [C++], detach
- std::thread [C++], get_id
- std::thread [C++], hardware_concurrency
- std::thread [C++], join
- std::thread [C++], joinable
- std::thread [C++], native_handle
- std::thread [C++], swap
ms.workload: cplusplus
ms.openlocfilehash: 2e2d9d1bd19b34cd4b542d0325b06ad57e1a7c51
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="thread-class"></a>thread クラス
アプリケーション内の実行スレッドを観察および管理するために使用するオブジェクトを定義します。  
  
## <a name="syntax"></a>構文  
  
```
class thread;
```  
  
## <a name="remarks"></a>コメント  
 アプリケーション内の実行スレッドを観察および管理するために `thread` オブジェクトを使用できます。 既定のコンストラクターを使用して作成されたスレッド オブジェクトは、実行スレッドに関連付けられていません。 呼び出し可能オブジェクトを使用して構築されたスレッド オブジェクトは、新しい実行スレッドを作成し、そのスレッドで呼び出し可能オブジェクトを呼び出します。 スレッド オブジェクトは移動できますが、コピーできません。 したがって、実行スレッドは 1 つのスレッド オブジェクトだけに関連付けることができます。  
  
 すべての実行スレッドに `thread::id` 型の一意の識別子があります。 関数 `this_thread::get_id` は呼び出しスレッドの識別子を返します。 メンバー関数 `thread::get_id` は、スレッド オブジェクトによって管理されるスレッドの識別子を返します。 既定で構築されるスレッド オブジェクトの場合、`thread::get_id` メソッドは、呼び出し時に結合できる実行スレッドに対して、既定で構築されるスレッド オブジェクトすべてで同じで、`this_thread::get_id` によって返される値とは異なる値を持つオブジェクトを返します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-classes"></a>パブリック クラス  
  
|名前|説明|  
|----------|-----------------|  
|[thread::id クラス](#id_class)|関連するスレッドを一意に識別します。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[thread](#thread)|`thread` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[デタッチ](#detach)|`thread` オブジェクトから関連するスレッドをデタッチします。|  
|[get_id](#get_id)|関連付けられたスレッドの一意の識別子を返します。|  
|[hardware_concurrency](#hardware_concurrency)|静的。 ハードウェア スレッド コンテキストの数の見積もりを返します。|  
|[join](#join)|関連のスレッドが完了するまでブロックします。|  
|[参加可能です](#joinable)|関連付けられたスレッドが結合可能かどうかを指定します。|  
|[native_handle](#native_handle)|スレッド ハンドルを表す実装固有の型を返します。|  
|[swap](#swap)|オブジェクトの状態を指定した `thread` オブジェクトと交換します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[thread::operator=](#op_eq)|スレッドを現在の `thread` オブジェクトと関連付けます。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<スレッド >  
  
 **名前空間:** std  
  
##  <a name="detach"></a>thread::detach
 関連するスレッドをデタッチします。 オペレーティング システムは、終了時にスレッド リソースを解放することが必要になります。  
  
```
void detach();
```  
  
### <a name="remarks"></a>コメント  
 `detach` を呼び出した後、後続の [get_id](#get_id) 呼び出しによって [id](#id_class) が返されます。  
  
 呼び出し元のオブジェクトに関連付けられているスレッドが結合可能でない場合、関数は、エラー コード `invalid_argument` で [system_error](../standard-library/system-error-class.md) をスローします。  
  
 呼び出し元のオブジェクトに関連付けられているスレッドが無効な場合、関数は、エラー コード `no_such_process` で `system_error` をスローします。  
  
##  <a name="get_id"></a>thread::get_id
 関連付けられたスレッドの一意の識別子を返します。  
  
```
id get_id() const noexcept;
```  
  
### <a name="return-value"></a>戻り値  
 関連付けられたスレッドを一意に識別する [thread::id](#id_class) オブジェクト、またはオブジェクトに関連付けられているスレッドがない場合は `thread::id()`。  
  
##  <a name="hardware_concurrency"></a>thread::hardware_concurrency
 ハードウェア スレッド コンテキストの数の見積もりを返す静的メソッド。  
  
```
static unsigned int hardware_concurrency() noexcept;
```  
  
### <a name="return-value"></a>戻り値  
 ハードウェア スレッド コンテキストの数の見積もり。 値を計算できない場合や、値が適切に定義されていない場合、このメソッドは 0 を返します。  
  
##  <a name="id_class"></a>  thread::id クラス  
 プロセス内の各実行スレッドの一意の識別子を提供します。  
  
```
class thread::id {
    id() noexcept;
};
```  
  
### <a name="remarks"></a>コメント  
 既定のコンストラクターは、既存のスレッドのオブジェクトについて、`thread::id` オブジェクトに等しいオブジェクトを作成しません。  
  
 既定で構築される `thread::id` オブジェクトは等しいものになります。  
  
##  <a name="join"></a>thread::join
 呼び出し元のオブジェクトに関連付けられている実行スレッドが完了するまでブロックします。  
  
```
void join();
```  
  
### <a name="remarks"></a>コメント  
 呼び出しが成功すると、呼び出し元のオブジェクトの後続の [get_id](#get_id) 呼び出しは、既存のどのスレッドの `thread::id` にも等しくない既定の [thread::id](#id_class) を返します。呼び出しが成功しなかった場合、`get_id` によって返される値は変更されません。  
  
##  <a name="joinable"></a>thread::joinable
 関連付けられたスレッドが*結合可能*かどうかを指定します。  
  
```
bool joinable() const noexcept;
```  
  
### <a name="return-value"></a>戻り値  
 関連付けられたスレッドが*結合可能*な場合は `true`、それ以外の場合は `false`。  
  
### <a name="remarks"></a>コメント  
 `get_id() != id()` の場合、スレッド オブジェクトは*結合可能*です。  
  
##  <a name="native_handle"></a>thread::native_handle
 スレッド ハンドルを表す実装固有の型を返します。 スレッド ハンドルは、実装固有の方法で使用できます。  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>戻り値  
 `native_handle_type` は、`void *` としてキャストされる Win32 `HANDLE` と定義されます。  
  
##  <a name="op_eq"></a>  thread::operator=  
 指定したオブジェクトのスレッドを現在のオブジェクトに関連付けます。  
  
```
thread& operator=(thread&& Other) noexcept;
```  
  
### <a name="parameters"></a>パラメーター  
 `Other`  
 `thread` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `*this`  
  
### <a name="remarks"></a>コメント  
 メソッドは、呼び出し元のオブジェクトが結合可能である場合、デタッチを呼び出します。  
  
 関連付けが行われると、`Other` が既定で構築される状態に設定されます。  
  
##  <a name="swap"></a>thread::swap
 オブジェクトの状態を、指定された `thread` オブジェクトの状態と交換します。  
  
```
void swap(thread& Other) noexcept;
```  
  
### <a name="parameters"></a>パラメーター  
 `Other`  
 `thread` オブジェクト。  
  
##  <a name="thread"></a>  thread::thread コンストラクター  
 `thread` オブジェクトを構築します。  
  
```
thread() noexcept;
template <class Fn, class... Args>
explicit thread(Fn&& F, Args&&... A);

thread(thread&& Other) noexcept;
```  
  
### <a name="parameters"></a>パラメーター  
 `F`  
 スレッドによって実行されるアプリケーション定義関数。  
  
 `A`  
 `F` に渡す引数のリスト。  
  
 `Other`  
 既存の `thread` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 最初のコンストラクターは、実行スレッドに関連付けられていないオブジェクトを構築します。 構築されたオブジェクトの `get_id` への呼び出しによって返される値は `thread::id()` です。  
  
 2 番目のコンストラクターは、新しい実行スレッドに関連付けられているオブジェクトを構築し、[\<functional>](../standard-library/functional.md) で定義されている擬似関数 `INVOKE` を実行します。 新しいスレッドを開始するのに十分なリソースがない場合、関数は、エラー コード `resource_unavailable_try_again` で [system_error](../standard-library/system-error-class.md) オブジェクトをスローします。 `F` への呼び出しが、キャッチされない例外で終了する場合、[terminate](../standard-library/exception-functions.md#terminate) が呼び出されます。  
  
 3 番目のコンストラクターは、`Other` に関連付けられているスレッドに関連付けられているオブジェクトを構築します。 `Other` は既定で構築される状態に設定されます。  
  
## <a name="see-also"></a>参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<thread>](../standard-library/thread.md)



