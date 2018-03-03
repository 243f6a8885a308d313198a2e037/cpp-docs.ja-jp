---
title: "クラスのダイアログ ボックスを追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.addclass
dev_langs:
- C++
helpviewer_keywords:
- Add Class dialog box
ms.assetid: 916259b8-8e5f-4267-bd10-313483beba67
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9936120a28e7120b5efcaaf6e05318b3970dab99
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="add-class-dialog-box"></a>[クラスの追加] ダイアログ ボックス
**[クラスの追加]** ダイアログ ボックスのテンプレートを使用すると、次の操作を実行できます。  
  
-   対応するコード ウィザードを開始する (使用できる場合)。 詳細については、次を参照してください。[コード ウィザードを使用した機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)です。  
  
 \- または  
  
-   適したファイルおよびソース コードをプロジェクトに追加して、新しいクラスを自動作成する。  
  
 アクセスすることができます、**クラスの追加**からダイアログ ボックス、**プロジェクト**] メニューの [**ソリューション エクスプ ローラー**、または[クラス ビュー](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)です。  
  
> [!NOTE]
>  現在のプロジェクトに対応しないクラスを追加しようとすると、エラー メッセージが表示されます。 **[OK]** をクリックすると、 **[クラスの追加]** ダイアログ ボックスに戻ります。  
  
## <a name="add-class-templates"></a>クラスの追加テンプレート  
 **クラスの追加** テンプレートには、4 つのカテゴリ (.NET、ATL、MFC、汎用) があります。 **[テンプレート]** ウィンドウでテンプレートを選択すると、選択したテンプレートの説明が **[カテゴリ]** ウィンドウと **[テンプレート]** ウィンドウに表示されます。  
  
### <a name="net"></a>.NET  
  
|テンプレート|ウィザード|  
|--------------|------------|  
|ASP.NET Web サービス|使用できません|  
|コンポーネント クラス (.NET)|使用できません|  
|インストーラー クラス (.NET)|使用できません|  
|ユーザー コントロール (.NET)|使用できません|  
|Windows フォーム (.NET)|使用できません|  
  
### <a name="atl"></a>ATL  
  
|テンプレート|ウィザード|  
|--------------|------------|  
|MFC に ATL サポートを追加|使用できません|  
|ATL Active Server Page コンポーネント|[ATL Active Server Page コンポーネント ウィザード](../atl/reference/atl-active-server-page-component-wizard.md)|  
|ATL コントロール|[ATL コントロール ウィザード](../atl/reference/atl-control-wizard.md)|  
|ATL ダイアログ|[ATL ダイアログ ウィザード](../atl/reference/atl-dialog-wizard.md)|  
|ATL COM+ 1.0 コンポーネント|[ATL COM+ 1.0 コンポーネント ウィザード](../atl/reference/atl-com-plus-1-0-component-wizard.md)|  
|ATL OLEDB コンシューマー|[ATL OLE DB コンシューマー ウィザード](../atl/reference/atl-ole-db-consumer-wizard.md)|  
|ATL OLEDB プロバイダー|[ATL OLE DB プロバイダー ウィザード](../atl/reference/atl-ole-db-provider-wizard.md)|  
|ATL プロパティ ページ|[ATL プロパティ ページ ウィザード](../atl/reference/atl-property-page-wizard.md)|  
|ATL シンプル オブジェクト|[ATL シンプル オブジェクト ウィザード](../atl/reference/atl-simple-object-wizard.md)|  
|WMI イベント プロバイダー|WMI イベント プロバイダー ウィザード|  
|WMI インスタンス プロバイダー|WMI インスタンス プロバイダー ウィザード|  
  
### <a name="mfc"></a>MFC  
  
|テンプレート|ウィザード|  
|--------------|------------|  
|MFC クラス|[MFC クラス追加ウィザード](../mfc/reference/mfc-add-class-wizard.md)|  
|ActiveX コントロールの MFC クラス|[ActiveX コントロール クラス追加ウィザード](../ide/add-class-from-activex-control-wizard.md)|  
|TypeLib からの MFC クラス|[Typelib ウィザードからクラスを追加します。](../mfc/reference/add-class-from-typelib-wizard.md)|  
|MFC ODBC コンシューマー|[MFC ODBC コンシューマー ウィザード](../mfc/reference/mfc-odbc-consumer-wizard.md)|  
  
### <a name="generic-classes"></a>汎用クラス  
  
|テンプレート|ウィザード|  
|--------------|------------|  
|汎用 C++ クラス|[汎用 C++ クラス ウィザード](../ide/generic-cpp-class-wizard.md)|  
  
## <a name="see-also"></a>参照  
 [メンバー関数の追加](../ide/adding-a-member-function-visual-cpp.md)   
 [メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md)   
 [仮想関数のオーバーライド](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC メッセージ ハンドラー](../mfc/reference/adding-an-mfc-message-handler.md)   
 [クラス各部へ](../ide/navigating-the-class-structure-visual-cpp.md)