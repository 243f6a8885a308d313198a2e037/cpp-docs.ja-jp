---
title: アクセラレータ テーブルへのエントリの追加 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- accelerator tables [C++], adding entries
- New Accelerator command
ms.assetid: 559c2415-8323-4339-9447-6966665f8288
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e0c5e94913a705ac97407f82075ff9c83a12dd6b
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642790"
---
# <a name="adding-an-entry-to-an-accelerator-table"></a>アクセラレータ テーブルへのエントリの追加
### <a name="to-add-an-entry-to-an-accelerator-table"></a>アクセラレータ テーブルにエントリを追加するには  
  
1.  アイコンをダブルクリックして、アクセラレータ テーブルを開く[リソース ビュー](../windows/resource-view-window.md)します。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  アクセラレータ テーブル内で右クリックし、**新しいアクセラレータ**からショートカット メニューのまたはテーブルの下部にある空の行エントリをクリックします。  
  
3.  選択、 [ID](id-property.md) ID のドロップダウン リストからボックスまたは新しい ID を入力、 **ID**ボックス。  
  
4.  型、[キー](../windows/accelerator-key-property.md)アクセラレータまたは右クリックとして使用する**キー タイピング登録**キーの組み合わせを設定するショートカット メニュー (、 **キー タイピング登録**コマンドは、使用可能な**編集**メニュー)。  
  
5.  変更、[修飾子](../windows/accelerator-modifier-property.md)と[型](../windows/accelerator-type-property.md)、必要な場合。  
  
6.  **Enter** キーを押します。  
  
    > [!NOTE]
    >  定義するすべてのアクセラレータが一意であることを確認します。 たとえば、同じ ID に割り当てられているいくつかのキーの組み合わせがあることができます**Ctrl** + **P**と**F8**どちらも ID_PRINT に割り当てる割り当てすることができます。 ただし、1 つ以上の ID は、うまく機能しませんなどに割り当てられているキーの組み合わせを持つ**Ctrl** + **Z** ID_SPELL_CHECK と ID_THESAURUS の両方に割り当てられます。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [アクセラレータ テーブルの編集](../windows/editing-accelerator-tables.md)   
 [アクセラレータ エディター](../windows/accelerator-editor.md)