---
title: "Platform::stringreference クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::StringReference::StringReference
- VCCORLIB/Platform::StringReference::Data
- VCCORLIB/Platform::StringReference::Length
- VCCORLIB/Platform::StringReference::GetHSTRING
- VCCORLIB/Platform::StringReference::GetString
dev_langs:
- C++
ms.assetid: 2d09c7ec-0f16-458e-83ed-7225a1b9221e
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c23960e392f39c44a57176e4afb81999783bad6c
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="platformstringreference-class"></a>Platform::StringReference クラス
最小のコピー操作で `Platform::String^` 入力パラメーターから他のメソッドに文字列データを渡すために使用できる最適化の手法です。  
  
## <a name="syntax"></a>構文  
  
```cpp  
class StringReference  
```  
  
### <a name="remarks"></a>コメント  
  
### <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[StringReference::StringReference](#ctor)|`StringReference`のインスタンスを作成するための 2 つのコンストラクター。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[StringReference::Data](#data)|文字列データを char16 値の配列として返します。|  
|[StringReference::Length](#length)|文字列内の文字数を返します。|  
|[StringReference::GetHSTRING](#gethstring)|文字列データを HSTRING として返します。|  
|[StringReference::GetString](#getstring)|文字列データを `Platform::String^`として返します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[StringReference::operator=](#operator-assign)|`StringReference` を新しい `StringReference` インスタンスに割り当てます。|  
|[StringReference::operator()](#operator-call)|`StringReference` を `Platform::String^`に変換します。|  
  
### <a name="requirements"></a>必要条件  
 **クライアントがサポートされる最小:** Windows 8  
  
 **サポートされているサーバーの最小値:** Windows Server 2012  
  
 **名前空間:** Platform  
  
 **ヘッダー:** vccorlib.h  

## <a name="data"></a>  Stringreference::data メソッド
この内容を返します`StringReference`char16 値の配列として。  
  
### <a name="syntax"></a>構文  
  
```cpp  
const ::default::char16 * Data() const  
```  
  
### <a name="return-value"></a>戻り値  
 char16 UNICODE テキスト文字の配列。  
  


## <a name="gethstring"></a>  Stringreference::gethstring メソッド
`__abi_HSTRING` として文字列の内容を返します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
__abi_HSTRING GetHSTRING() const  
  
```  
  
### <a name="return-value"></a>戻り値  
 文字列データを格納する `__abi_HSTRING`。  
  
### <a name="remarks"></a>コメント  
  


## <a name="getstring"></a>  Stringreference::getstring メソッド
`Platform::String^` として文字列の内容を返します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
__declspec(no_release_return) __declspec(no_refcount)  
    ::Platform::String^ GetString() const  
```  
  
### <a name="return-value"></a>戻り値  
 文字列データを格納する `Platform::String^`。  

## <a name="length"></a>  Stringreference::length メソッド
文字列内の文字数を返します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
unsigned int Length() const  
```  
  
### <a name="return-value"></a>戻り値  
 文字列の文字数を指定する符号なし整数。  
  
### <a name="remarks"></a>コメント  
  


## <a name="operator-assign"></a>  StringReference::operator = 演算子
指定されたオブジェクトを現在の `StringReference` オブジェクトに割り当てます。  
  
### <a name="syntax"></a>構文  
  
```cpp  
StringReference& operator=(const StringReference& __fstrArg);  
StringReference& operator=(const ::default::char16* __strArg);    
```  
  
### <a name="parameters"></a>パラメーター  
 `__fstrArg`  
 現在の `StringReference` オブジェクトを初期化するために使用される、`StringReference` オブジェクトのアドレス。  
  
 `__strArg`  
 現在の `StringReference` オブジェクトを初期化するために使用される char16 値の配列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 `StringReference` 型のオブジェクトへの参照。  
  
### <a name="remarks"></a>コメント  
 `StringReference`は標準の C++ クラスと ref クラスではなく、それがない、**オブジェクト ブラウザー**です。  
  


## <a name="operator-call"></a>  Stringreference::operator() 演算子
`StringReference` オブジェクトを `Platform::String^` オブジェクトに変換します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
  
__declspec(no_release_return) __declspec(no_refcount)  
         operator ::Platform::String^() const  
  
```  
  
### <a name="return-value"></a>戻り値  
 `Platform::String` 型のオブジェクトへのハンドル。  

## <a name="ctor"></a>  StringReference::StringReference コンストラクター
`StringReference` クラスの新しいインスタンスを初期化します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
  
    StringReference();  
  
   StringReference(const StringReference& __fstrArg)  
  
StringReference(const ::default::char16* __strArg)  
  
StringReference(const ::default::char16* __strArg, size_t __lenArg)  
```  
  
### <a name="parameters"></a>パラメーター  
 `__fstrArg`  
 新しいインスタンスを初期化するためにデータが使用される `StringReference`。  
  
 `__strArg`  
 新しいインスタンスを初期化するために使用される char16 値の配列へのポインター。  
  
 `__lenArg`  
 `__strArg` にある要素の数。  
  
### <a name="remarks"></a>コメント  
 このコンストラクターの最初のバージョンは、既定のコンストラクターです。 2 番目のバージョンは、`StringReference` パラメーターで指定されたオブジェクトから新しい `__fstrArg` インスタンス クラスを初期化します。 3 番目と 4 番目のオーバー ロードは、新しい初期化`StringReference`char16 値の配列からのインスタンス。 char16 は、16 ビット UNICODE テキスト文字を表します。  
  


  
## <a name="see-also"></a>参照  
 [Platform::StringReference クラス](../cppcx/platform-stringreference-class.md)