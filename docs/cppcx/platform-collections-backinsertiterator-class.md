---
title: Platform::Collections::BackInsertIterator クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::BackInsertIterator::BackInsertIterator
dev_langs:
- C++
helpviewer_keywords:
- BackInsertIterator Class
ms.assetid: aecee1ff-100d-4129-b84b-1966f0923dbf
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d0be32b550cd0e19facb127ca6a052b03ef1eaf5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090019"
---
# <a name="platformcollectionsbackinsertiterator-class"></a>Platform::Collections::BackInsertIterator クラス
要素を上書きするのではなく、シーケンシャル コレクションの末尾に要素を挿入する反復子を表します。  
  
## <a name="syntax"></a>構文  
  
```  
template <typename T>  
class BackInsertIterator : 
public ::std::iterator<::std::output_iterator_tag, void, void, void, void>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 現在のコレクション内の項目の型。  
  
### <a name="remarks"></a>コメント  
 BackInsertIterator クラスは、 [back_insert_iterator Class](../standard-library/back-insert-iterator-class.md)が要求する規則を実装します。  
  
### <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[BackInsertIterator::BackInsertIterator](#ctor)|BackInsertIterator クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[BackInsertIterator::operator* 演算子](#operator-dereference)|現在の BackInsertIterator への参照を取得します。|  
|[BackInsertIterator::operator++ 演算子](#operator-increment)|現在の BackInsertIterator への参照を返します。 反復子は変更されません。|  
|[BackInsertIterator::operator= 演算子](#operator-assign)|指定されたオブジェクトを、現在のシーケンシャル コレクションの末尾に追加します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `BackInsertIterator`  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform::Collections  
  
---
## <a name="ctor"></a>  Backinsertiterator::backinsertiterator コンス トラクター
`BackInsertIterator` クラスの新しいインスタンスを初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
  
explicit BackInsertIterator(  
   Windows::Foundation::Collections::IVector<T>^ v);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `v`  
 IVector\<T > オブジェクト。  
  
### <a name="remarks"></a>コメント  
 `BackInsertIterator` は、`v` パラメーターで指定されたオブジェクトの最後の要素の後に要素を挿入します。  
 
## <a name="operator-assign"></a>  Backinsertiterator::operator = 演算子
指定されたオブジェクトを、現在のシーケンシャル コレクションの末尾に追加します。  
  
## <a name="syntax"></a>構文  
  
```    
BackInsertIterator& operator=( const T& t);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `t`  
 現在のコレクションに追加するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 現在の BackInsertIterator への参照。  

## <a name="operator-dereference"></a>  Backinsertiterator::operator * 演算子
現在の BackInsertIterator への参照を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
BackInsertIterator& operator*();  
```  
  
### <a name="return-value"></a>戻り値  
 現在の BackInsertIterator への参照。  
  
### <a name="remarks"></a>コメント  
 この演算子は、現在のコレクション内の要素ではなく、現在の BackInsertIterator への参照を返します。  
 
## <a name="operator-increment"></a>  Backinsertiterator::operator++ 演算子
現在の BackInsertIterator への参照を返します。 反復子は変更されません。  
  
## <a name="syntax"></a>構文  
  
``` 
  
BackInsertIterator& operator++();  
  
BackInsertIterator operator++(int);  
```  
  
### <a name="return-value"></a>戻り値  
 現在の BackInsertIterator への参照。  
  
### <a name="remarks"></a>コメント  
 仕様では、最初の構文は現在の BackInsertIterator に前置インクリメント演算を行い、2 つ目の構文は現在の BackInsertIterator に後置インクリメント演算を行います。 2 つ目の構文の `int` 型は、実際の整数オペランドではなく後置インクリメント演算を示します。  
  
 ただし、この演算子は実際には BackInsertIterator を変更しません。 代わりに、この演算子は変更されていない現在の反復子への参照を返します。 これと同じ動作[演算子 *](#dereference-operator)です。  
  
  
## <a name="see-also"></a>関連項目  
 [プラットフォーム Namespace](platform-namespace-c-cx.md)