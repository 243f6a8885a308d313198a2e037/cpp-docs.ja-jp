---
title: "SET_PARAM_TYPE |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SET_PARAM_TYPE
dev_langs: C++
helpviewer_keywords: SET_PARAM_TYPE macro
ms.assetid: 85979070-2d55-4c67-94b1-9b9058babc59
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 024cf67033cdc35917f37c2e6183e60042c40d45
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="setparamtype"></a>SET_PARAM_TYPE
`COLUMN_ENTRY` マクロの後に続く `SET_PARAM_TYPE` マクロが入力、出力、入出力のいずれであるかを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
SET_PARAM_TYPE(  
type  
 )  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `type`  
 [入力] 設定するパラメーターの種類。  
  
## <a name="remarks"></a>コメント  
 プロバイダーは、基になるデータ ソースによってサポートされているパラメーター入出力タイプだけをサポートします。 type は、1 つ以上の **DBPARAMIO** 値の組み合わせです ( [OLE DB プログラマーズ リファレンス](https://msdn.microsoft.com/en-us/library/ms716845.aspx) の「 *DBBINDING Structures (DBBINDING 構造体)*」を参照してください)。  
  
-   **DBPARAMIO_NOTPARAM** アクセサーにパラメーターがありません。 通常、行アクセサーで **eParamIO** をこの値に設定して、パラメーターが無視されることをユーザーに知らせます。  
  
-   **DBPARAMIO_INPUT** 入力パラメーター。  
  
-   **DBPARAMIO_OUTPUT** 出力パラメーター。  
  
-   **DBPARAMIO_INPUT &#124;です。DBPARAMIO_OUTPUT**パラメーターは、入力と出力パラメーターの両方です。  
  
## <a name="example"></a>例  
```cpp  
class CArtistsProperty
{
public:
   short m_nReturn;
   short m_nAge;
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];

BEGIN_PARAM_MAP(CArtistsProperty)
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)
   COLUMN_ENTRY(1, m_nReturn)
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_nAge)
END_PARAM_MAP()

BEGIN_COLUMN_MAP(CArtistsProperty)
   COLUMN_ENTRY(1, m_szFirstName)
   COLUMN_ENTRY(2, m_szLastName)
END_COLUMN_MAP()

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsProperty, L" \
      { ? = SELECT Age FROM Artists WHERE Age < ? }")
};
``` 
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [OLE DB コンシューマー テンプレート用マクロおよびグローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)