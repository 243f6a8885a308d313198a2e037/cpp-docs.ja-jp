---
title: "Main に代わる wmain の使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- wmain
dev_langs:
- C++
helpviewer_keywords:
- main function, vs. wmain
- wmain function
ms.assetid: 7abb1257-b85c-413a-b913-d45b1582a71d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d43ab12c42315d735220af8f91c40d8b6a5cc4f9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="using-wmain-instead-of-main"></a>main に代わる wmain の使用
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 Unicode プログラミング モデルでは、**main** 関数のワイド文字バージョンを定義できます。 使用して**wmain**の代わりに**メイン**Unicode 仕様に準拠した移植可能なコードを記述する場合。  
  
 **wmain** に渡す仮引数は、**main** に渡す際の形式に準拠して宣言します。 さらに、ワイド文字の引数と、必要であればワイド文字環境ポインターもプログラムに渡すことができます。 **wmain** の引数 `argv` と `envp` の型は `wchar_t*` です。  
  
 プログラムで使用する場合、**メイン**関数の場合、マルチバイト文字環境がプログラムの起動時にオペレーティング システムによって作成します。 必要な場合にのみ、ワイド文字環境のコピーが作成された (への呼び出しなどにより、 [_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)または[_wputenv](../c-runtime-library/reference/putenv-wputenv.md)関数)。 `_wputenv` を最初に呼び出すとき、または MBCS 環境が既に存在する場合に `_wgetenv` を最初に呼び出すとき、対応するワイド文字列環境が作成され、その後は作成されたワイド文字列環境が `_wenviron` グローバル変数 (`_environ` グローバル変数のワイド文字バージョン) によって参照されます。 この時点までで、2 つの環境のコピー (MBCS および Unicode) が同時に存在していることになるわけですが、両方ともプログラムが消滅するまでオペレーティング システムによって保持されます。  
  
 同様に、プログラムで使用する場合、 **wmain**関数、MBCS (ASCII) 環境が作成される最初の呼び出しで`_putenv`または`getenv`、によって指されると、`_environ`グローバル変数。  
  
 MBCS 環境の詳細については、次を参照してください。[シングル バイト文字とマルチバイト文字セット](../c-runtime-library/single-byte-and-multibyte-character-sets.md)で、*ランタイム ライブラリ リファレンスです。*  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [main: プログラムの起動](../cpp/main-program-startup.md)