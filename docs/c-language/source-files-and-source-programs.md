---
title: "ソース ファイルとソース プログラム | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ファイル [C++], source"
  - "プログラム [C++], source"
  - "ソース ファイル, 指定 (コンパイラで)"
  - "ソース プログラム"
ms.assetid: 18bb2826-17da-48e5-92a2-10e649f1bc9f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# ソース ファイルとソース プログラム
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ソース プログラムは、1 つ以上の "ソース ファイル" または "翻訳単位" に分割できます。 コンパイラへの入力は "翻訳単位" と呼ばれます。  
  
## 構文  
 *translation\-unit*:  
 *external\-declaration*  
  
 *translation\-unit external\-declaration*  
  
 *external\-declaration*:  
 *function\-definition*  
  
 *declaration*  
  
 「[宣言の概要](../Topic/Overview%20of%20Declarations.md)」では、非終端要素である `declaration` の構文を示します。『プリプロセッサ リファレンス』では、[翻訳単位](../preprocessor/phases-of-translation.md)の処理方法について説明します。  
  
> [!NOTE]
>  ANSI 構文規則については、「[C 言語の構文の概要](../c-language/c-language-syntax-summary.md)」の説明を参照してください。  
  
 翻訳単位の構成要素は、関数定義および識別子宣言を含む外部宣言です。  これらの宣言と定義は、ソース ファイル、ヘッダー ファイル、ライブラリなど、プログラムが必要とするファイルに含めることができます。  各翻訳単位をコンパイルし、結果のオブジェクト ファイルをリンクして、プログラムを作成する必要があります。  
  
 C の "ソース プログラム" は、ディレクティブ、プラグマ、宣言、定義、ステートメント ブロック、および関数のコレクションです。  Microsoft C プログラムの有効な構成要素であるためには、それぞれがこのブックで説明された構文に従う必要があります。ただし、プログラム内で登場する順序は任意です \(このブック全体で示された規則に従います\)。  ただし、これらの構成要素の場所は、変数と関数がプログラムでどのように使用されるかに影響します  \(詳細については、「[有効期間、スコープ、可視性、およびリンケージ](../Topic/Lifetime,%20Scope,%20Visibility,%20and%20Linkage.md)」を参照してください\)。  
  
 ソース ファイルは、実行可能なステートメントを含む必要はありません。  たとえば、変数の定義を 1 つのソース ファイルに置き、これらの変数を使用する他のソース ファイルでこれらの変数への参照を宣言すると便利な場合があります。  この手法により、必要なときに簡単に定義を見つけて更新できるようになります。  同じ理由から、定数およびマクロは、ソース ファイルで必要に応じて参照できる "インクルード ファイル" または "ヘッダー ファイル" という名前の別個のファイルにまとめることがよくあります。  [マクロ](../Topic/Macros%20\(C-C++\).md)および[インクルード ファイル](../preprocessor/hash-include-directive-c-cpp.md)については、『プリプロセッサ リファレンス』の説明を参照してください。  
  
## 参照  
 [プログラムの構造](../c-language/program-structure.md)