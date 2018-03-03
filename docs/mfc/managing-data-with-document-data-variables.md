---
title: "ドキュメント データ変数を使用してデータを管理する |Microsoft ドキュメント"
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
- documents [MFC], data storage
- friend classes [MFC]
- classes [MFC], friend
- data [MFC]
- data [MFC], documents
- collection classes [MFC], used by document object
- document data [MFC]
- member variables [MFC], document class [MFC]
ms.assetid: e70b87f4-8c30-49e5-8986-521c2ff91704
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c737557d503ca7e0959d159a0818f1ca78280ea2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="managing-data-with-document-data-variables"></a>ドキュメント データ変数を使ったデータ管理
ドキュメント クラスのメンバー変数として、ドキュメントのデータを実装します。 たとえば、この Scribble プログラムが型のデータ メンバーを宣言して`CObList`— へのポインターを格納するリンクされたリスト`CObject`オブジェクト。 この一覧を使用して、フリーハンド線画を構成する点の配列を格納します。  
  
 ドキュメントのメンバー データを実装する方法は、アプリケーションの性質によって異なります。 アウトするために、MFC での「コレクション クラス」グループに提供: 配列、リスト、および C++ テンプレートに基づいてコレクションを含むマップ (辞書)、-など、さまざまな一般的なデータ型をカプセル化するクラスと共に`CString`、 `CRect`、 `CPoint`、 `CSize`、および`CTime`です。 これらのクラスの詳細については、次を参照してください。、[クラス ライブラリの概要](../mfc/class-library-overview.md)で、 *『 MFC リファレンス*です。  
  
 ドキュメントのメンバー データを定義するときは、設定しデータ項目を取得し、他の便利操作を実行するには、ドキュメント クラスに通常のメンバー関数を追加します。  
  
 ビューには、ビューの作成時にインストールされているドキュメントに、ビューのポインターを使用してドキュメント オブジェクトにアクセスします。 このビューのメンバー関数ポインターを取得するには呼び出すことによって、`CView`メンバー関数は、 **GetDocument**です。 必ず、独自のドキュメントの種類へのポインターをキャストしてください。 ポインターを通じてパブリック ドキュメント メンバーにアクセスすることができます。  
  
 頻繁なデータ転送には、直接のアクセスが必要です、またはドキュメント クラスの非パブリック メンバーを使用する、クラスのフレンド クラス (C++ の用語) ドキュメント クラスのビューを作成することがあります。  
  
## <a name="see-also"></a>参照  
 [ドキュメントの使い方](../mfc/using-documents.md)

