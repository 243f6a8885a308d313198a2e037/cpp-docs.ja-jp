---
title: "バッファリングの効果 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- buffers, effects of buffering
- buffering, effects of
ms.assetid: 5d544812-e95e-4f28-b15a-edef3f3414fd
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: e834b5be6b7d31d1f1516799462d57330bf4ceb2
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="effects-of-buffering"></a>バッファリングの効果
次に、バッファリングの効果を示す例を示します。 `please wait`を出力して 5 秒待ってから先に進むプログラムを想定することができますが、 必ずしもそのとおりに動作するとは限りません。これは、出力がバッファリングされるためです。  
  
```  
// effects_buffering.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <time.h>  
using namespace std;  
  
int main( )  
{  
   time_t tm = time( NULL ) + 5;  
   cout << "Please wait...";  
   while ( time( NULL ) < tm )  
      ;  
   cout << "\nAll done" << endl;  
}  
```  
  
 プログラムを論理的に動作させるには、メッセージが表示されたときに `cout` オブジェクトがそれ自体を空にする必要があります。 `ostream` オブジェクトをフラッシュするには、それを `flush` マニピュレーターに送信します。  
  
```  
cout <<"Please wait..." <<flush;  
```  
  
 この手順ではバッファーがフラッシュされるため、必ず待機の前にメッセージが出力されます。 使用することも、`endl`マニピュレーター、バッファーをフラッシュし、改行を出力するか、使用することができます、`cin`オブジェクト。 通常、このオブジェクト (および `cerr` または `clog` オブジェクト) は `cout` オブジェクトに関連付けられています。 そのため、 `cin` (あるいは `cerr` または `clog` オブジェクト) を使用すると、 `cout` オブジェクトがフラッシュされます。  
  
## <a name="see-also"></a>関連項目  
 [出力ストリーム](../standard-library/output-streams.md)


