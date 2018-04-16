---
title: "MFC オブジェクト間の関係 |Microsoft ドキュメント"
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
- MFC, relationships between key objects
- objects [MFC], relationships
- relationships, MFC objects
- MFC object relationships
ms.assetid: 6e8f3b51-e80f-4d88-94c8-4c1e4ee163ad
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2ea93e9e56b676e4dfef33ecbcabfd9754458024
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="relationships-among-mfc-objects"></a>各種 MFC オブジェクト間の関係
パースペクティブにドキュメント/ビューの作成プロセスを配置するには、実行中のプログラムを検討してください: ドキュメント、ビューの格納に使用されるフレーム ウィンドウおよびドキュメントに関連付けられたビュー。  
  
-   ドキュメントは、ドキュメントを作成するドキュメント テンプレートへのポインター、そのドキュメントのビューの一覧を保持します。  
  
-   ビューは、ドキュメントへのポインターを保持、親フレーム ウィンドウの子です。  
  
-   ドキュメント フレーム ウィンドウは、その現在のアクティブなビューへのポインターを保持します。  
  
-   ドキュメント テンプレートは、開いているドキュメントのリストを保持します。  
  
-   アプリケーションでは、そのドキュメント テンプレートのリストを保持します。  
  
-   Windows は追跡の開いているすべての windows にメッセージを送信できるようにします。  
  
 ドキュメント/ビューの作成時に、これらのリレーションシップが確立されます。 次の表では、実行中のプログラム内のオブジェクトが他のオブジェクトにアクセスする方法を示します。 任意のオブジェクトは、グローバル関数を呼び出すことによって、アプリケーション オブジェクトへのポインターを取得できます[AfxGetApp](../mfc/reference/application-information-and-management.md#afxgetapp)です。  
  
### <a name="gaining-access-to-other-objects-in-your-application"></a>アプリケーション内の他のオブジェクトへのアクセス  
  
|オブジェクトから|その他のオブジェクトにアクセスする方法|  
|-----------------|---------------------------------|  
|ドキュメント|使用して[GetFirstViewPosition](../mfc/reference/cdocument-class.md#getfirstviewposition)と[GetNextView](../mfc/reference/cdocument-class.md#getnextview)ドキュメントのビューの一覧を表示します。<br /><br /> 呼び出す[GetDocTemplate](../mfc/reference/cdocument-class.md#getdoctemplate)ドキュメント テンプレートを取得します。|  
|表示|呼び出す[GetDocument](../mfc/reference/cview-class.md#getdocument)ドキュメントを取得します。<br /><br /> 呼び出す[GetParentFrame](../mfc/reference/cwnd-class.md#getparentframe)フレーム ウィンドウを取得します。|  
|ドキュメント フレーム ウィンドウ|呼び出す[GetActiveView](../mfc/reference/cframewnd-class.md#getactiveview)を現在のビューを取得します。<br /><br /> 呼び出す[GetActiveDocument](../mfc/reference/cframewnd-class.md#getactivedocument)現在のビューにアタッチされているドキュメントを取得します。|  
|MDI フレーム ウィンドウ|呼び出す[MDIGetActive](../mfc/reference/cmdiframewnd-class.md#mdigetactive)を現在アクティブな取得[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)です。|  
  
 通常、フレーム ウィンドウが 1 つのビューが、場合によっては、分割ウィンドウと同様に、同じフレーム ウィンドウが含まれる複数のビュー。 フレーム ウィンドウが現在アクティブなビューにポインターを保持します。ポインターには、いつでも別のビューがアクティブ化が更新されます。  
  
> [!NOTE]
>  メイン フレーム ウィンドウへのポインターが格納されている、 [m_pMainWnd](../mfc/reference/cwinthread-class.md#m_pmainwnd)アプリケーション オブジェクトのメンバー変数。 呼び出し`OnFileNew`のオーバーライドで、`InitInstance`のメンバー関数`CWinApp`設定`m_pMainWnd`します。 呼び出さない場合`OnFileNew`変数の値を設定する必要があります`InitInstance`自分でします。 (SDI COM コンポーネント (サーバー) のアプリケーションが変数を設定しなかった場合は、コマンドラインで/Embedding。)なお`m_pMainWnd`クラスのメンバーであるようになりました`CWinThread`なく`CWinApp`です。  
  
## <a name="see-also"></a>参照  
 [ドキュメント テンプレートとドキュメント/ビューの作成手順](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [ドキュメント テンプレートの作成](../mfc/document-template-creation.md)   
 [ドキュメント/ビューの作成](../mfc/document-view-creation.md)   
 [新しいドキュメント、ウィンドウ、ビューの作成](../mfc/creating-new-documents-windows-and-views.md)

