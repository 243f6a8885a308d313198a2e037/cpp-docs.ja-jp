---
title: "アクセラレータ テーブルにエントリを追加する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- accelerator tables [C++], adding entries
- New Accelerator command
ms.assetid: 559c2415-8323-4339-9447-6966665f8288
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9fe2df81aae0b9b7232443de1db091a9cbb0c0d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="adding-an-entry-to-an-accelerator-table"></a>アクセラレータ テーブルへのエントリの追加
### <a name="to-add-an-entry-to-an-accelerator-table"></a>アクセラレータ テーブルにエントリを追加するには  
  
1.  アイコンをダブルクリックして、アクセラレータ テーブルを開く[リソース ビュー](../windows/resource-view-window.md)です。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  アクセラレータ テーブル内を右クリックして**新しいアクセラレータ**からショートカット メニューのまたはテーブルの下部にある空の行エントリをクリックします。  
  
3.  選択、 [ID](id-property.md) ID のドロップダウン リストからボックスまたは 新しい ID を入力、 **ID**ボックス。  
  
4.  型、[キー](../windows/accelerator-key-property.md)アクセラレータまたは右クリックとして使用しを選択する**キー タイピング登録**、ショートカット メニューをキーの組み合わせを設定する (、 **キー タイピング登録**コマンドは、利用でき、**編集**メニュー)。  
  
5.  変更、[修飾子](../windows/accelerator-modifier-property.md)と[型](../windows/accelerator-type-property.md)必要に応じて、します。  
  
6.  **Enter** キーを押します。  
  
    > [!NOTE]
    >  定義するすべてのアクセラレータが一意であることを確認します。 いくつかのキーの組み合わせを、同じ ID に問題なく割り当てることができます。たとえば、Ctrl + P と F8 は、どちらも ID_PRINT に割り当てることができます。 ただし、キーの組み合わせを複数の ID に割り当てると、うまく機能しません。たとえば、Ctrl + Z を ID_SPELL_CHECK と ID_THESAURUS の両方に割り当てる場合などです。  
  

  
 **必要条件**  
  
 Win32  
  
## <a name="see-also"></a>参照  
 [アクセラレータ テーブルの編集](../windows/editing-accelerator-tables.md)   
 [アクセラレータ エディター](../windows/accelerator-editor.md)