---
title: "TOOLTIPTEXT 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TOOLTIPTEXT
dev_langs:
- C++
helpviewer_keywords:
- TOOLTIPTEXT structure [MFC]
- tool tips [MFC], notifications
ms.assetid: 547591bf-80f5-400e-a2a7-0708cfffbb5d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: becbdcfcc6dbd26ae3095de098d12dbc078530cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="tooltiptext-structure"></a>TOOLTIPTEXT 構造体
書き込みで、[ツール ヒントの通知ハンドラー](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)を使用する必要があります、`TOOLTIPTEXT`構造体。 メンバー、`TOOLTIPTEXT`構造は。  
  
 `typedef struct {`  
  
 `NMHDR     hdr;        // required for all WM_NOTIFY messages`  
  
 `LPTSTR    lpszText;   // see below`  
  
 `TCHAR     szText[80]; // buffer for tool tip text`  
  
 `HINSTANCE hinst;      // see below`  
  
 `UINT      uflags;     // flag indicating how to interpret the`  
  
 `// idFrom member of the NMHDR structure`  
  
 `// that is included in the structure`  
  
 `} TOOLTIPTEXT, FAR *LPTOOLTIPTEXT;`  
  
 `hdr`  
 テキストを必要とするツールを識別します。 必要に応じてこの構造体の唯一のメンバーは、コントロールのコマンド id です。 コントロールのコマンド ID ができるように、`idFrom`のメンバー、`NMHDR`構造体、構文を使用してアクセス`hdr.idFrom`です。 参照してください[NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514)用のメンバーの詳細については、`NMHDR`構造体。  
  
 `lpszText`  
 ツールは、テキストを受け取る文字列のアドレス。  
  
 `szText`  
 ツール ヒントのテキストを受け取るバッファー。 アプリケーションは、文字列のアドレスを指定する代わりに、このバッファーにテキストをコピーできます。  
  
 `hinst`  
 ツール ヒントのテキストとして使用する文字列が含まれているインスタンスのハンドルです。 場合`lpszText`アドレスは、ツール ヒントのテキストのこのメンバーは NULL です。  
  
 処理するときに、`TTN_NEEDTEXT`通知メッセージで、次の方法のいずれかで表示される文字列を指定します。  
  
-   指定されたバッファーにテキストをコピー、`szText`メンバー。  
  
-   テキストを含むバッファーのアドレスをコピー、`lpszText`メンバー。  
  
-   文字列リソースの識別子をコピー、`lpszText`メンバー、およびコピーするリソースを含むインスタンスのハンドル、`hinst`メンバー。  
  
## <a name="see-also"></a>参照  
 [CFrameWnd から派生していないウィンドウのツール ヒント](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

