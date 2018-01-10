---
title: "CWnd オブジェクトの初期化のタイミング |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- window objects [MFC], when to initialize CWnd
- initializing CWnd objects [MFC]
- initializing objects [MFC], CWnd
- CWnd objects [MFC], when HWND is attached
- HWND, when attached to CWnd object
- CWnd objects [MFC], when to initialize
ms.assetid: 4d31bcb1-73db-4f2f-b71c-89b087569a10
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3d1efceb4fa826d5cd2bf8dc900180eb36cea4de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="when-to-initialize-cwnd-objects"></a>CWnd オブジェクトの初期化のタイミング
独自の子ウィンドウを作成またはのコンス トラクターで、Windows API 関数を呼び出すことはできません、 `CWnd`-派生オブジェクト。 これは、ため、`HWND`の`CWnd`オブジェクトがまだ作成されていません。 子ウィンドウを追加するなど、最も Windows 固有の初期化を行う必要があります、 [OnCreate](../mfc/reference/cwnd-class.md#oncreate)メッセージ ハンドラー。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [ドキュメント フレーム ウィンドウの作成](../mfc/creating-document-frame-windows.md)  
  
-   [ドキュメント/ビューの作成](../mfc/document-view-creation.md)  
  
## <a name="see-also"></a>参照  
 [フレーム ウィンドウの使用](../mfc/using-frame-windows.md)

