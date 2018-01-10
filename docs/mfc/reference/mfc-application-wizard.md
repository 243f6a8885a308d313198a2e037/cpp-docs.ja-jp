---
title: "MFC アプリケーション ウィザード |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.mfc.exe.overview
dev_langs: C++
helpviewer_keywords:
- MFC Application Wizard
- executable files, creating
ms.assetid: 227ac090-921d-4b2f-be0a-66a5f4cab0d4
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9d4997d2d793102119e5021ba1110db2674e1b42
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-application-wizard"></a>MFC アプリケーション ウィザード
MFC アプリケーション ウィザードでは、コンパイル時に Windows 実行可能アプリケーション (.exe) の基本機能が実装されるアプリケーションが生成されます。 MFC の初期アプリケーションには、C++ ソース (.cpp) ファイル、リソース (.rc) ファイル、ヘッダー (.h) ファイル、およびプロジェクト (.vcxproj) ファイルが含まれます。 これらの初期ファイルで生成されるコードは、MFC に基づいています。  
  
> [!NOTE]
>  選択したオプションに応じて、ウィザードがこの他のファイルをプロジェクトに作成します。 例では、選択した場合の**状況依存のヘルプ**上、[高度な機能](../../mfc/reference/advanced-features-mfc-application-wizard.md) ページで、ウィザードは、プロジェクトのヘルプ ファイルをコンパイルするために必要なファイルを作成します。 ウィザードで作成されるファイルの詳細については、次を参照してください。 [Visual c プロジェクトに対して作成されるファイルの種類](../../ide/file-types-created-for-visual-cpp-projects.md)、し、プロジェクトの Readme.txt ファイルを参照してください。  
  
## <a name="overview"></a>概要  
 ウィザードのこのページでは、作成する MFC アプリケーションの現在のアプリケーション設定が示されます。 既定では、このウィザードでは、次のようなウィザード プロジェクトが作成されます。  
  
-   [[アプリケーションの種類] (MFC アプリケーション ウィザード)](../../mfc/reference/application-type-mfc-application-wizard.md)  
  
    -   タブ付きのマルチ ドキュメント インターフェイス (MDI: Multiple Document Interface) をサポートするプロジェクト。 詳細については、次を参照してください。 [SDI と MDI](../../mfc/sdi-and-mdi.md)です。  
  
    -   プロジェクトを使用して、[ドキュメント/ビュー アーキテクチャ](../../mfc/document-view-architecture.md)です。  
  
    -   Unicode ライブラリを使用するプロジェクト  
  
    -   Visual Studio のプロジェクト形式を使用して作成された、表示形式の切り替えができるプロジェクト  
  
    -   共有 DLL 内の MFC を使用するプロジェクト 詳細については、「[Visual C++ の DLL](../../build/dlls-in-visual-cpp.md)」をご覧ください。  
  
-   [[複合ドキュメント サポート] (MFC アプリケーション ウィザード)](../../mfc/reference/compound-document-support-mfc-application-wizard.md)  
  
    -   複合ドキュメントをサポートするプロジェクト  
  
-   [[ドキュメント テンプレート文字列] (MFC アプリケーション ウィザード)](../../mfc/reference/document-template-strings-mfc-application-wizard.md)  
  
    -   既定のドキュメント テンプレート文字列としてプロジェクト名を使用するプロジェクト  
  
-   [[データベース サポート] (MFC アプリケーション ウィザード)](../../mfc/reference/database-support-mfc-application-wizard.md)  
  
    -   データベースをサポートするプロジェクト  
  
-   [[ユーザー インターフェイスの機能] (MFC アプリケーション ウィザード)](../../mfc/reference/user-interface-features-mfc-application-wizard.md)  
  
    -   標準の Windows ユーザー インターフェイスがシステム メニューのステータス バー、最大化し、ボックスに、最小限に抑えるように機能を実装するプロジェクト、**に関する**ボックス、標準のメニュー バーとドッキング ツールバー、および子フレーム。  
  
-   [[高度な機能] (MFC アプリケーション ウィザード)](../../mfc/reference/advanced-features-mfc-application-wizard.md)  
  
    -   印刷と印刷プレビューをサポートするプロジェクト  
  
    -   ActiveX コントロールをサポートするプロジェクト 詳細については、次を参照してください。 [ActiveX コントロールの作成の操作のシーケンス](../../mfc/sequence-of-operations-for-creating-activex-controls.md)です。  
  
    -   プロジェクトのサポートが提供されません[オートメーション](../../mfc/automation.md)、 [MAPI](../../mfc/mapi-support-in-mfc.md)、 [Windows Sockets](../../mfc/windows-sockets-in-mfc.md)、または Active Accessibility です。  
  
    -   プロジェクトをサポートしている、**エクスプ ローラー** 、ドッキング ペイン、**出力**、ドッキング ペイン、および**プロパティ**ドッキング ペインです。  
  
-   [[生成されたクラス] (MFC アプリケーション ウィザード)](../../mfc/reference/generated-classes-mfc-application-wizard.md)  
  
    -   プロジェクトのビュー クラス、 [CView クラス](../../mfc/reference/cview-class.md)です。  
  
    -   派生した、プロジェクトのアプリケーションのクラスは、 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)です。  
  
    -   プロジェクトのドキュメント クラス、 [CDocument クラス](../../mfc/reference/cdocument-class.md)です。  
  
    -   プロジェクトのメイン フレーム クラス、 [CMDIFrameWndEx クラス](../../mfc/reference/cmdiframewndex-class.md)です。  
  
    -   プロジェクトの子フレーム クラスから派生、 [CMDIChildWndEx クラス](../../mfc/reference/cmdichildwndex-class.md)です。  
  
 これらの既定の設定を変更するには、ウィザードの左の列で該当するタブ タイトルをクリックし、表示されるページで必要な変更を行います。  
  
 MFC アプリケーション プロジェクトを作成した後する Visual C を使用して、プロジェクトにオブジェクトやコントロールを追加できます[コード ウィザード](../../ide/adding-functionality-with-code-wizards-cpp.md)です。  
  
## <a name="see-also"></a>参照  
 [MFC アプリケーションの作成](../../mfc/reference/creating-an-mfc-application.md)   
 [MFC デスクトップ アプリケーション](../../mfc/mfc-desktop-applications.md)   
 [クラスを使用した Windows アプリケーションの作成](../../mfc/using-the-classes-to-write-applications-for-windows.md)
