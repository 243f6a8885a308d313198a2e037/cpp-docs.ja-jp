---
title: "cancellation_token_source クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cancellation_token_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::cancellation_token_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::cancel
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::create_linked_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::get_token
dev_langs:
- C++
helpviewer_keywords:
- cancellation_token_source class
ms.assetid: 3548b1a0-12b0-4334-95db-4bf57141c066
caps.latest.revision: 10
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
ms.openlocfilehash: f41a4a21af5bc37ab612221152b8311a5a91d914
ms.contentlocale: ja-jp
ms.lasthandoff: 03/17/2017

---
# <a name="cancellationtokensource-class"></a>cancellation_token_source クラス
`cancellation_token_source` クラスは、取り消し可能な操作を取り消す機能を表します。  
  
## <a name="syntax"></a>構文  
  
```
class cancellation_token_source;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[cancellation_token_source](#ctor)|オーバーロードされます。 新しい `cancellation_token_source` を構築します。 ソースを使用して、一部の取り消し可能な操作について取り消しのフラグを設定できます。|  
|[~ cancellation_token_source デストラクター](#dtor)||  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[キャンセル](#cancel)|トークンを取り消します。 トークンを利用するすべての `task_group`、`structured_task_group`、および `task` は、このメソッドが呼び出されたときに取り消され、次の割り込みポイントで例外がスローされます。|  
|[create_linked_source](#create_linked_source)|オーバーロードされます。 指定されたトークンが取り消されたときに取り消される `cancellation_token_source` を作成します。|  
|[get_token](#get_token)|このソースに関連付けられたキャンセル トークンを返します。 返されたトークンは、取り消すためにポーリングしたり、取り消しが発生した場合にコールバックを指定したりできます。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator!=](#operator_neq)||  
|[operator=](#operator_eq)||  
|[operator==](#operator_eq_eq)||  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `cancellation_token_source`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** pplcancellation_token.h  
  
 **名前空間:** concurrency  
  
##  <a name="dtor"></a>~ cancellation_token_source 

```
~cancellation_token_source();
```  
  
##  <a name="cancel"></a>キャンセル 

 トークンを取り消します。 トークンを利用するすべての `task_group`、`structured_task_group`、および `task` は、このメソッドが呼び出されたときに取り消され、次の割り込みポイントで例外がスローされます。  
  
```
void cancel() const;
```  
  
##  <a name="ctor"></a>cancellation_token_source 

 新しい `cancellation_token_source` を構築します。 ソースを使用して、一部の取り消し可能な操作について取り消しのフラグを設定できます。  
  
```
cancellation_token_source();

cancellation_token_source(const cancellation_token_source& _Src);

cancellation_token_source(cancellation_token_source&& _Src);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Src`  
  
##  <a name="create_linked_source"></a>create_linked_source 

 指定されたトークンが取り消されたときに取り消される `cancellation_token_source` を作成します。  
  
```
static cancellation_token_source create_linked_source(
    cancellation_token& _Src);

template<typename _Iter>
static cancellation_token_source create_linked_source(_Iter _Begin, _Iter _End);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Iter`  
 `_Src`  
 取り消された場合は、返されるトークン ソースの取り消しの原因となるトークン。 このパラメーターに含まれるソースとは関係なく、返されるトークン ソースも取り消されることに注意してください。  
  
 `_Begin`  
 C++ 標準ライブラリに反復子トークンの範囲の先頭に対応する取り消しをリッスンします。  
  
 `_End`  
 C++ 標準ライブラリに反復子トークンの範囲の終了に対応する取り消しをリッスンします。  
  
### <a name="return-value"></a>戻り値  
 `cancellation_token_source` パラメーターによって指定されたトークンが取り消されたときに取り消される `_Src`。  
  
##  <a name="get_token"></a>get_token 

 このソースに関連付けられたキャンセル トークンを返します。 返されたトークンは、取り消すためにポーリングしたり、取り消しが発生した場合にコールバックを指定したりできます。  
  
```
cancellation_token get_token() const;
```  
  
### <a name="return-value"></a>戻り値  
 このソースに関連付けられたキャンセル トークン。  
  
##  <a name="operator_neq"></a>operator! = 

```
bool operator!= (const cancellation_token_source& _Src) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Src`  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="operator_eq"></a>演算子 = 

```
cancellation_token_source& operator= (const cancellation_token_source& _Src);

cancellation_token_source& operator= (cancellation_token_source&& _Src);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Src`  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="operator_eq_eq"></a>演算子 = = 

```
bool operator== (const cancellation_token_source& _Src) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Src`  
  
### <a name="return-value"></a>戻り値  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)

