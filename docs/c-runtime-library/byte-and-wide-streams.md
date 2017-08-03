---
title: "バイト ストリームとワイド ストリーム | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Byte and Wide Streams
dev_langs:
- C++
helpviewer_keywords:
- byte streams
- wide streams
ms.assetid: 61ef0587-4cbc-4eb8-aae5-4c298dbbc6f9
caps.latest.revision: 8
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
ms.openlocfilehash: c916caf1ee0b39567813921401ee02cbda83d222
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="byte-and-wide-streams"></a>バイト ストリームとワイド ストリーム
バイト ストリームはバイトのシーケンスとしてファイルを扱います。 プログラム内で、ストリームは、同じバイトのシーケンスです。  
  
 これに対しワイド ストリームは、さまざまなエンコードの規則を持つことができる、汎用のマルチバイト文字のシーケンスとしてファイルを扱います。 (テキスト ファイルとバイナリ ファイルは、それでも、既に説明したように読み取りと書き込みが行われます。)プログラム内で、ストリームは、対応するワイド文字のシーケンスのように見えます。 2 つの表現の間の変換は、標準 C ライブラリ内で行われます。 変換規則は、原則として、カテゴリ `LC_CTYPE` を変更する [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) の呼び出しによって変更できます。 各ワイド ストリームでは、ワイド指向になるときにその変換規則が決定され、以降にカテゴリ `LC_CTYPE` が変更されてもこれらの規則が保持されます。  
  
 ワイド ストリーム内の位置決めは、テキスト ストリームと同じ制約を受けます。 さらに、ファイル位置インジケーターで状態依存のエンコードに対処する必要が生じることもあります。 通常は、ストリーム内のバイト オフセットと `mbstate_t` 型のオブジェクトの両方が含まれます。 したがって、ワイド ストリーム内のファイル位置を取得する唯一の信頼できる方法は、[fgetpos](../c-runtime-library/reference/fgetpos.md) を呼び出すことであり、この方法で取得した位置を元に戻すの信頼できる方法は、[fsetpos](../c-runtime-library/reference/fsetpos.md) を呼び出すことです。  
  
## <a name="see-also"></a>関連項目  
 [ファイルとストリーム](../c-runtime-library/files-and-streams.md)   
 [setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)
