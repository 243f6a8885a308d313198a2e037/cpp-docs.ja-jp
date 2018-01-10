---
title: "タイプ ライブラリからの MFC クラスの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- classes [MFC], adding MFC
- MFC, adding classes from type libraries
- type libraries, adding MFC classes from
ms.assetid: aba40476-3cfb-47af-990e-ae2e9e0d79cf
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1efc61e097d7e1136fdb7b6ef740dc00342077e4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="adding-an-mfc-class-from-a-type-library"></a>タイプ ライブラリからの MFC クラスの追加
このウィザードを使用すると、利用可能なタイプ ライブラリ内のインターフェイスからの MFC クラスを作成します。 MFC クラスを追加することができます、 [MFC アプリケーション](../../mfc/reference/creating-an-mfc-application.md)、 [MFC DLL](../../mfc/reference/creating-an-mfc-dll-project.md)、または[MFC ActiveX コントロール](../../mfc/reference/creating-an-mfc-activex-control.md)です。  
  
> [!NOTE]
>  タイプ ライブラリからクラスを追加する有効な Automation では、MFC プロジェクトを作成する必要はありません。  
  
 タイプ ライブラリには、パラメーターと戻り値の型とメソッドを定義する、コンポーネントによって公開されるインターフェイスのバイナリ記述が含まれています。 表示するため、タイプ ライブラリを登録する必要があります、**使用可能なタイプ ライブラリ**Typelib ウィザードからのクラスの追加の一覧です。 「内部分散 COM:: タイプ ライブラリと言語統合」詳細については、MSDN ライブラリを参照してください。  
  
### <a name="to-add-an-mfc-class-from-a-type-library"></a>タイプ ライブラリからの MFC クラスを追加するには  
  
1.  いずれかで**ソリューション エクスプ ローラー**または[クラス ビュー](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)クラスを追加するプロジェクトの名前を右クリックします。  
  
2.  ショートカット メニューをクリックして**追加**、クリックして**クラスの追加**です。  
  
3.  [クラスの追加](../../ide/add-class-dialog-box.md)ダイアログ ボックスの [テンプレート] ペインで、クリックして**Typelib からの MFC クラス**、順にクリック**開く**を表示する、 [Typelib ウィザードからのクラスの追加](../../mfc/reference/add-class-from-typelib-wizard.md).  
  
 ウィザードで、タイプ ライブラリ内の 2 つ以上のクラスを追加することができます。 同様に、1 つのウィザード セッションで 1 つ以上のタイプ ライブラリからクラスを追加することができます。  
  
 派生した MFC クラスを作成するウィザード[COleDispatchDriver](../../mfc/reference/coledispatchdriver-class.md)、選択したタイプ ライブラリから追加する各インターフェイスに対してです。 `COleDispatchDriver`OLE オートメーションのクライアント側を実装します。  
  
## <a name="see-also"></a>参照  
 [オートメーション クライアント](../../mfc/automation-clients.md)   
 [オートメーション クライアント: タイプ ライブラリの使用](../../mfc/automation-clients-using-type-libraries.md)

