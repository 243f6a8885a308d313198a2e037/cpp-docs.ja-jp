---
title: "accelerator_view クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- accelerator_view
- AMPRT/accelerator_view
- AMPRT/Concurrency::accelerator_view:accelerator_view
- AMPRT/Concurrency::accelerator_view:create_marker
- AMPRT/Concurrency::accelerator_view:flush
- AMPRT/Concurrency::accelerator_view:get_accelerator
- AMPRT/Concurrency::accelerator_view:get_is_auto_selection
- AMPRT/Concurrency::accelerator_view:get_is_debug
- AMPRT/Concurrency::accelerator_view:get_queuing_mode
- AMPRT/Concurrency::accelerator_view:get_version
- AMPRT/Concurrency::accelerator_view:wait
- AMPRT/Concurrency::accelerator_view:accelerator
- AMPRT/Concurrency::accelerator_view:is_auto_selection
- AMPRT/Concurrency::accelerator_view:is_debug
- AMPRT/Concurrency::accelerator_view:queuing_mode
- AMPRT/Concurrency::accelerator_view:version
dev_langs:
- C++
helpviewer_keywords:
- accelerator_view class
ms.assetid: 9f298c21-bf62-46e0-88b8-01c5c78ef144
caps.latest.revision: 18
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
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: f5e6fd5689cf034cc260649fa005f7dfe6e9fd69
ms.lasthandoff: 03/17/2017

---
# <a name="acceleratorview-class"></a>accelerator_view クラス
C ++. AMP のデータ並列アクセラレータでの仮想デバイスの抽象化を表します。  
  
### <a name="syntax"></a>構文  
  
```  
class accelerator_view;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[accelerator_view コンス トラクター](#ctor)|`accelerator_view` クラスの新しいインスタンスを初期化します。|  
|[~ accelerator_view デストラクター](#dtor)|`accelerator_view` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[create_marker](#create_marker)|これまでにこの `accelerator_view` オブジェクトに送信されたすべてのコマンドの完了を追跡するために予定を返します。|  
|[flush](#flush)|`accelerator_view` オブジェクトのキューに格納されたすべての保留中のコマンドを実行のためにアクセラレータに送信します。|  
|[get_accelerator](#get_accelerator)|`accelerator` オブジェクトの `accelerator_view` オブジェクトを返します。|  
|[get_is_auto_selection](#get_is_auto_selection)|ランタイムの適切なアクセラレータが自動的に選択するかどうかを示すブール値を返すときに、`accelerator_view`に渡されるオブジェクト、 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)します。|  
|[get_is_debug](#get_is_debug)|`accelerator_view` オブジェクトに広範なエラー レポートに有効なデバッグ レイヤーがあるかどうかを示すブール値を返します。|  
|[get_queuing_mode](#get_queuing_mode)|`accelerator_view` オブジェクトのキュー モードを返します。|  
|[get_version](#get_version)|`accelerator_view` のバージョンを返します。|  
|[待機](#wait)|終了する `accelerator_view` オブジェクトに送信されるすべてのコマンドを待機します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator!=](#operator_neq)|この `accelerator_view` オブジェクトを別のオブジェクトと比較し、同じ場合は `false` を返し、それ以外の場合は `true` を返します。|  
|[operator=](#operator_eq)|指定された `accelerator_view` オブジェクトの内容をこのオブジェクトにコピーします。|  
|[operator==](#operator_eq_eq)|この `accelerator_view` オブジェクトを別のオブジェクトと比較し、同じ場合は `true` を返し、それ以外の場合は `false` を返します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[アクセラレータ](#accelerator)|`accelerator` オブジェクトの `accelerator_view` オブジェクトを取得します。|  
|[is_auto_selection](#is_auto_selection)|ランタイムの適切なアクセラレータが自動的に選択するかどうかを示すブール値を取得ときに、`accelerator_view`に渡されるオブジェクト、 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)します。|  
|[is_debug](#is_debug)|`accelerator_view` オブジェクトに広範なエラー レポートに有効なデバッグ レイヤーがあるかどうかを示すブール値を取得します。|  
|[queuing_mode](#queuing_mode)|`accelerator_view` オブジェクトのキュー モードを取得します。|  
|[version](#version)|accelerator のバージョンを取得します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `accelerator_view`  
  
### <a name="remarks"></a>コメント  
 `accelerator_view` オブジェクトは、アクセラレータの論理的で分離されたビューを表します。 単一の物理計算デバイスは、多くの論理的で分離された `accelerator_view` オブジェクトを使用できます。 各アクセラレータには既定の `accelerator_view` オブジェクトがあります。 追加の `accelerator_view` オブジェクトを作成できます。  
  
 物理デバイスは、多くのクライアント スレッド間で共有できます。 クライアント スレッドがアクセラレータの同じ `accelerator_view` オブジェクトを協調的に使用することができるか、または、各クライアントが他のクライアント スレッドから分離するために独立した `accelerator_view` オブジェクトを使用して計算デバイスと通信できます。  
  
 `accelerator_view`オブジェクトは、2 つのいずれかを設定できます[queuing_mode 列挙型](concurrency-namespace-enums-amp.md#queuing_mode)状態です。 キュー モードが `immediate` である場合、`copy` および `parallel_for_each` のようなコマンドが呼び出し元に戻るとすぐに対応するアクセラレータ デバイスに送信されます。 キュー モードが `deferred` の場合、このようなコマンドは `accelerator_view` オブジェクトに対応するコマンド キューに置かれます。 コマンドは、`flush()` が呼び出されるまでデバイスに実際に送信されません。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amprt.h  
  
 **名前空間:** Concurrency  

## <a name="accelerator"></a>アクセラレータ 

Accelerator_view オブジェクトのアクセラレータのオブジェクトを取得します。  
  
### <a name="syntax"></a>構文  
  
```  
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;  
```  
  
## <a name="ctor"></a>accelerator_view 

既存のコピーによって accelerator_view クラスの新しいインスタンスを初期化します。`accelerator_view`オブジェクトです。  
  
### <a name="syntax"></a>構文  
  
```  
accelerator_view( const accelerator_view & _Other );  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 コピーする `accelerator_view` オブジェクト。  
  
