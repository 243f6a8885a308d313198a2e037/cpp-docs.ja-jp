---
title: "標準 Windows メッセージのハンドラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: afx_msg
dev_langs: C++
helpviewer_keywords:
- Windows messages [MFC], handlers
- message handling [MFC], Windows message handlers
- handler functions, standard Windows messages
- functions [MFC], handler
- messages [MFC], Windows
ms.assetid: 19412a8b-2c38-4502-81da-13c823c7e36c
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 91df3462297c2a45a8938d815cc3b6a3b8ca6edb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="handlers-for-standard-windows-messages"></a>標準 Windows メッセージのハンドラー
既定の標準の Windows メッセージのハンドラー (**wm _ で始まる**) クラスで定義済み`CWnd`です。 クラス ライブラリは、メッセージ名に基づいて、これらのハンドラーの名前を行います。 たとえばのハンドラーを`WM_PAINT`でメッセージが宣言されている`CWnd`として。  
  
 `afx_msg void OnPaint();`  
  
 **Afx_msg**キーワードは C++ の効果を提案**仮想**キーワードを他のハンドラーを区別することによって`CWnd`メンバー関数。 ただし、これらの関数が実際には仮想; がないこと代わりにメッセージ マップを通じて実装されます。 メッセージ マップは、C++ 言語へのすべての拡張機能ではなく、標準のプリプロセッサ マクロにのみ依存します。 **Afx_msg**キーワードは、前処理した後、空白文字に解決されます。  
  
 基底クラスで定義されているハンドラーを変更するとハンドラーのメッセージ マップ エントリを作成するのには、派生クラスで同じプロトタイプを持つ関数を定義します。 ハンドラー「上書き」クラスの基底クラスのいずれかで、同じ名前のいずれかのハンドラー。  
  
 場合によっては、ハンドラーは、基底クラスと Windows でメッセージを処理できるように、基底クラスでオーバーライドされたハンドラーを呼び出す必要があります。 オーバーライドで基底クラスのハンドラーを呼び出す場所は、状況によって異なります。 場合があります最初の基本クラスのハンドラーを呼び出し、最後の場合もありますする必要があります。 呼び出すことも、基底クラス ハンドラー条件付きで、メッセージを処理しないように選択する場合。 基本クラスのハンドラーを呼び出すし、値または基本クラスのハンドラーによって返された状態によっては、独自のハンドラー コードを条件付きで実行する必要があります。  
  
> [!CAUTION]
>  基本クラスのハンドラーに渡す場合、ハンドラーに渡される引数を変更する安全ではありません。 たとえば、する場合がありますを変更したくなる、`nChar`の引数、`OnChar`ハンドラー (大文字に変換するなど)。 この動作は、あまり知られてがこの特殊効果を実行する必要がある場合、`CWnd`メンバー関数は、 **SendMessage**代わりにします。  
  
 [プロパティ] ウィンドウは、特定のメッセージのハンドラー関数のスケルトンを書き込む場合に、特定のメッセージを上書きする適切な方法を決定する方法:、`OnCreate`のハンドラーを`WM_CREATE`、たとえば — の推奨される形式で、スケッチメンバー関数をオーバーライドします。 次の例は、ハンドラーが最初に基底クラスのハンドラーを呼び出す、のみである条件で-1 が返されませんに行われるお勧めします。  
  
 [!code-cpp[NVC_MFCMessageHandling#3](../mfc/codesnippet/cpp/handlers-for-standard-windows-messages_1.cpp)]  
  
 慣例により、これらのハンドラーの名前プレフィックスで始まる、"On" これらのハンドラーの引数を受け取らず、いくつかあればです。 ある戻り値の型以外の`void`します。 すべての既定のハンドラー **wm _ で始まる**メッセージについては、『、 *『 MFC リファレンス*クラスのメンバー関数として`CWnd`名前が「オン」で始まる メンバー関数の宣言で`CWnd`が付きます。 **afx_msg**です。  
  
## <a name="see-also"></a>参照  
 [メッセージ ハンドラー関数の宣言](../mfc/declaring-message-handler-functions.md)
