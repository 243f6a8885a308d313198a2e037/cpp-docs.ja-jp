---
title: "モジュール定義ステートメントに関する規則 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .def
dev_langs: C++
helpviewer_keywords:
- module definition files, statement syntax
- module definition files
ms.assetid: f65cd3a7-65d7-4d06-939f-a8b1ecd50f2d
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 40eb4875b195871aff8d274667e005d63424a110
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="rules-for-module-definition-statements"></a>モジュール定義ステートメントに関する規則
次の構文規則は、.def ファイル内のすべてのステートメントに適用されます。 特定のステートメントに適用されるその他の規則は、それぞれのステートメントについて説明します。  
  
-   ステートメント、属性のキーワード、およびユーザー指定の識別子は大文字小文字を区別します。  
  
-   長いファイル名を空白またはセミコロン (;) を格納している引用符 (") で囲む必要があります。  
  
-   ステートメントのキーワードを引数に区別するため、個々 のステートメントを区切るために、スペース、タブ、または改行文字の 1 つまたは複数を使用します。 コロン (:) または等号 (=) の引数を指定するは、0 以上のスペース、タブ、または改行文字で囲まれています。  
  
-   A**名前**または**ライブラリ**ステートメントでは、使用する場合の他のすべてのステートメント必要があります前にします。  
  
-   **セクション**と**エクスポート**.def ファイル内のステートメントが複数回使用できます。 各ステートメントでは、複数の仕様は、1 つ以上のスペース、タブ、または改行文字で区切る必要を実行できます。 ステートメントのキーワードでは、最初の指定の前に 1 回指定する必要があり、各追加の指定の前に繰り返すことができます。  
  
-   多くのステートメントでは、同等のリンク コマンド ライン オプションがあります。 追加の詳細について、対応するリンク オプションの説明を参照してください。  
  
-   .Def ファイル内のコメントはセミコロン (;) で指定されているそれぞれのコメント行の先頭にします。 コメントはステートメントでは、回線を共有することはできませんが、複数行のステートメントの仕様を区切ることができます。 (**セクション**と**エクスポート**複数行のステートメントします)。  
  
-   数値の引数が 10 進数で指定されているか、16 進数です。  
  
-   文字列引数に一致する場合、[予約語](../../build/reference/reserved-words.md)、二重引用符 (") で囲む必要があります。  
  
## <a name="see-also"></a>参照  
 [モジュール定義 (.def) ファイル](../../build/reference/module-definition-dot-def-files.md)  