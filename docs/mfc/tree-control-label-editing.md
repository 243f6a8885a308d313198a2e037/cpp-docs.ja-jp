---
title: "ツリー コントロールのラベルの編集 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- editing tree control labels
- CTreeCtrl class [MFC], editing labels
- label editing in CTreeCtrl class [MFC]
- tree controls [MFC], label editing
ms.assetid: 6cde2ac3-43ee-468f-bac2-cf1a228ad32d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 03fb11c29b51b30b1aaffccbe3e999f1cefc3fbb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="tree-control-label-editing"></a>ツリー コントロールのラベルの編集
ユーザーは、ツリー コントロールの項目のラベルを直接編集できます ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) を持つ、 **TVS_EDITLABELS**スタイル。 ユーザーは、フォーカスがある項目のラベルをクリックして編集を開始します。 アプリケーションを使用して編集を開始、 [EditLabel](../mfc/reference/ctreectrl-class.md#editlabel)メンバー関数。 ツリー コントロールは、編集するときの通知を開始しがキャンセルまたは完了に送信します。 編集が完了したら、するは、項目のラベルを更新する適切な場合です。  
  
 ラベルの編集が開始した場合、ツリー コントロールの送信、 [TVN_BEGINLABELEDIT](http://msdn.microsoft.com/library/windows/desktop/bb773506)通知メッセージです。 この通知を処理することでは、いくつかのラベルの編集を許可して、他のユーザーの編集できないようにします。 0 を返すことにより、編集、および 0 以外を返すようにします。  
  
 ラベルの編集をキャンセル、または完了時にツリー コントロールの送信、 [TVN_ENDLABELEDIT](http://msdn.microsoft.com/library/windows/desktop/bb773515)通知メッセージです。 `lParam`パラメーターがのアドレス、 [NMTVDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773418)構造体。 **項目**メンバーは、 [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456)構造体を項目を識別し、編集済みのテキストが含まれています。 更新するため、項目のラベル、必要に応じて、おそらく編集済みの文字列を検証した後を担当しています。 **PszText**のメンバー`TV_ITEM`編集がキャンセルされた場合は 0 です。  
  
 ラベルの編集中に、通常への応答、 [TVN_BEGINLABELEDIT](http://msdn.microsoft.com/library/windows/desktop/bb773506)通知メッセージを使用してラベルを編集するために使用される編集コントロールにポインターを取得できます、 [GetEditControl](../mfc/reference/ctreectrl-class.md#geteditcontrol)メンバー関数。 エディット コントロールを呼び出すことができます[SetLimitText](../mfc/reference/cedit-class.md#setlimittext)メンバー関数をユーザーが入力できるテキストまたはサブクラスをインターセプトし、無効な文字を破棄するには、エディット コントロールの量を制限します。 ただし、編集コントロールがのみに表示されている*後* **TVN_BEGINLABELEDIT**が送信されます。  
  
## <a name="see-also"></a>参照  
 [CTreeCtrl の使い方](../mfc/using-ctreectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

