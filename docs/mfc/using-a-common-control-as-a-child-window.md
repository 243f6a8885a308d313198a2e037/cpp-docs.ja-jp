---
title: "子ウィンドウとしてのコモン コントロールの使い方 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- controls [MFC], using as child windows
- windows [MFC], common controls as
- child windows [MFC], common controls as
- common controls [MFC], child windows
- Windows common controls [MFC], child windows
ms.assetid: 608f7d47-7854-4fce-bde9-856c51e76753
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 475c769bf09c0693c04780712b85884ae7c48862
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="using-a-common-control-as-a-child-window"></a>子ウィンドウとしてのコモン コントロールの使い方
Windows コモン コントロールのいずれかは、その他のウィンドウの子ウィンドウとして使用できます。 次の手順では、共通のコントロールを動的に作成し、操作する方法について説明します。  
  
### <a name="to-use-a-common-control-as-a-child-window"></a>子ウィンドウとしてのコモン コントロールを使用するには  
  
1.  関連するクラスまたはハンドラーのコントロールを定義します。  
  
2.  コントロールの上書きを使用して、 [cwnd::create](../mfc/reference/cwnd-class.md#create)メソッドを Windows のコントロールを作成します。  
  
3.  コントロールが作成された後 (として事前、`OnCreate`ハンドラー場合サブクラス コントロール)、そのメンバー関数を使用して、コントロールを操作することができます。 個々 のコントロールの説明を参照してください[コントロール](../mfc/controls-mfc.md)メソッドの詳細。  
  
4.  コントロールが終了したらを使用して[に](../mfc/reference/cwnd-class.md#destroywindow)コントロールを破棄します。  
  
## <a name="see-also"></a>参照  
 [作成方法とコントロールの使用](../mfc/making-and-using-controls.md)   
 [コントロール](../mfc/controls-mfc.md)

