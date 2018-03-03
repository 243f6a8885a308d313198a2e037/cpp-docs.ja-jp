---
title: "日付型 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- DATE
dev_langs:
- C++
helpviewer_keywords:
- Date data type, implementing
- Date data type
- DATE type
- Date data type, about Date data type
- MFC, date and time
- hour values representation
ms.assetid: 695853ed-b614-4575-b793-b8c287372038
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f1ed7eb2b467fd52545f65f98b87e8e34ad71f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="date-type"></a>日付型
**日付**8 バイト浮動小数点数を使用して型を実装します。 日付は 1899 年 12 月 30 日午前 0 時 0 時から始まる整数値の増分で表されます。 時間の値は、数値の小数部の絶対値として表されます。 次に示すいくつかの日付と共に、**日付**数値と同等の型。  
  
|日付と時刻|表現|  
|-------------------|--------------------|  
|1899 年 12 月 30日午前 0 時|0.00|  
|1900 年 1 月 1日午前 0 時|2.00|  
|1900 年 1 月 4日午前 0 時|5.00|  
|1900 年 1 月 4日午前 6 時|5.25|  
|1900 年 1 月 4日正午|5.50|  
|1900 年 1 月 4日午後 9|5.875|  
  
 **日付**データ型、だけでなく`COleDateTime`クラスを表す日付と時刻、クラシックの数の行として。 `COleDateTime`クラスには、その他の一般的な日付形式との間の変換などの日付の値を操作するためのいくつかのメソッドが含まれています。  
  
 Automation でこれらの日付と時刻の形式を使用する場合は、次の点を注意してください。  
  
-   日付は現地時刻で指定します。同期は、異なるタイム ゾーンの日付を使用する場合、手動で実行する必要があります。  
  
-   日付型は、夏時間には考慮されません。  
  
-   日付の時系列になります (1899 年 12 月 30日) の前に 0 未満の日付値を連続していません。 これは、日付値の整数部分は、小数部分を処理中に、符号付きとして扱われるために、符号なしとします。 つまり、日付値の整数部分があります正または負の場合、日付の値の小数部は常に、全体的な論理的な日付に追加中にします。 次の表は、いくつかの例を示しています。  
  
|日付と時刻|表現|  
|-------------------|--------------------|  
|1899 年 12 月 27日午前 0 時|-3.00|  
|1899 年 12 月 28日正午|-2.50|  
|1899 年 12 月 28日午前 0 時|-2.00|  
|1899 年 12 月 29日午前 0 時|-1.00|  
|1899 年 12 月 30日午後 6 時|-0.75|  
|1899 年 12 月 30日正午|-0.50|  
|1899 年 12 月 30日午前 6 時|-0.25|  
|1899 年 12 月 30日午前 0 時|0.00|  
|1899 年 12 月 30日午前 6 時|0.25|  
|1899 年 12 月 30日正午|0.50|  
|1899 年 12 月 30日午後 6 時|0.75|  
|1899 年 12 月 31日午前 0 時|1.00|  
|1900 年 1 月 1日午前 0 時|2.00|  
|1900 年 1 月 1日正午|2.50|  
|1900 年 1 月 2日午前 0 時|3.00|  
  
> [!CAUTION]
>  6時 00分 AM がかどうかを 1 日を表す整数が正の値 (1899 年 12 月 30 日) の後に関係なく、小数部の値 0.25 で表される常にまたは負の値 (1899 年 12 月 30 日) の前に、単純な浮動ポイントの比較が誤って並べ替えために注意してください。任意**日付**として 12/30/1899 より前の日に 6時 00分 AM を表す*後*よりも、**日付**同じ日に 7時 00分 AM を表すです。  
  
 関連する問題の詳細について、**日付**と`COleDateTime`型見つかります[COleDateTime クラス](../atl-mfc-shared/reference/coledatetime-class.md)と[日付と時刻: オートメーションのサポート](../atl-mfc-shared/date-and-time-automation-support.md)です。  
  
## <a name="see-also"></a>参照  
 [日付と時刻](../atl-mfc-shared/date-and-time.md)   
 [COleDateTime クラス](../atl-mfc-shared/reference/coledatetime-class.md)

