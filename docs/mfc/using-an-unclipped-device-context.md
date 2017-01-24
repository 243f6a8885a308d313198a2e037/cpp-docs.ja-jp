---
title: "クリッピングを行わないデバイス コンテキストの使用 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC ActiveX コントロール, クリッピングを行わないデバイス コンテキスト"
ms.assetid: 9c020063-73da-4803-bf7b-2e1fd950c9ed
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# クリッピングを行わないデバイス コンテキストの使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コントロールは、クライアントの四角形の外側に描画しないことを確実にする場合は、`IntersectClipRect` に `COleControl`による呼び出しを無効にすることにより小さく検出可能な速度の向上を実現できます。  これを行うには、[COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md)によって返されるフラグのセットから **clipPaintDC** フラグを削除します。  たとえば、次のようになります。  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/CPP/using-an-unclipped-device-context_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#14](../mfc/codesnippet/CPP/using-an-unclipped-device-context_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/CPP/using-an-unclipped-device-context_3.cpp)]  
  
 このフラグを削除するコードは自動的にコントロールを MFC ActiveX コントロール ウィザードを作成すると [コントロールの設定](../mfc/reference/control-settings-mfc-activex-control-wizard.md) ページの **クリッピングを行わないデバイス コンテキスト\(U\)** オプションを選択すると生成されます。  
  
 ウィンドウなしでアクティブを使用する場合は、この最適化は無効です。  
  
## 参照  
 [MFC ActiveX コントロール : 最適化](../mfc/mfc-activex-controls-optimization.md)