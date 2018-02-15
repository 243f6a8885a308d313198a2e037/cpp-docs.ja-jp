---
title: "ウィザードを使用しないコンシューマーの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumers, creating
ms.assetid: e8241cfe-5faf-48f8-9de3-241203de020b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a61de0a4621f6f9387da23093f9f450749129ac3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="creating-a-consumer-without-using-a-wizard"></a>ウィザードを使用しないコンシューマーの作成
次の例では、既存の ATL プロジェクトに OLE DB コンシューマーのサポートを追加することを前提としています。 MFC アプリケーションに OLE DB コンシューマーのサポートを追加するには、必要なすべてのサポートを作成し、アプリケーションを実行するために必要な MFC ルーチンを呼び出します MFC アプリケーション ウィザードを実行する必要があります。  
  
 ATL OLE DB コンシューマー ウィザードを使用せずには、OLE DB コンシューマーのサポートを追加。  
  
-   Stdafx.h ファイルに次の文字列を`#include`ステートメント。  
  
    ```  
    #include <atlbase.h>  
    #include <atldbcli.h>  
    #include <atldbsch.h> // if you are using schema templates  
    ```  
  
 プログラムでは、コンシューマーでは、通常次の操作手順を実行します。  
  
-   ローカル変数に列をバインドするユーザー レコード クラスを作成します。 この例では`CMyTableNameAccessor`、ユーザー レコード クラスは、(を参照してください[ユーザー レコード](../../data/oledb/user-records.md))。 このクラスには、列のマップおよびパラメーター マップが含まれています。 列マップで指定したフィールドごとに、ユーザー レコード クラスのデータ メンバーを宣言します。これらのデータ メンバーのそれぞれについてもに、ステータスのデータ メンバーと長さのデータ メンバーを宣言します。 詳細については、次を参照してください。[ウィザードで生成されたアクセサーのフィールド ステータス データ メンバー](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md)です。  
  
    > [!NOTE]
    >  独自のコンシューマーを作成する場合、ステータスや長さ変数より前に、データ変数を引き起こすことがあります。  
  
-   データ ソースとセッションのインスタンスを作成します。 使用して、行セットを使用して、インスタンス化しアクセサーと行セットの種類を決定[CCommand](../../data/oledb/ccommand-class.md)または[CTable](../../data/oledb/ctable-class.md):  
  
    ```  
    CDataSource ds;  
    CSession ss;  
    class CMyTableName : public CCommand<CAccessor<CMyTableNameAccessor>>  
    ```  
  
-   呼び出す**CoInitialize** COM を初期化するには これは通常、メイン コードで呼び出されます。 例:  
  
    ```  
    HRESULT hr = CoInitialize(NULL);  
    ```  
  
-   呼び出す[cdatasource::open](../../data/oledb/cdatasource-open.md)またはそのバリエーションの 1 つです。  
  
-   データ ソースへの接続を開くセッションを開き、および行セットを初期化 (を開き場合、コマンドも実行)。  
  
    ```  
    hr = ds.Open();  
    hr = ss.Open(ds);  
    hr = rs.Open();            // (Open also executes the command)  
    ```  
  
-   必要に応じて、行セット プロパティの設定を使用して`CDBPropSet::AddProperty`をパラメーターとして渡すと`rs.Open`です。 これを行う方法の例を参照してくださいで GetRowsetProperties[コンシューマー メソッド](../../data/oledb/consumer-wizard-generated-methods.md)です。  
  
-   データの取得や操作に行セットを使えるようになりました。  
  
-   アプリケーションが完了すると、接続、セッション、および行セットを閉じます。  
  
    ```  
    rs.Close();  
    ss.Close();  
    ds.Close();  
    ```  
  
     コマンドを使用している場合に呼び出す`ReleaseCommand`後**閉じる**です。 コード例で[ccommand::close](../../data/oledb/ccommand-close.md)を呼び出す方法を示しています。**閉じる**と`ReleaseCommand`です。  
  
-   呼び出す**CoUnInitialize** COM. の初期化を解除するには これは通常、メイン コードで呼び出されます。  
  
    ```  
    CoUninitialize();  
    ```  
  
## <a name="see-also"></a>参照  
 [OLE DB コンシューマーの作成](../../data/oledb/creating-an-ole-db-consumer.md)