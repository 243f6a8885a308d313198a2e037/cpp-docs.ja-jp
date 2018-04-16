---
title: "ATL サポートの詳細については、ATL ウィザードで追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.atl.support
dev_langs:
- C++
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: aa66bad0-008f-4886-94c1-2a0a0d04bce4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 17d5063db9eb76e0fc6db9eecfe183b63276b874
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="details-of-atl-support-added-by-the-atl-wizard"></a>ATL ウィザードで追加した ATL サポートの詳細
ときに、[既存の MFC の実行可能ファイルまたは DLL に ATL サポートを追加](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)、Visual C は、既存の MFC プロジェクトに次の変更 (この例では、プロジェクトと呼びます`MFCEXE`)。  
  
-   2 つの新しいファイル (.idl ファイルと、サーバーを登録するために使用、.rgs ファイル) が追加されます。  
  
-   アプリケーションのメイン ヘッダー ファイルと実装ファイル (Mfcexe.h および Mfcexe.cpp) で、新しいクラス (から派生した**CAtlMFCModule**) を追加します。 コードを追加、新しいクラスだけでなく`InitInstance`登録します。 コードにも追加、`ExitInstance`クラス オブジェクトを取り消すための関数。 ヘッダー ファイルに最後に、新しい 2 つのヘッダー ファイル (Initguid.h および Mfcexe_i.c) に含まれて、実装ファイルは、宣言と初期化用に新しい Guid、 **CAtlMFCModule**-クラスを派生します。  
  
-   正しく、サーバーを登録するには、新しい .rgs ファイルのエントリが、プロジェクトのリソース ファイルに追加されます。  
  
## <a name="notes-for-dll-projects"></a>DLL プロジェクトに関するメモ  
 MFC DLL プロジェクトに ATL サポートを追加する場合は、いくつか相違点が表示されます。 コードに追加されます、 **DLLRegisterServer**と**DLLUnregisterServer**を登録して、DLL の登録を解除するための関数。 コードにも追加[DllCanUnloadNow](../../atl/reference/catldllmodulet-class.md#dllcanunloadnow)と[DllGetClassObject](../../atl/reference/catldllmodulet-class.md#dllgetclassobject)です。  
  
## <a name="see-also"></a>参照  
 [MFC プロジェクトに ATL サポート](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)   
 [コード ウィザードによる機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [クラスの追加](../../ide/adding-a-class-visual-cpp.md)   
 [メンバー関数の追加](../../ide/adding-a-member-function-visual-cpp.md)   
 [メンバー変数の追加](../../ide/adding-a-member-variable-visual-cpp.md)   
 [仮想関数のオーバーライド](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC メッセージ ハンドラー](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [クラス各部へ](../../ide/navigating-the-class-structure-visual-cpp.md)
