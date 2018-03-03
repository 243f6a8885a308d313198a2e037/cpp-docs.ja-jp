---
title: "遅延読み込みする Dll を指定する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- DELAYLOAD linker option
- delayed loading of DLLs
- delayed loading of DLLs, specifying
- /DELAYLOAD linker option
ms.assetid: 94cbecfe-7a42-40d1-a618-9f2786bac0d8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d7c04b0885228bcef65b1b53cda6d28dc6755379
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="specifying-dlls-to-delay-load"></a>遅延読み込みする DLL の指定
遅延読み込みする Dll を指定することができます、 [/delayload](../../build/reference/delayload-delay-load-import.md):`dllname`リンカー オプション。 独自のバージョンのヘルパー関数を使う計画がない場合は、プログラムを delayimp.lib (デスクトップ アプリケーションの場合) または dloadhelper.lib (ストア アプリの場合) とリンクする必要もあります。  
  
 DLL の遅延読み込みの簡単な例を以下に示します。  
  
```  
// cl t.cpp user32.lib delayimp.lib  /link /DELAYLOAD:user32.dll  
#include <windows.h>  
// uncomment these lines to remove .libs from command line  
// #pragma comment(lib, "delayimp")  
// #pragma comment(lib, "user32")  
  
int main() {  
   // user32.dll will load at this point  
   MessageBox(NULL, "Hello", "Hello", MB_OK);  
}  
```  
  
 DEBUG バージョンのプロジェクトをビルドします。 デバッガーを使ってコードを段階的に実行すると、`MessageBox` に対する呼び出しを行なう場合のみ user32.dll が読み込まれることがわかります。  
  
## <a name="see-also"></a>参照  
 [リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)