---
title: "方法: 既存の MFC リボンをリボン リソースに変換します |。Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ribbon resource, converting from an MFC ribbon
- MFC ribbon, converting to a ribbon resource
ms.assetid: 324b7ff6-58f9-4691-96a9-9836a79d0fb6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e7cb0d5d80edd52a85834963d030e35eef96d718
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-convert-an-existing-mfc-ribbon-to-a-ribbon-resource"></a>方法: 既存の MFC リボンをリボン リソースに変換する
リボン リソースは、視覚化、変更、および手動でコード化されたリボンより管理しやすくします。 このトピックでは、MFC プロジェクトに手動でコード化されたリボンをリボン リソースに変換する方法について説明します。  
  
 たとえば、MFC リボン クラスを使用するコードを持つ既存の MFC プロジェクトをする必要があります[CMFCRibbonBar クラス](../mfc/reference/cmfcribbonbar-class.md)です。  
  
### <a name="to-convert-an-mfc-ribbon-to-a-ribbon-resource"></a>MFC リボンをリボン リソースに変換するには  
  
1.  Visual Studio での既存の MFC プロジェクトで CMFCRibbonBar オブジェクトが初期化されて、ソース ファイルを開きます。 通常、ファイルは、mainfrm.cpp です。 リボンの初期化コードの後に、次のコードを追加します。  
  
 ```  
    m_wndRibbonBar.SaveToXMLFile("RibbonOutput.xml");

 ```  
  
     ファイルを保存して閉じます。  
  
2.  ビルド、MFC アプリケーションを実行し、メモ帳で、RibbonOutput.txt し開いてその内容をコピーします。  
  
3.  Visual Studio での**プロジェクト** メニューのをクリックして**リソースの追加**です。 **リソースの追加**ダイアログ ボックスで、**リボン** をクリックし、**新規**です。  
  
     Visual Studio では、リボン リソースを作成し、デザイン ビューで開きます。 リボン リソース ID に表示される IDR_RIBBON1**リソース ビュー**です。 リボンは、ribbon1.mfcribbon ms XML ファイルで定義されます。  
  
4.  Visual Studio で、ribbon1.mfcribbon ms、その内容を削除し RibbonOutput.txt で、先ほどコピーの内容を貼り付けます。 保存して ribbon1.mfcribbon ms を閉じます。  
  
5.  CMFCRibbonBar オブジェクトが初期化されてソース ファイルをもう一度開きます (一般に、mainfrm.cpp) し、リボンのコードを既存のコメント。 コメント アウトされているコードの後に、次のコードを追加します。  
  
 ```  
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);

 ```  
  
6.  プロジェクトをビルドし、プログラムを実行します。  
  
## <a name="see-also"></a>参照  
 [リボン デザイナー (MFC)](../mfc/ribbon-designer-mfc.md)

