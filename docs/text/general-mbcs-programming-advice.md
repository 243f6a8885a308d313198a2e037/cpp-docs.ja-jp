---
title: "一般的な MBCS プログラミングにおけるアドバイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _mbcs
dev_langs: C++
helpviewer_keywords:
- MBCS [C++], dialog box fonts
- MS Shell Dlg
- MBCS [C++], programming
- dialog boxes [C++], fonts
ms.assetid: 7b541235-f3e5-4af0-b2c2-a0112cd5fbfb
caps.latest.revision: "9"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a09bfb9b30e279e8d0b7696055c1e54ac56bfae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="general-mbcs-programming-advice"></a>MBCS プログラミングにおける一般的なアドバイス
次のヒントを使用します。  
  
-   柔軟性を高める場合など、実行時のマクロを使用して`_tcschr`と`_tcscpy`可能な場合です。 詳細については、次を参照してください。 [Tchar.h における汎用テキスト マッピング](../text/generic-text-mappings-in-tchar-h.md)です。  
  
-   C ランタイムを使用して`_getmbcp`を現在のコード ページに関する情報を取得します。  
  
-   文字列リソースを再利用しません。 言語によっては、ターゲットを指定する文字列に変換するときに、異なる意味があります。 たとえば、"File"で、アプリケーションのメイン メニューは、文字列"File" ダイアログ ボックスから異なる方法で変換可能性があります。 同じ名前の 2 つ以上の文字列を使用する必要がある場合は、ごとに異なる文字列 Id を使用します。  
  
-   Mbcs のオペレーティング システム、アプリケーションが実行されているかどうかを検索する場合があります。 これを行うプログラムの起動時にフラグを設定します。API 呼び出しに依存しません。  
  
-   ダイアログ ボックスをデザインする場合に、約 30% を許可する MBCS 変換用の静的テキスト コントロールの末尾に余分なスペースです。  
  
-   必ず、アプリケーションのフォントを選択するときに一部のフォントはすべてのシステムで利用できないためです。 たとえば、日本語版の Windows 2000 は Helvetica フォントをサポートしていません。  
  
-   ダイアログ ボックスのフォントを選択するを使用して[MS Shell Dlg](http://msdn.microsoft.com/library/windows/desktop/dd374112) MS Sans Serif や「helvetica」代わりにします。 MS Shell Dlg は適切なフォントに、ダイアログ ボックスを作成する前に、システムによって置換されます。 MS Shell Dlg を使用して、このフォントに対処するオペレーティング システムで変更が自動的に使用できることをによりします。 (MFC 置換 MS Shell Dlg DEFAULT_GUI_FONT または Windows 95、Windows 98、および Windows NT 4 で、システム フォントでこれらのシステムは MS Shell Dlg が正しく処理されないためです。)  
  
-   アプリケーションを設計するときに、どの言語で文字列をローカライズすることができますを決定します。 不明な場合に、すべての文字列をローカライズすることを想定しています。 そのため、混在させないでくださいローカライズ可能な文字列にすることはできません。  
  
## <a name="see-also"></a>参照  
 [MBCS のプログラミングについて](../text/mbcs-programming-tips.md)   
 [ポインターのインクリメントとデクリメント](../text/incrementing-and-decrementing-pointers.md)