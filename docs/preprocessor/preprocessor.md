---
title: "プリプロセッサ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor
ms.assetid: e120eda3-b413-49f1-a07c-e9fb128cf500
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 75caab67343e7806e1dd97fb673114949c68a94c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="preprocessor"></a>プリプロセッサ
プリプロセッサは、変換の第 1 段階としてソース ファイルのテキストを操作するテキスト プロセッサです。 プリプロセッサは、ソース テキストを解析しませんが、マクロの呼び出しを特定する目的でトークンに分割します。 コンパイラは通常、最初のパスでプリプロセッサを呼び出しますが、コンパイルすることなくテキストを処理するために個別にプリプロセッサを呼び出すことができます。  
  
 プリプロセッサのリファレンス資料として、次のセクションを参照してください。  
  
-   [プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)  
  
-   [プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)  
  
-   [定義済みマクロ](../preprocessor/predefined-macros.md)  
  
-   [プラグマ](../preprocessor/pragma-directives-and-the-pragma-keyword.md)  
  
 **Microsoft 固有の仕様**  
  
 使用して前処理した後、ソース コードの一覧を取得することができます、 [/E](../build/reference/e-preprocess-to-stdout.md)または[/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)コンパイラ オプション。 両オプション共に、プリプロセッサを呼び出し、生成されるテキストを標準出力デバイス (ほとんどの場合、コンソール) に出力します。 2 つのオプション間の違いは、/E では `#line` ディレクティブが含まれ、/EP ではこうしたディレクティブが削除されることです。  
  
 **Microsoft 固有の仕様はここまで**  
  
##  <a name="_predir_special_terminology"></a> 特別な用語  
 プリプロセッサのドキュメントでは、"引数" という用語は、関数に渡されるエンティティを意味します。 場合によっては、関数呼び出しで指定される引数式、および関数定義で指定される引数宣言をそれぞれ表す "実" または "仮" を修飾として先頭に付けることがあります。  
  
 "変数" という用語は、簡単な C 型のデータ オブジェクトを意味します。 "オブジェクト" は、C++ オブジェクトおよび変数の両方を意味する包括的な用語です。  
  
## <a name="see-also"></a>参照  
 [C/C++ プリプロセッサ リファレンス](../preprocessor/c-cpp-preprocessor-reference.md)   
 [変換フェーズ](../preprocessor/phases-of-translation.md)