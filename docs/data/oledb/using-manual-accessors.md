---
title: "手動アクセサーの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- command handling, OLE DB Templates
- manual accessors
- accessors [C++], manual
ms.assetid: 29f00a89-0240-482b-8413-4120b9644672
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e7d6bd8f0228103e4899e6bc24f6d67af0f3fdb4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="using-manual-accessors"></a>手動アクセサーの使用
不明なコマンドを処理する場合は 4 つの点があります。  
  
-   パラメーターを確認します。  
  
-   コマンドを実行します。  
  
-   出力列を決定します  
  
-   複数の戻り値の行セットがあるかを参照してください。  
  
 そのためには、OLE DB コンシューマー テンプレートを使用して、`CManualAccessor`クラスし、これらの手順に従います。  
  
1.  開く、`CCommand`オブジェクト`CManualAccessor`テンプレート パラメーターとして。  
  
    ```  
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;  
    ```  
  
2.  クエリのセッション、 **IDBSchemaRowset**インターフェイスし、プロシージャのパラメーター行セットを使用します。 場合、 **IDBSchemaRowset**インターフェイスが使用できないクエリを実行、`ICommandWithParameters`インターフェイスです。 呼び出す`GetParameterInfo`についてです。 どちらのインターフェイスを使用できる場合は、パラメーターがないと見なすことができます。  
  
3.  各パラメーターでは、呼び出す`AddParameterEntry`パラメーターを追加して、それらの設定にします。  
  
4.  行セットを開くことは、バインド パラメーターに設定**false**です。  
  
5.  呼び出す`GetColumnInfo`を出力列を取得します。 使用して`AddBindEntry`バインドに出力列を追加します。  
  
6.  呼び出す`GetNextResult`複数行セットが使用可能なかどうかを判断します。 手順 2. ~ 5. を繰り返します。  
  
 手動アクセサーの例は、次を参照してください。 **CDBListView::CallProcedure**で、 [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832)サンプルです。  
  
## <a name="see-also"></a>参照  
 [アクセサーの使用](../../data/oledb/using-accessors.md)