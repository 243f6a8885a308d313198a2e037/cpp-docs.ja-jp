---
title: "Cdynamicaccessor::getvalue |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetValue
- CDynamicAccessor::GetValue<ctype>
- ATL.CDynamicAccessor.GetValue<ctype>
- CDynamicAccessor.GetValue
- CDynamicAccessor::GetValue
- ATL.CDynamicAccessor.GetValue
- ATL::CDynamicAccessor::GetValue
- ATL::CDynamicAccessor::GetValue<ctype>
dev_langs: C++
helpviewer_keywords: GetValue method
ms.assetid: 553f44af-68bc-4cb6-8774-e0940003fa90
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 131c0ebba0ec271a4a92967f677d237703bb592a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="cdynamicaccessorgetvalue"></a>CDynamicAccessor::GetValue
指定された列のデータを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      void* GetValue(   
   DBORDINAL nColumn    
) const throw( );  
void* GetValue(  
   const CHAR* pColumnName   
) const throw( );  
void* GetValue(  
   const WCHAR* pColumnName   
) const throw( );  
template < class ctype >  
bool GetValue(  
   DBORDINAL nColumn,  
   ctype* pData   
) const throw( );  
template < class ctype >  
bool GetValue(  
   const CHAR* pColumnName,  
   ctype* pData   
) const throw( );  
template < class ctype >  
bool GetValue(  
   const WCHAR* pColumnName,  
   ctype* pData   
) const throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ctype`  
 [in]文字列型を除く任意のデータ型を処理するテンプレート パラメーター (**CHAR\***、 **WCHAR\***)、特別な処理を必要とします。 `GetValue`ここでの指定に基づいて適切なデータ型を使用します。  
  
 `nColumn`  
 [in]列番号。 列番号は、1 から始まります。 値 0 は、存在する場合に、ブックマーク列を参照します。  
  
 `pColumnName`  
 [in]列の名前。  
  
 `pData`  
 [out]指定された列の内容へのポインター。  
  
## <a name="return-value"></a>戻り値  
 文字列データを渡す場合は、template 宣言されていないバージョンを使用して`GetValue`です。 このメソッドの template 宣言されていないバージョンを返す**void\***、指定された列のデータを格納しているバッファーの一部を指しています。 返します**NULL**列が見つからない場合。  
  
 その他のすべてのデータ型は、テンプレート化されたバージョンを使用する方が簡単`GetValue`です。 テンプレート化されたバージョンを返す**true**成功した場合または**false**エラー発生時にします。  
  
## <a name="remarks"></a>コメント  
 Template 宣言されていないバージョンを使用して、文字列およびその他のデータ型を含む列のテンプレート化されたバージョンを含む列を返します。  
  
 デバッグ モードで表示されるアサーション場合のサイズ`pData`が指している列のサイズと等しくないです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)