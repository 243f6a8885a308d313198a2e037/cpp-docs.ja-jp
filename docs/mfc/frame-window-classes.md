---
title: "フレーム ウィンドウ クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- frame window classes [MFC], about frame window classes
- frame window classes [MFC]
- windows [MFC], MDI
- document frame windows [MFC], classes
- single document interface (SDI), frame windows
- window classes [MFC], frame
- MFC, frame windows
- MDI [MFC], frame windows
- classes [MFC], window
ms.assetid: c27e43a7-8ad0-4759-b1b7-43f4725f4132
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 60f3938042cd42c7b02c12eb4e6316a00783c280
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="frame-window-classes"></a>フレーム ウィンドウ クラス
各アプリケーションには 1 つの「メイン フレーム ウィンドウ」、通常、アプリケーション名がある、キャプションのするデスクトップ ウィンドウです。 各ドキュメントが通常は 1 つは「ドキュメント フレーム ウィンドウです」 ドキュメント フレーム ウィンドウには、ドキュメントのデータを表示するには、少なくとも 1 つのビューが含まれています。  
  
## <a name="frame-windows-in-sdi-and-mdi-applications"></a>SDI と MDI アプリケーションでのフレーム ウィンドウ  
 SDI アプリケーションの場合は、1 つのフレーム ウィンドウ クラスから派生した[CFrameWnd](../mfc/reference/cframewnd-class.md)です。 このウィンドウは、メイン フレーム ウィンドウとドキュメント フレーム ウィンドウの両方には。 MDI アプリケーションは、メイン フレーム ウィンドウ クラスから派生して[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)、および、MDI 子ウィンドウであり、ドキュメント フレーム ウィンドウ クラスから派生[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)です。  
  
## <a name="use-the-frame-window-class-or-derive-from-it"></a>フレーム ウィンドウ クラスを使用するか、そこから派生  
 これらのクラスは、アプリケーションに必要なフレーム ウィンドウの機能のほとんどを提供します。 通常の状況では、既定の動作と外観を提供するは、ニーズに合うされます。 追加の機能を必要がある場合は、これらのクラスから派生します。  
  
### <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [アプリケーションのウィザードで作成されるフレーム ウィンドウ クラス](../mfc/frame-window-classes-created-by-the-application-wizard.md)  
  
-   [フレーム ウィンドウ スタイル](../mfc/frame-window-styles-cpp.md)  
  
-   [MFC で作成したウィンドウのスタイルを変更します。](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)  
  
## <a name="see-also"></a>関連項目  
 [フレーム ウィンドウ](../mfc/frame-windows.md)