## <a name="accelerator_view__create_marker"></a>create_marker 

これまでにこの `accelerator_view` オブジェクトに送信されたすべてのコマンドの完了を追跡するために予定を返します。  
  
### <a name="syntax"></a>構文  
  
```  
concurrency::completion_future create_marker();  
```  
  
### <a name="return-value"></a>戻り値  
 これまでこの `accelerator_view` オブジェクトに送信されたすべてのコマンドの完了を追跡するための予定です。  
  
## <a name="flush"></a>フラッシュ 

実行のためにアクセラレータに accelerator_view オブジェクトをキューに保留中のすべてのコマンドを送信します。  
  
### <a name="syntax"></a>構文  
  
```  
void flush();  
```  
  
### <a name="return-value"></a>戻り値  
 `void` を返します。  

## <a name="accelerator_view__get_accelerator"></a>get_accelerator 

Accelerator_view オブジェクトのアクセラレータのオブジェクトを返します。
### <a name="syntax"></a>構文
```
accelerator get_accelerator() const;
```
### <a name="return-value"></a>戻り値
Accelerator_view オブジェクトのアクセラレータのオブジェクト。

## <a name="accelerator_view__get_is_auto_selection"></a>get_is_auto_selection 

選択を示すかどうか、ランタイムは自動的に適切なアクセラレータ accelerator_view に渡されるブール値を返す、 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)します。  
  
### <a name="syntax"></a>構文  
  
