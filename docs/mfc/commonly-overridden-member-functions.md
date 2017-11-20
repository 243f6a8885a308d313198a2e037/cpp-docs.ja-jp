---
title: "通常オーバーライドされるメンバー関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CDialog class [MFC], members
- OnInitDialog function
- dialog classes [MFC], commonly overridden member functions
- OnCancel function
- overriding, dialog class members
- OnOK function
- MFC dialog boxes [MFC], overriding member functions
ms.assetid: 78eb566c-e361-4c86-8db5-c7e2791b249a
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1b5c5c4d5689c57f02766f2d6c2af2ddad88ee1e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="commonly-overridden-member-functions"></a>通常オーバーライドされるメンバー関数
次の表のほとんどの場合でオーバーライドされるメンバー関数、 `CDialog`-クラスを派生します。  
  
### <a name="commonly-overridden-member-functions-of-class-cdialog"></a>通常オーバーライドされるクラス CDialog のメンバー関数  
  
|メンバー関数|メッセージに応答します。|オーバーライドの目的|  
|---------------------|----------------------------|-----------------------------|  
|`OnInitDialog`|**WM_INITDIALOG**|ダイアログ ボックスのコントロールを初期化します。|  
|`OnOK`|**BN_CLICKED**ボタンの**IDOK**|ユーザーが [ok] ボタンをクリックしたときに応答します。|  
|`OnCancel`|**BN_CLICKED**ボタンの**IDCANCEL**|ユーザーは [キャンセル] ボタンをクリックしたときに応答します。|  
  
 `OnInitDialog`、 `OnOK`、および`OnCancel`仮想関数。 これらをオーバーライドする派生ダイアログ クラスを使用して、オーバーライドする関数を宣言する、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。  
  
 `OnInitDialog`ダイアログ ボックスが表示される直前に呼び出されます。 既定値を呼び出す必要があります`OnInitDialog`オーバーライドからハンドラー-通常は、ハンドラーの最初のアクションとして。 既定では、`OnInitDialog`返します**TRUE**  ダイアログ ボックスで、最初のコントロールにフォーカスを設定する必要がありますを指定します。  
  
 `OnOK`通常、モードレスがないモーダル ダイアログ ボックスのオーバーライドされます。 モーダル ダイアログ ボックスのこのハンドラーをオーバーライドする場合は、オーバーライドから基底クラスのバージョンを呼び出す — ことを確認する`EndDialog`が呼び出された-呼び出しまたは`EndDialog`自分でします。  
  
 `OnCancel`通常、モードレス ダイアログ ボックスをオーバーライドします。  
  
 これらのメンバー関数の詳細については、クラスを参照してください。 [CDialog](../mfc/reference/cdialog-class.md)で、 *『 MFC リファレンス*とのディスカッション[ ダイアログ ボックスのライフ サイクル](../mfc/life-cycle-of-a-dialog-box.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックス](../mfc/dialog-boxes.md)   
 [通常追加されるメンバー関数](../mfc/commonly-added-member-functions.md)
