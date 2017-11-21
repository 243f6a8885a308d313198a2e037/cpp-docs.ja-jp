---
title: "方法: リソースを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- toolbars [C++], resources
- resource toolbars
- resources [Visual Studio], creating
ms.assetid: aad44914-9145-45a3-a7d8-9de89b366716
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 46e03602e53c79ff6c384ad9cc613849cb329423
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-create-a-resource"></a>方法: リソースを作成する
> [!NOTE]
>  リソース ビューは Express Edition ではサポートされていません。  
  
### <a name="to-create-a-new-resource-in-resource-view"></a>リソース ビューでリソースを新規作成するには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)でフォーカスを .rc ファイルに置き、 **[編集]** メニューの **[リソースの追加]** をクリックするか、またはリソース ビューで .rc ファイルを右クリックし、ショートカット メニューの **[リソースの追加]** をクリックします。  
  
     **メモ** プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  [[リソースの追加] ダイアログ ボックス](../windows/add-resource-dialog-box.md)で、プロジェクトに追加するリソースを選択します。  
  
### <a name="to-create-a-new-resource-in-solution-explorer"></a>ソリューション エクスプローラーでリソースを新規作成するには  
  
1.  **ソリューション エクスプローラー**でプロジェクト フォルダーを右クリックし、ショートカット メニューの **[追加]**、 **[リソースの追加]** の順にクリックします。  
  
     プロジェクトに .rc ファイルがない場合は、この手順で作成されます。 その後、この手順を繰り返すと、特定のリソースの種類を新しい .rc ファイルに追加できます。  
  
2.  [[リソースの追加] ダイアログ ボックス](../windows/add-resource-dialog-box.md)で、プロジェクトに追加するリソースを選択します。  
  
### <a name="to-create-a-new-resource-in-class-view"></a>クラス ビューでリソースを新規作成するには  
  
1.  [クラス ビュー](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)で、クラスを右クリックし、ショートカット メニューの **[追加]**、 **[リソースの追加]** の順にクリックします。  
  
2.  [[リソースの追加] ダイアログ ボックス](../windows/add-resource-dialog-box.md)で、プロジェクトに追加するリソースを選択します。  
  
### <a name="to-create-a-new-resource-from-the-project-menu"></a>[プロジェクト] メニューからリソースを新規作成するには  
  
1.  **[プロジェクト]** メニューの **[リソースの追加]**を選択します。  
  
 リソースを新規作成すると、Visual C++ により IDD_Dialog1 などの一意の名前が割り当てられます。 関連するリソース エディターまたは [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)でリソースのプロパティを編集することによって、このリソース ID をカスタマイズできます。  
  
 リソースは、新しい既定のリソース (テンプレートに基づいていないリソース) として作成するか、または [テンプレート](../windows/how-to-use-resource-templates.md)の後でパターン化されるリソースとして作成できます。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。*  
  
 **Requirements**  
  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [リソース ファイル (Visual Studio)](../windows/resource-files-visual-studio.md)   
 [リソース エディター](../windows/resource-editors.md)   
 [[リソースの追加] ダイアログ ボックス](../windows/add-resource-dialog-box.md)