---
title: "集計 |Microsoft ドキュメント"
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
- aggregation [C++]
- aggregate objects [C++]
ms.assetid: 7125bb8e-b269-4b50-9bba-295b467a54cc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8dbb0332bc7e55464e5b8af9d0b57e236f23dc86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="aggregation"></a>集約
ときにオブジェクトを実装には、構築済みの別のオブジェクトによって提供されるサービスの利用もあります。 さらに、この 2 番目のオブジェクトが最初の一部として表示されることと思います。 COM ではどちらも包含構造と集計をこれらの目標のです。  
  
 集計では、親 (外部) オブジェクトの作成プロセスの一部として含まれている (内部) オブジェクトを作成して、内部オブジェクトのインターフェイスが、外側によって公開されていることを示します。 オブジェクトをそれ自体にするか、集計可能ではできます。 場合は、集計正常に動作するための特定のルールを従う必要があります。  
  
 主に、すべて**IUnknown**親オブジェクトに含まれているオブジェクトに対するメソッド呼び出しを委任する必要があります。  
  
## <a name="see-also"></a>参照  
 [COM の概要](../atl/introduction-to-com.md)   
 [オブジェクトを再利用](http://msdn.microsoft.com/library/windows/desktop/ms678443)

