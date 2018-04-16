---
title: "フレームワークが、コードを呼び出す方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- control flow [MFC], MFC framework and your code
- events [MFC], command routing in MFC
- command routing [MFC], framework
- command handling [MFC], calling handlers and code in MFC
- events [MFC], event-driven programming
- MFC, calling code from
- MFC, calling code
- application-specific events [MFC]
- command routing [MFC], MFC
ms.assetid: 39e68189-a580-40d0-9e35-bf5cd24a8ecf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 83eeb1c7fd3032ae33c213f17522b171bdb46e55
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="how-the-framework-calls-your-code"></a>フレームワークと記述したコードとの関係
これは、ソース コードと、MFC フレームワーク内のコード間の関係を理解するために重要です。 アプリケーションを実行するときに、制御フローのほとんどは、framework のコードに存在します。 フレームワークは、メッセージのように、ユーザーがコマンドを選択し、編集ビューでのデータを Windows から取得されるメッセージ ループを管理します。 フレームワークは、それ自体で処理できるイベントに依存しないコードにします。 たとえば、フレームワークは、ユーザー コマンドへの応答でアプリケーションを終了する方法と、ウィンドウを閉じる方法を認識します。 これらのタスク処理時に、フレームワークはこれらのイベントに応答するのに機会を提供するのにメッセージ ハンドラーと C++ の仮想関数を使用します。 ただし; は、コントロールではなく、コードです。フレームワークです。  
  
 フレームワークは、アプリケーションに固有のイベントのコードを呼び出します。 たとえば、メニュー コマンドを選択すると、フレームワーク、コマンド ルーティングの C++ オブジェクトのシーケンスに沿った: 現在のビューとフレームのウィンドウで、ビュー、ドキュメントのドキュメント テンプレート、およびアプリケーションのオブジェクトに関連付けられたドキュメントです。 コマンドは、これらのオブジェクトが処理される場合は、適切なメッセージ ハンドラー関数を呼び出すことです。 、任意のコマンドを呼び出されるコードが自分のものかフレームワークの場合があります。  
  
 この配置は、Windows の従来のプログラミングまたはイベント ドリブン プログラミングの使用経験がプログラマにいくらか知っています。  
  
 関連のトピックでは、どのようなフレームワークは初期化しアプリケーションを実行して、クリーンアップ、アプリケーションが終了するとを読み取ります。 収まることを記述するコードをここでは理解もできます。  
  
 詳細については、次を参照してください。[クラス CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)と[ドキュメント テンプレートとドキュメント/ビューの作成手順](../mfc/document-templates-and-the-document-view-creation-process.md)です。  
  
## <a name="see-also"></a>参照  
 [フレームワークを使ったアプリケーションの作成](../mfc/building-on-the-framework.md)

