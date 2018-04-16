---
title: "プログレス コントロールの設定 |Microsoft ドキュメント"
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
- CProgressCtrl class [MFC], settings
- progress controls [MFC], settings
ms.assetid: f4616e91-74fa-4000-ba0d-d3ddc0ee075b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1ad62f3a60c8fe4fcd7efdde7f69f5c5e9450d14
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="settings-for-the-progress-control"></a>プログレス コントロールの設定
プログレス コントロールの基本設定 ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)) は、範囲と現在の位置。 範囲は、操作の全体の時間を表します。 現在の位置では、アプリケーションが加えた操作の完了に向けた進行状況を表します。 範囲または位置への変更が発生する進行状況コントロール自体を再描画をします。  
  
 既定では、範囲が設定されて 0 - 100、および最初の位置が 0 に設定します。 プログレス コントロールの現在の範囲の設定を取得するを使用して、 [GetRange](../mfc/reference/cprogressctrl-class.md#getrange)メンバー関数。 範囲を変更するには、使用、 [SetRange](../mfc/reference/cprogressctrl-class.md#setrange)メンバー関数。  
  
 位置を設定するには、使用[SetPos](../mfc/reference/cprogressctrl-class.md#setpos)です。 新しい値を指定せず、現在の位置を取得する[GetPos](../mfc/reference/cprogressctrl-class.md#getpos)です。 たとえば、現在の操作の状態を簡単にことができます。  
  
 プログレス コントロールの現在の位置をステップを使用して[StepIt](../mfc/reference/cprogressctrl-class.md#stepit)です。 各手順の量を設定するには、使用[SetStep](../mfc/reference/cprogressctrl-class.md#setstep)  
  
## <a name="see-also"></a>参照  
 [CProgressCtrl の使い方](../mfc/using-cprogressctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

