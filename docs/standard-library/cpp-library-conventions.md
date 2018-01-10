---
title: "C++ ライブラリの規則 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- C++ Standard Library, conventions
- classes [C++]
- functions [C++], library naming conventions
- naming conventions [C++], C++ Standard Library
- conventions [C++], C++ Standard Library
- function names [C++]
- coding conventions, C++ Standard Library
- naming conventions [C++], C++ library
ms.assetid: bf41b79a-2d53-4f46-8d05-779358335146
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0699e589340081d5dd13e8ab879094445005e327
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="c-library-conventions"></a>C++ ライブラリの規則
C++ ライブラリは、標準 C ライブラリとほとんど同じ規則に従い、ここで説明するいくつかの追加事項があります。  
  
 実装では、C++ ライブラリでの型と関数の宣言方法にある程度の自由さがあります。  
  
-   標準 C ライブラリでの関数の名前は、 extern #"C++" または extern "C" リンケージです。 ライブラリ エンティティをインラインで宣言するのではなく、適切な標準 C ヘッダーをインクルードします。  
  
-   ライブラリ クラスのメンバー関数名には、このドキュメントに記載されているものに対する追加の関数シグネチャが存在する場合があります。 ここで説明されている関数呼び出しは期待したとおりに動作しますが、ライブラリ メンバー関数のアドレスを確実に取得することはできません (型が予想したものではない場合があります)。  
  
-   ライブラリのクラスには、ドキュメント化されていない (非仮想の) 基底クラスが存在する場合あります。 別のクラスから派生するように記載されているクラスは、実際には、他のドキュメントになっていクラスを通じて、そのクラスから派生されることがあります。  
  
-   一部の整数型に対してシノニムと定義されている型は、複数の異なる整数型の 1 つと同じである場合があります。  
  
-   ビットマスク型は、整数型または列挙型のいずれかとして実装することができます。 いずれの場合も、同じビットマスク型の値に対してビットごとの演算 (`AND` や `OR` など) を行うことができます。 ビットマスク型の要素 `A` と `B` は、`A` & `B` がゼロであるようなゼロ以外の値です。  
  
-   例外の指定がないライブラリ関数は、その定義で可能性が明確に制限されていない限り、任意の例外をスローできます。  
  
 一方で、いくつかの制限があります。  
  
-   標準 C ライブラリは、マスク マクロを使用しません。 関数自体の名前ではなく、特定の関数のシグネチャのみが予約されています。  
  
-   クラスに含まれないライブラリ関数名には、文書化されていない追加の関数シグネチャはありません。 そのアドレスを確実に取得できます。  
  
-   仮想として記述されている基底クラスとメンバー関数は確実に仮想であり、非仮想として記述されているものは確実に非仮想です。  
  
-   C++ ライブラリによって定義されている 2 つの型は、このドキュメントで明示的に指摘されていない限り、常に異なるものです。  
  
-   置き換え可能な関数の既定バージョンを含む、ライブラリで提供されている関数は、*最も多い場合でで*、例外の指定に列記されている例外をスローする可能性があります。 ライブラリによって提供されるデストラクターは例外をスローしません。 `qsort` が例外をスローする比較関数を呼び出すときのように、標準 C ライブラリの関数は例外を伝播することがありますが、それ以外の場合は例外をスローしません。  
  
## <a name="see-also"></a>参照  
 [C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)

