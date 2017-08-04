---
title: "__argc、__argv、__wargv | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __wargv
- __argv
- __argc
apilocation:
- msvcrt120.dll
apitype: DLLExport
f1_keywords:
- __argv
- __argc
- __wargv
dev_langs:
- C++
helpviewer_keywords:
- __argv
- __wargv
- __argc
ms.assetid: 17001b0a-04ad-4762-b3a6-c54847f02d7c
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 1141b9fefd1a42a3ee8a84c8ea24e1d3996329d8
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="argc-argv-wargv"></a>__argc、__argv、__wargv
`__argc` グローバル変数は、プログラムに渡されるコマンド ライン引数の数です。 `__argv` は、プログラム引数を含む 1 バイト文字列またはマルチバイト文字列の配列へのポインターです。`__wargv` は、プログラム引数を含むワイド文字列の配列へのポインターです。 これらのグローバル変数によって、`main` または `wmain` に引数が提供されます。  
  
## <a name="syntax"></a>構文  
  
```  
extern int __argc;  
extern char ** __argv;  
extern wchar_t ** __wargv;  
```  
  
## <a name="remarks"></a>コメント  
 `main` 関数を使用するプログラムでは、`__argc` および `__argv` は、プログラムの起動に使用されるコマンド ラインを使用してプログラムの起動時に初期化されます。 コマンド ラインは解析されて個々の引数になり、ワイルドカードは展開されます。 引数の数は `__argc` に代入され、引数の文字列はヒープ上に割り当てられ、引数の配列へのポインターは `__argv` に代入されます。 ワイド文字および `wmain` 関数を使用するようにコンパイルされたプログラムでは、ワイド文字列として引数は解析されワイルドカードは展開されて、引数の文字列の配列へのポインターは `__wargv` に代入されます。  
  
 移植性のあるコードの場合、`main` に渡される引数を使用してプログラムでコマンド ライン引数を取得することをお勧めします。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE が未定義の場合|_UNICODE が定義されている場合|  
|---------------------|---------------------------|-----------------------|  
|`__targv`|`__argv`|`__wargv`|  
  
## <a name="requirements"></a>要件  
  
|グローバル変数|必須ヘッダー|  
|---------------------|---------------------|  
|`__argc`、`__argv`、`__wargv`|\<stdlib.h>、\<cstdlib> (C++)|  
  
 `__argc`、`__argv`、および `__wargv` は Microsoft 拡張機能です。 互換性の詳細については、「[互換性](../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [グローバル変数](../c-runtime-library/global-variables.md)   
 [main: プログラムの起動](../cpp/main-program-startup.md)   
 [main に代わる wmain の使用](../cpp/using-wmain-instead-of-main.md)
