---
title: CAccessorBase クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CAccessorBase
- CAccessorBase.Close
- CAccessorBase::Close
- GetHAccessor
- CAccessorBase::GetHAccessor
- CAccessorBase.GetHAccessor
- CAccessorBase::GetNumAccessors
- GetNumAccessors
- CAccessorBase.GetNumAccessors
- IsAutoAccessor
- CAccessorBase.IsAutoAccessor
- CAccessorBase::IsAutoAccessor
- CAccessorBase::ReleaseAccessors
- CAccessorBase.ReleaseAccessors
- ReleaseAccessors
dev_langs:
- C++
helpviewer_keywords:
- CAccessorBase class
- Close method
- GetHAccessor method
- GetNumAccessors method
- IsAutoAccessor method
- ReleaseAccessors method
ms.assetid: 389b65be-11ca-4ae0-9290-60c621c4982b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 18199a700cbc5065d987a57cc076a5d0cf670577
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340665"
---
# <a name="caccessorbase-class"></a>CAccessorBase クラス
OLE DB テンプレートのすべてのアクセサーは、このクラスから派生します。 `CAccessorBase` 複数のアクセサーを管理する 1 つの行セットを使用できます。 パラメーターと出力列の両方のバインドも提供します。  
  
## <a name="syntax"></a>構文

```cpp
// Replace with syntax  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[閉じる](#close)|アクセサーを閉じます。|  
|[GetHAccessor](#geth)|アクセサーのハンドルを取得します。|  
|[GetNumAccessors](#getnum)|クラスによって作成されたアクセサーの数を取得します。|  
|[IsAutoAccessor](#isauto)|指定されたアクセサーが自動かどうかをテストします。|  
|[ReleaseAccessors](#release)|アクセサーを解放します。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  

## <a name="close"></a> Caccessorbase::close
アクセサーを閉じます。  
  
### <a name="syntax"></a>構文  
  
```cpp
void Close();  
```  
  
### <a name="remarks"></a>Remarks  
 呼び出す必要があります[ReleaseAccessors](../../data/oledb/caccessorbase-releaseaccessors.md)最初。  

## <a name="geth"></a> Caccessorbase::gethaccessor
指定されたアクセサーのアクセサーのハンドルを取得します。  
  
### <a name="syntax"></a>構文  
  
```cpp
HACCESSOR GetHAccessor(ULONG nAccessor) const;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *nAccessor*  
 [in]アクセサーのゼロ オフセット番号。  
  
### <a name="return-value"></a>戻り値  
 アクセサーのハンドルです。  

## <a name="getnum"></a> Caccessorbase::getnumaccessors
クラスによって作成されたアクセサーの数を取得します。  
  
### <a name="syntax"></a>構文  
  
```cpp
ULONG GetNumAccessors() const;  
```  
  
### <a name="return-value"></a>戻り値  
 クラスによって作成されたアクセサーの数。  

## <a name="isauto"></a> Caccessorbase::isautoaccessor
移動操作中に、アクセサーのデータが自動的に取得される場合に true を返します。  
  
### <a name="syntax"></a>構文  
  
```cpp
bool IsAutoAccessor(ULONG nAccessor) const;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *nAccessor*  
 [in]アクセサーのゼロ オフセット番号。  
  
### <a name="return-value"></a>戻り値  
 返します**true**アクセサーが自動である場合。 それ以外の場合は **false**を返します。  

## <a name="release"></a> Caccessorbase::releaseaccessors
クラスによって作成されたアクセサーを解放します。  
  
### <a name="syntax"></a>構文  
  
```cpp
HRESULT ReleaseAccessors(IUnknown* pUnk);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *pUnk*  
 [in]ポインター、`IUnknown`アクセサーが作成されている COM オブジェクトのインターフェイス。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT です。  
  
### <a name="remarks"></a>Remarks  
 呼び出される[caccessorrowset::close](../../data/oledb/caccessorrowset-close.md)します。 
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessorBase クラス](../../data/oledb/caccessorbase-class.md)