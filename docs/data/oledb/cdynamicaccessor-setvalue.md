---
title: "Cdynamicaccessor::setvalue |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDynamicAccessor.SetValue
- ATL::CDynamicAccessor::SetValue
- ATL::CDynamicAccessor::SetValue<ctype>
- CDynamicAccessor.SetValue
- ATL.CDynamicAccessor.SetValue<ctype>
- CDynamicAccessor::SetValue
- CDynamicAccessor::SetValue<ctype>
dev_langs:
- C++
helpviewer_keywords:
- SetValue method
ms.assetid: ecc18850-96e5-4845-abe5-ab34ad467238
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2227564d321ca3c5c590c11fca52b906ebc911ca
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="cdynamicaccessorsetvalue"></a>CDynamicAccessor::SetValue
指定された列にデータを格納します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template <class ctype>
bool SetValue(   
   DBORDINAL nColumn,   
   constctype& data) throw( );  

template <class ctype>    
bool SetValue(   
   const CHAR * pColumnName,   
   const ctype& data) throw( );  

template <class ctype>   
bool SetValue(  
   const WCHAR *pColumnName,  
   const ctype& data) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ctype`  
 [in]文字列型を除く任意のデータ型を処理するテンプレート パラメーター (**CHAR\***、 **WCHAR\***)、特別な処理を必要とします。 `GetValue` ここでの指定に基づいて適切なデータ型を使用します。  
  
 `pColumnName`  
 [in]列名を含む文字列へのポインター。  
  
 `data`  
 [in]データを含むメモリへのポインター。  
  
 `nColumn`  
 [in]列番号。 列番号は、1 から始まります。 値 0 は、存在する場合に、ブックマーク列を参照します。  
  
## <a name="return-value"></a>戻り値  
 文字列データを設定する場合は、template 宣言されていないバージョンを使用して`GetValue`です。 このメソッドの template 宣言されていないバージョンを返す**void\***、指定された列のデータを格納しているバッファーの一部を指しています。 返します**NULL**列が見つからない場合。  
  
 その他のすべてのデータ型は、テンプレート化されたバージョンを使用する方が簡単`GetValue`です。 テンプレート化されたバージョンを返す**true**成功した場合または**false**エラー発生時にします。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)