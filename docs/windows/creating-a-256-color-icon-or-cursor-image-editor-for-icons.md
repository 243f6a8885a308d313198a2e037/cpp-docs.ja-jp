---
title: "256 色のアイコンまたはカーソル (アイコン用イメージ エディター) の作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- 256-color palette
- cursors, color
- colors, icons
- colors, cursors
- icons, color
ms.assetid: 2738089b-4fd3-4c45-96ae-6a15e4c6b780
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 11c25c808ad9d1917413a66044e052e4c49ea584
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-256-color-icon-or-cursor-image-editor-for-icons"></a>256 色のアイコンまたはカーソルの作成 (アイコン用イメージ エディター)
イメージ エディターを使用して、アイコンとカーソルは、サイズ設定された大規模な (64 × 64) から選択する 256 色カラー パレットを指定できます。 リソースを作成すると、デバイス イメージのスタイルが選択されます。  
  
### <a name="to-create-a-256-color-icon-or-cursor"></a>256 色のアイコンまたはカーソルを作成するには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)、.rc ファイルを右クリックし **リソースの挿入**ショートカット メニューからです。 (を単に右クリック、カーソルなど、.rc ファイルに既存のイメージ リソースがある場合、**カーソル**フォルダーを選択**挿入カーソル**ショートカット メニューからです)。  
  
     **メモ** プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  [リソースの挿入ダイアログ ボックス](../windows/add-resource-dialog-box.md)[**アイコン**または**カーソル**] をクリック**新規**です。  
  
3.  **イメージ** メニューのをクリックして**新しいデバイス イメージ**です。  
  
4.  256 色の画像のスタイルを選択します。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
 **必要条件**  
  
 なし  
  
## <a name="see-also"></a>参照  
 [256 色カラー パレットの使用](../windows/using-the-256-color-palette-image-editor-for-icons.md)   
 [アクセラレータ キー](../windows/accelerator-keys-image-editor-for-icons.md)   
 [アイコンとカーソル: ディスプレイ デバイスのイメージ リソース](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)

