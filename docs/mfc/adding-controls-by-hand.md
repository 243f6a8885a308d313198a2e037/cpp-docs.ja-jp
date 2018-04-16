---
title: "手動でコントロールを追加する |Microsoft ドキュメント"
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
- Windows common controls [MFC], adding
- dialog box controls [MFC], adding to dialog boxes
- controlling input focus
- input focus control
- focus, controlling input [MFC]
- controls [MFC], adding to dialog boxes
- common controls [MFC], adding
ms.assetid: bc843e59-0c51-4b5b-8bf2-343f716469d2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b13f6fdfb3c11819eb8d8838e5617e7a349d1023
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="adding-controls-by-hand"></a>手動でコントロールを追加する方法
か[ダイアログ エディター ダイアログ ボックスにコントロールを追加](../mfc/using-the-dialog-editor-to-add-controls.md)コードで、自分で追加することです。  
  
 コントロール オブジェクトを自分で作成するには、C++ コントロール オブジェクト [C++] ダイアログ ボックスまたはフレーム ウィンドウ オブジェクト通常埋め込むされます。 Framework の他の多くのオブジェクトのようには、コントロールには、2 段階の構築が必要があります。 コントロールを呼び出す必要があります**作成**親ダイアログ ボックスまたはフレーム ウィンドウの作成の一環としてメンバー関数。 ダイアログ ボックスでは、これは、通常[OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)、およびフレーム ウィンドウで[OnCreate](../mfc/reference/cwnd-class.md#oncreate)です。  
  
 次の例は、可能性がありますを宣言する方法を示しています、`CEdit`派生ダイアログ クラスのクラス宣言内のオブジェクトを呼び出す、**作成**メンバー関数内`OnInitDialog`です。 `CEdit`オブジェクトは、埋め込みオブジェクトとして宣言されて、ダイアログ オブジェクトを構築すると、ですが、それ自体で初期化する必要があるときに自動的に構築された**作成**メンバー関数。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#1](../mfc/codesnippet/cpp/adding-controls-by-hand_1.h)]  
  
 次`OnInitDialog`関数は、四角形の設定を呼び出して**作成**を Windows のエディット コントロールを作成し、初期化されていないにアタッチ`CEdit`オブジェクト。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#2](../mfc/codesnippet/cpp/adding-controls-by-hand_2.cpp)]  
  
 エディット オブジェクトを作成すると、設定することできますも入力フォーカス コントロールを呼び出すことによって、`SetFocus`メンバー関数。 0 を返す最後に、`OnInitDialog`フォーカスを設定することを表示します。 0 以外の値を返す場合ダイアログ マネージャーは、ダイアログ ボックスの項目一覧の最初のコントロールの項目にフォーカスを設定します。 ほとんどの場合は、コントロールを追加するダイアログ ボックスにダイアログ エディターを使用します。  
  
## <a name="see-also"></a>参照  
 [作成方法とコントロールの使用](../mfc/making-and-using-controls.md)   
 [コントロール](../mfc/controls-mfc.md)   
 [CDialog::OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)

