---
title: "行セット オブジェクト インターフェイス |Microsoft ドキュメント"
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
- interfaces, OLE DB
- OLE DB, interfaces
- rowset objects [OLE DB]
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: 0d7a5d48-2fe4-434f-a84b-157c1fdc3494
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 211fb5bbd0a950eff5f954d1c23b3dc993badb0d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="rowset-object-interfaces"></a>行セット オブジェクト インターフェイス
次の表は、行セット オブジェクトの OLE DB で定義されている必須およびオプションのインターフェイスを示します。  
  
|Interface|必須?|OLE DB テンプレートによって実装されるか。|  
|---------------|---------------|--------------------------------------|  
|[IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx)|必須|[はい]|  
|[IColumnsInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx)|必須|[はい]|  
|[IConvertType](https://msdn.microsoft.com/en-us/library/ms715926.aspx)|必須|[はい]|  
|[IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx)|必須|[はい]|  
|[IRowsetInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx)|必須|[はい]|  
|[IChapteredRowset](https://msdn.microsoft.com/en-us/library/ms718180.aspx)|Optional|×|  
|[IColumnsInfo2](https://msdn.microsoft.com/en-us/library/ms712953.aspx)|Optional|×|  
|[IColumnsRowset](https://msdn.microsoft.com/en-us/library/ms722657.aspx)|Optional|×|  
|[IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)|Optional|○ (ATL)|  
|[IDBAsynchStatus](https://msdn.microsoft.com/en-us/library/ms709832.aspx)|Optional|×|  
|[IGetRow](https://msdn.microsoft.com/en-us/library/ms718047.aspx)|Optional|×|  
|[IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx)|Optional|[はい]|  
|[IRowsetChapterMember](https://msdn.microsoft.com/en-us/library/ms725430.aspx)|Optional|×|  
|[IRowsetCurrentIndex](https://msdn.microsoft.com/en-us/library/ms709700.aspx)|Optional|×|  
|[IRowsetFind](https://msdn.microsoft.com/en-us/library/ms724221.aspx)|Optional|×|  
|[IRowsetIdentity](https://msdn.microsoft.com/en-us/library/ms715913.aspx)|省略可能 (ただし、レベル 0 のプロバイダーに必要)|[はい]|  
|[IRowsetIndex](https://msdn.microsoft.com/en-us/library/ms719604.aspx)|Optional|×|  
|[IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx)|Optional|[はい]|  
|[IRowsetRefresh](https://msdn.microsoft.com/en-us/library/ms714892.aspx)|Optional|×|  
|[IRowsetScroll](https://msdn.microsoft.com/en-us/library/ms712984.aspx)|Optional|×|  
|[IRowsetUpdate](https://msdn.microsoft.com/en-us/library/ms714401.aspx)|Optional|[はい]|  
|[IRowsetView](https://msdn.microsoft.com/en-us/library/ms709755.aspx)|Optional|×|  
|[ISupportErrorInfo](https://msdn.microsoft.com/en-us/library/ms715816.aspx)|Optional|[はい]|  
|[IRowsetBookmark](https://msdn.microsoft.com/en-us/library/ms714246.aspx)|Optional|×|  
  
 ウィザードで生成された行セット オブジェクトを実装する`IAccessor`、 `IRowset`、および`IRowsetInfo`継承を使用します。 `IAccessorImpl`両方の出力列をバインドします。 `IRowset`インターフェイス フェッチ行とデータを処理します。 `IRowsetInfo`インターフェイスは、行セット プロパティを処理します。  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)