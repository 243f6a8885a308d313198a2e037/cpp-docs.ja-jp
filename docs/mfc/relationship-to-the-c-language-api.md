---
title: "C 言語 API との関係 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.mfc
dev_langs: C++
helpviewer_keywords:
- books [MFC], about MFC and Windows SDK
- books [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- Windows API [MFC], and MFC
ms.assetid: 334e8efc-f3cc-4018-bc2e-02908b2a39fe
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 26458242ab6afcf69d6e70065ba70e31f0adbe74
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="relationship-to-the-c-language-api"></a>C 言語 API との関係
Windows の他のクラス ライブラリとは別に、Microsoft Foundation Class (MFC) ライブラリを設定する特性の 1 つは、C 言語で記述された Windows API に非常に類似のマッピングです。 さらを混在させることが呼び出し、クラス ライブラリを自由に Windows API に直接の呼び出しをします。 この直接アクセス、ただしを意味しませんクラスが対象となる API の完全な置換です。 開発者がなど一部の Windows 関数への直接呼び出しを行う場合によってはまだ必要があります[以前](http://msdn.microsoft.com/library/windows/desktop/ms648393)と[問題](http://msdn.microsoft.com/library/windows/desktop/ms724385)、例を示します。 Windows の機能は、する作業は、明確な利点がある場合にのみ、クラス メンバー関数によってラップされます。  
  
 ネイティブの Windows 関数呼び出しを行う必要がある場合があります、ため、C 言語の Windows API のドキュメントへのアクセスが必要です。 このドキュメントは、Microsoft Visual C に含まれています。  
  
> [!NOTE]
>  MFC ライブラリのフレームワークの動作方法の詳細については、次を参照してください。[クラスを Windows アプリケーションの作成に使用する](../mfc/using-the-classes-to-write-applications-for-windows.md)です。  
  
## <a name="see-also"></a>参照  
 [一般的なクラス デザインの考え方](../mfc/general-class-design-philosophy.md)
