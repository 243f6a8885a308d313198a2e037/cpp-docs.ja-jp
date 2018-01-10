---
title: "リッチ エディット コントロールでの印刷 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- printing [MFC], CRichEditCtrl
- rich edit controls [MFC], printing
- CRichEditCtrl class [MFC], printing
ms.assetid: dbda0e40-018f-424e-b5d8-7b489aaf27af
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ab8e15e25e2d419bb7c3ac67fc2c6f3453fb03c4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="printing-in-rich-edit-controls"></a>リッチ エディット コントロールでの印刷
リッチ エディット コントロールに指示することができます ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) プリンターなどの指定したデバイスの出力を表示するためにします。 出力デバイスをリッチ エディット コントロールがそのテキストを書式設定を指定することもできます。  
  
 特定のデバイスのリッチ エディット コントロールの内容の一部をフォーマットするには、使用することができます、 [FormatRange](../mfc/reference/cricheditctrl-class.md#formatrange)メンバー関数。 [FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787911)この関数で使用される構造体は、ターゲット デバイスのデバイス コンテキスト (DC) および書式設定テキストの範囲を指定します。  
  
 出力デバイス用のテキストを書式設定後にことができます、出力を送信するデバイスを使用して、[続いて](../mfc/reference/cricheditctrl-class.md#displayband)メンバー関数。 繰り返しを使用して`FormatRange`と`DisplayBand`、縞模様、リッチ エディット コントロールの内容を出力するアプリケーションで実装できます。 (縞模様は出力の小さな部分に分割印刷の目的で) です。  
  
 使用することができます、 [SetTargetDevice](../mfc/reference/cricheditctrl-class.md#settargetdevice)リッチ エディット コントロールを対象のターゲット デバイスを指定するメンバー関数は、そのテキストを書式設定します。 この関数は、WYSIWYG に役立つ (表示) 書式設定、アプリケーションが、画面の代わりに既定のプリンターのフォント メトリックを使用してテキストを配置します。  
  
## <a name="see-also"></a>参照  
 [CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