```  
bool get_is_auto_selection() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ランタイムが自動的に適切なアクセラレータを選択する場合は `true`、それ以外の場合は `false`。  
  
## <a name="accelerator_view__get_is_debug"></a>get_is_debug 

Accelerator_view オブジェクトに広範なエラー レポートに有効なデバッグ レイヤーがあるかどうかを示すブール値を返します。  
  
### <a name="syntax"></a>構文  
  
```  
bool get_is_debug() const;  
```  
  
### <a name="return-value"></a>戻り値  
 示すブール値かどうか、`accelerator_view`広範なエラー レポートに有効なデバッグ レイヤーが付きます。  

## <a name="accelerator_view__get_queuing_mode"></a>get_queuing_mode 

Accelerator_view オブジェクトのキュー モードを返します。  
  
### <a name="syntax"></a>構文  
  
```  
queuing_mode get_queuing_mode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 キュー モード、`accelerator_view`オブジェクトです。  
  
## <a name="accelerator_view__get_version"></a>get_version 

Accelerator_view のバージョンを返します。  
  
### <a name="syntax"></a>構文  
  
```  
unsigned int get_version() const;  
```  
  
### <a name="return-value"></a>戻り値  
 バージョン、`accelerator_view`です。  
  
## <a name="accelerator_view__is_auto_selection"></a>is_auto_selection 

選択を示すかどうか、ランタイムは自動的に適切なアクセラレータ accelerator_view に渡されるブール値を取得、 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)します。  
  
### <a name="syntax"></a>構文  
  
```  
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;  
```  
  
## <a name="accelerator_view__is_debug"></a>is_debug 

Accelerator_view オブジェクトに広範なエラー レポートに有効なデバッグ レイヤーがあるかどうかを示すブール値を取得します。  
  
### <a name="syntax"></a>構文  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
## <a name="accelerator_view__operator_neq"></a>operator! = 

別の場合は、この accelerator_view オブジェクトを比較し、返します`false`は同じである場合、それ以外の場合を返します`true`します。  
  
### <a name="syntax"></a>構文  
  
```  
bool operator!= (    const accelerator_view & _Other ) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 `accelerator_view`これと比較するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 2 つのオブジェクトが同一である場合は `false`。それ以外の場合は `true`。  
  
## <a name="accelerator_view__operator_eq"></a>演算子 = 

これには、指定された accelerator_view オブジェクトの内容をコピーします。  
  
### <a name="syntax"></a>構文  
  
```  
accelerator_view & operator= (    const accelerator_view & _Other );  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 コピー元の `accelerator_view` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 変更したへの参照を`accelerator_view`オブジェクトです。  
  
## <a name="accelerator_view__operator_eq_eq"></a>演算子 = = 

別の場合は、この accelerator_view オブジェクトを比較し、返します`true`は同じである場合、それ以外の場合を返します`false`します。  
  
### <a name="syntax"></a>構文  
  
```  
bool operator= = (    const accelerator_view & _Other ) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 `accelerator_view`これと比較するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 2 つのオブジェクトが同一である場合は `true`。それ以外の場合は `false`。  
  
## <a name="accelerator_view__queuing_mode"></a>queuing_mode 

Accelerator_view オブジェクトのキュー モードを取得します。  
  
### <a name="syntax"></a>構文  
  
```  
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;  
```  
  
## <a name="accelerator_view__version"></a>バージョン 

Accelerator_view のバージョンを取得します。  
  
### <a name="syntax"></a>構文  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
## <a name="accelerator_view__wait"></a>待機 

Accelerator_view オブジェクトに送信されたすべてのコマンドを完了するまで待機します。  
  
### <a name="syntax"></a>構文  
  
```  
void wait();  
```  
  
#### <a name="return-value"></a>戻り値  
 `void` を返します。  
  
#### <a name="remarks"></a>コメント  
 場合、 [queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode)は`immediate`、ブロックすることがなく、このメソッドをすぐに返します。  
  
##  <a name="dtor"></a>~ accelerator_view 

 Accelerator_view オブジェクトを破棄します。  
  
#### <a name="syntax"></a>構文  
  
```  
~accelerator_view();  
```  
  
### <a name="return-value"></a>戻り値  
  
 
## <a name="see-also"></a>関連項目  
 [Concurrency 名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)

