---
title: ツール バー コントロールのスタイル |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ToolBar control styles [MFC]
ms.assetid: 0f717eb9-fa32-4263-b852-809238863feb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 35b5b87944f2b0f9ce78adbe42b59d92b98a6e5a
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885836"
---
# <a name="toolbar-control-styles"></a>ツール バー コントロールのスタイル
[CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)がボタンの動作と外観を決定するスタイル フラグのセット。 これらのフラグの組み合わせを設定するには呼び出すことによって[CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle)します。 このトピックでは、スタイル フラグの値とその意味を示します。  
  
## <a name="property-values"></a>プロパティの値  
 次の値は、コントロールを表すボタンの種類を決定します。  
  
 TBBS_BUTTON  
 標準プッシュ ボタン (既定値)。  
  
 TBBS_CHECKBOX  
 チェック ボックスです。  
  
 TBBS_CHECKGROUP  
 チェック ボックスの グループの先頭。  
  
 TBBS_GROUP  
 ボタンのグループの開始。  
  
 TBBS_SEPARATOR  
 区切り記号。  
  
 次の値は、コントロールの現在の状態を表します。  
  
 TBBS_CHECKED  
 チェック ボックスをオンします。  
  
 TBBS_DISABLED  
 コントロールが無効です。  
  
 TBBS_INDETERMINATE  
 チェック ボックスは、不定状態では。  
  
 TBBS_PRESSED  
 ボタンが押されました。  
  
 次の値は、ツールバーのボタンのレイアウトを変更します。  
  
 TBBS_BREAK  
 新しい行または新しい列に列を分離することがなく、項目を配置します。  
  
## <a name="remarks"></a>Remarks  
 現在のスタイルが格納されている[CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle)します。 新しい値を設定しないでください`m_nStyle`を直接いくつかの派生クラスを呼び出すときに、追加の処理を実行するため、`SetStyles`します。  
  
 ビジュアル マネージャーでは、各状態にあるボタンの外観を決定します。 参照してください[ビジュアル マネージャー](../../mfc/visualization-manager.md)詳細についてはします。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxtoolbarbutton.h  
  
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)   
 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [ビジュアル マネージャー](../../mfc/visualization-manager.md)


