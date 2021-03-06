---
title: バッファー オーバーフローが発生 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- buffers [C++], character sizes
- buffer overflows [C++]
- MBCS [C++], buffer overflow
ms.assetid: f2b7e40a-f02b-46d8-a449-51d26fc0c663
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9bb362be360986371200c8cde292b3fff5acd7cd
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020188"
---
# <a name="buffer-overflow"></a>バッファー オーバーフロー
文字のサイズを変更すると、バッファーに文字を配置するときに問題が発生することができます。 次のコードは、文字列から文字をコピー、 `sz`、バッファーに`rgch`:  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
    rgch[ cb++ ] = *sz++;  
```  
  
 質問: 最後のバイトが先行バイトをコピーしますか? 次は問題が解決しない、バッファー オーバーフローする可能性がある可能性があるため。  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 `_mbccpy`呼び出しが正しいことを行う試行-1 つまたは 2 バイトかどうかは、すべての文字をコピーします。 エントリの文字が 2 バイト幅の場合、コピーする最後の文字が、バッファーが適合しないアカウントにはなりません。 解決するには。  
  
```  
cb = 0;  
while( (cb + _mbclen( sz )) <= sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 このコードは、ループでバッファーのオーバーフローのテストを使用してテスト`_mbclen`によって示される現在の文字のサイズをテストする`sz`します。 呼び出すことによって、`_mbsnbcpy`関数のコードを置き換えることができます、**中**1 行のコードをループします。 例えば:  
  
```  
_mbsnbcpy( rgch, sz, sizeof( rgch ) );  
```  
  
## <a name="see-also"></a>関連項目  
 [MBCS のプログラミングについて](../text/mbcs-programming-tips.md)