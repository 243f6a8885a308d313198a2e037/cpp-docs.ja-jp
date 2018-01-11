---
title: "文字列に文字書式または特殊文字を追加する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- special characters, adding to strings
- ASCII characters, adding to strings
- strings [C++], formatting
- strings [C++], special characters
ms.assetid: c40f394a-8b2c-4896-ab30-6922863ddbb5
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ca91ef9742f2dfb10a0af12c74ca58f80035d131
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="adding-formatting-or-special-characters-to-a-string"></a>文字列への書式指定文字または特殊文字の追加
### <a name="to-add-formatting-or-special-characters-to-a-string"></a>文字列に文字書式または特殊文字を追加するには  
  
1.  アイコンをダブルクリックして、文字列テーブルを開きます[リソース ビュー](../windows/resource-view-window.md)です。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  変更する文字列を選択します。  
  
3.  [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)、内のテキストの下にリストの標準のエスケープ シーケンスのいずれかの追加、**キャプション**ボックス、およびキーを押して**ENTER**です。  
  
    |これを取得するには|入力します。|  
    |-----------------|---------------|  
    |改行|\n|  
    |キャリッジ リターン|\r|  
    |タブ|\t|  
    |円記号 (\\)|\\\|  
    |ASCII 文字|\ddd (8 進表記)|  
    |警告 (ベル)|\a|  
  
> [!NOTE]
>  ストリング エディターは ASCI 文字のエスケープの完全なセットをサポートしていません。 上記のリストにのみ使用できます。  
  
 マネージ プロジェクト (共通言語ランタイムを対象とするもの) にリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* 」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「 [チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) 」および「 [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)。  
  
 **必要条件**  
  
 Win32  
  
## <a name="see-also"></a>参照  
 [ストリング エディター](../windows/string-editor.md)   

