---
title: "レコード セット: 合計およびその他の集計の結果 (ODBC) を取得する |Microsoft ドキュメント"
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
- SQL, retrieving aggregate values from recordsets
- recordsets, retrieving SQL aggregate values
- retrieving SQL aggregate values from recordsets
- ODBC recordsets, retrieving SQL aggregate values
- SQL aggregate values
- SQL Server projects, retrieving aggregate values from recordsets
- SQL aggregate values, retrieving from recordsets
ms.assetid: 94500662-22a4-443e-82d7-acbe6eca447b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4753193789c95b726a8770cef9a153b041fa762c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-obtaining-sums-and-other-aggregate-results-odbc"></a>レコードセット: 集計値の計算 (ODBC)
このトピックの内容は、MFC ODBC クラスに該当します。  
  
 このトピックの内容を次を使用した集計の結果を取得する方法を説明します[SQL](../../data/odbc/sql.md)キーワード。  
  
-   **合計**数値データ型の列の値の合計を計算します。  
  
-   **MIN**数値データ型の列の最小値を抽出します。  
  
-   **最大**数値データ型の列の最大値を抽出します。  
  
-   **AVG**数値データ型の列のすべての値の平均値を計算します。  
  
-   **カウント**任意のデータ型の列内のレコードの数をカウントします。  
  
 これらの SQL 関数を使用するは、データ ソースからレコードを抽出するのではなく、データ ソース内のレコードに関する統計情報を取得します。 1 つの通常作成されるレコード セットで構成されます (すべての列が場合の集計) レコードを格納している値。 (を使用した場合、複数のレコードにすることがあります、 **GROUP BY**句)。この値は、計算または SQL 関数によって抽出の結果を示します。  
  
> [!TIP]
>  SQL を追加する**GROUP BY**句 (および場合によって、 **HAVING**句)、SQL ステートメントの末尾に追加**か**です。 例:  
  
```  
m_strFilter = "sales > 10 GROUP BY SALESPERSON_ID";  
```  
  
 フィルターおよび並べ替えの列で集計結果を得るために使用するレコードの数を制限することができます。  
  
> [!CAUTION]
>  いくつかの集計演算子は、集計される列から別のデータ型を返します。  
  
-   **合計**と**AVG**次より大きいデータ型を返す場合があります (などで呼び出して`int`を返します**長い**または**二重**)。  
  
-   **カウント**通常返します**長い**ターゲット列の種類に関係なく。  
  
-   **最大**と**MIN**計算列と同じデータ型を返します。  
  
     たとえば、**クラスの追加**ウィザードで作成`long` `m_lSales` Sales 列が、それに合わせて、これを置き換える必要があります、`double m_dblSumSales`集計の結果に対応するデータ メンバーです。 次の例を参照してください。  
  
#### <a name="to-obtain-an-aggregate-result-for-a-recordset"></a>レコード セットの集計結果を取得するには  
  
1.  レコード セットの作成」の説明に従って[MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)集計結果を取得する列を含むです。  
  
2.  変更、 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)レコード セットの関数。 列名を表す文字列を置き換える (の 2 番目の引数、 [RFX](../../data/odbc/record-field-exchange-using-rfx.md)関数呼び出しの) 列の集計関数を表す文字列を使用します。 たとえば、次のように置き換えます。  
  
    ```  
    RFX_Long(pFX, "Sales", m_lSales);  
    ```  
  
     :  
  
    ```  
    RFX_Double(pFX, "Sum(Sales)", m_dblSumSales)  
    ```  
  
3.  レコード セットを開きます。 集計操作の結果のままに`m_dblSumSales`です。  
  
> [!NOTE]
>  ウィザードは、実際には、ハンガリー語プレフィックスなしのデータ メンバー名を割り当てます。 ウィザードは、たとえば、 `m_Sales` Sales 列ではなく、`m_lSales`前の図に使用する名前。  
  
 使用している場合、 [CRecordView](../../mfc/reference/crecordview-class.md)クラスのデータを表示する、新しいデータ メンバー値を表示する、DDX 関数の呼び出しを変更する必要がここでは、変更することから。  
  
```  
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_lSales, m_pSet);  
```  
  
 移動先:  
  
```  
DDX_FieldText(pDX, IDC_SUMSALES, m_pSet->m_dblSumSales, m_pSet);  
```  
  
## <a name="see-also"></a>参照  
 [レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)   
 [レコードセット: レコード選択のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)