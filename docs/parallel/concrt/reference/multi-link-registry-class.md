---
title: "multi_link_registry クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- multi_link_registry
- AGENTS/concurrency::multi_link_registry
- AGENTS/concurrency::multi_link_registry::multi_link_registry
- AGENTS/concurrency::multi_link_registry::add
- AGENTS/concurrency::multi_link_registry::begin
- AGENTS/concurrency::multi_link_registry::contains
- AGENTS/concurrency::multi_link_registry::count
- AGENTS/concurrency::multi_link_registry::remove
- AGENTS/concurrency::multi_link_registry::set_bound
dev_langs: C++
helpviewer_keywords: multi_link_registry class
ms.assetid: b2aa73a8-e8a6-4255-b117-d07530c328b2
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c5d95a98d56ea666ed823f3caef2190dea1591cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="multilinkregistry-class"></a>multi_link_registry クラス
`multi_link_registry` オブジェクトは、複数のソース ブロックまたは複数のターゲット ブロックを管理する `network_link_registry` です。  
  
## <a name="syntax"></a>構文  
  
```
template<class _Block>
class multi_link_registry : public network_link_registry<_Block>;
```  
  
#### <a name="parameters"></a>パラメーター  
 `_Block`  
 ブロックのデータ型に格納されている、`multi_link_registry`オブジェクト。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[multi_link_registry](#ctor)|`multi_link_registry` オブジェクトを構築します。|  
|[~ multi_link_registry デストラクター](#dtor)|`multi_link_registry` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[add](#add)|リンクを追加、`multi_link_registry`オブジェクト。 (上書き[network_link_registry::add](network-link-registry-class.md#add))。|  
|[begin](#begin)|最初の要素を指す反復子を返します、`multi_link_registry`オブジェクト。 (上書き[network_link_registry::begin](network-link-registry-class.md#begin))。|  
|[含まれています](#contains)|検索、`multi_link_registry`の指定されたブロックのオブジェクト。 (上書き[network_link_registry::contains](network-link-registry-class.md#contains))。|  
|[count](#count)|内の項目の数をカウント、`multi_link_registry`オブジェクト。 (上書き[network_link_registry::count](network-link-registry-class.md#count))。|  
|[remove](#remove)|リンクを削除、`multi_link_registry`オブジェクト。 (上書き[network_link_registry::remove](network-link-registry-class.md#remove))。|  
|[set_bound](#set_bound)|リンクの数に上限を設定、`multi_link_registry`オブジェクトを保持できます。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [network_link_registry](network-link-registry-class.md)  
  
 `multi_link_registry`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="add"></a>追加 

 リンクを追加、`multi_link_registry`オブジェクト。  
  
```
virtual void add(_EType _Link);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Link`  
 追加されるブロックへのポインター。  
  
### <a name="remarks"></a>コメント  
 メソッドをスロー、 [invalid_link_target](invalid-link-target-class.md)例外リンクは既に、レジストリに存在する場合、または場合、バインドは既に設定されてと、`set_bound`関数とのリンクは削除されました。  
  
##  <a name="begin"></a>開始 

 最初の要素を指す反復子を返します、`multi_link_registry`オブジェクト。  
  
```
virtual iterator begin();
```  
  
### <a name="return-value"></a>戻り値  
 最初の要素を指定する反復子、`multi_link_registry`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 最終の状態がによって示される、`NULL`リンクします。  
  
##  <a name="contains"></a>含まれています 

 検索、`multi_link_registry`の指定されたブロックのオブジェクト。  
  
```
virtual bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Link`  
 内で検索するのには、ブロックへのポインター、`multi_link_registry`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `true`指定されたブロックが見つかった場合は`false`それ以外の場合。  
  
##  <a name="count"></a>カウント 

 内の項目の数をカウント、`multi_link_registry`オブジェクト。  
  
```
virtual size_t count();
```  
  
### <a name="return-value"></a>戻り値  
 内の項目数、`multi_link_registry`オブジェクト。  
  
##  <a name="ctor"></a>multi_link_registry 

 `multi_link_registry` オブジェクトを構築します。  
  
```
multi_link_registry();
```  
  
##  <a name="dtor"></a>~ multi_link_registry 

 `multi_link_registry` オブジェクトを破棄します。  
  
```
virtual ~multi_link_registry();
```  
  
### <a name="remarks"></a>コメント  
 メソッドをスロー、 [invalid_operation](invalid-operation-class.md)すべてのリンクが削除される前に呼び出された場合は例外です。  
  
##  <a name="remove"></a>削除します。 

 リンクを削除、`multi_link_registry`オブジェクト。  
  
```
virtual bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Link`  
 削除する場合はブロックへのポインターが見つかりました。  
  
### <a name="return-value"></a>戻り値  
 `true`リンクが検出され、削除、`false`それ以外の場合。  
  
##  <a name="set_bound"></a>set_bound 

 リンクの数に上限を設定、`multi_link_registry`オブジェクトを保持できます。  
  
```
void set_bound(size_t _MaxLinks);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MaxLinks`  
 最大数をリンクする、`multi_link_registry`オブジェクトを保持できます。  
  
### <a name="remarks"></a>コメント  
 制限を設定すると、エントリのリンクを解除するとが、`multi_link_registry`オブジェクト不変の状態を入力する場所への呼び出しをさらに`add`がスローされます、`invalid_link_target`例外。  
  
## <a name="see-also"></a>参照  
 [同時実行 Namespace](concurrency-namespace.md)   
 [single_link_registry クラス](single-link-registry-class.md)
