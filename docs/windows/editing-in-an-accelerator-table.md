---
title: "編集 (アクセラレータ テーブルで) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- accelerator tables [C++], editing
- keyboard shortcuts [C++], editing in an accelerator table
ms.assetid: 545b650b-4f26-4b20-8431-d942548443bd
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 909b5548856d5d2ffc31a4f43d5ce85e9c2f8e5e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="editing-in-an-accelerator-table"></a>アクセラレータ テーブルでのエントリの編集
### <a name="to-edit-in-an-accelerator-table"></a>アクセラレータ テーブルで編集するには  
  
1.  アイコンをダブルクリックして、アクセラレータ テーブルを開く[リソース ビュー](../windows/resource-view-window.md)です。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  テーブル内のエントリを選択し、クリックしてインプレース編集をアクティブにします。  
  
3.  変更するには、ドロップダウン コンボ ボックスから選択するか、インプレースで入力します。  
  
    -   [ID](id-property.md)でリストまたは入力して編集を選択します。  
  
    -   [修飾子](../windows/accelerator-modifier-property.md)、一覧から選択します。  
  
    -   [キー](../windows/accelerator-key-property.md)でリストまたは入力して編集を選択します。  
  
    -   [型](../windows/accelerator-type-property.md)、一覧から ASCII または VIRTKEY を選択します。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。*  
  
 **必要条件**  
  
 Win32  
  
## <a name="see-also"></a>参照  
 [アクセラレータ テーブルの編集](../windows/editing-accelerator-tables.md)   
 [アクセラレータ エディター](../windows/accelerator-editor.md)