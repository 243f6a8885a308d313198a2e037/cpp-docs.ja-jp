---
title: "hdrstop |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- hdrstop_CPP
- vc-pragma.hdrstop
dev_langs: C++
helpviewer_keywords:
- hdrstop pragma
- pragmas, hdrstop
ms.assetid: 5ea8370a-10d1-4538-ade6-4c841185da0e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cf1bd1d80f692695c1cbf4ad535d2c5e759e4ea5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="hdrstop"></a>hdrstop
プリコンパイル ファイル名およびコンパイル状態が保存される場所に対する追加の制御を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
#pragma hdrstop [( "filename" )]    
```  
  
## <a name="remarks"></a>コメント  
 *Filename*使用または作成するプリコンパイル済みヘッダー ファイルの名前を指定します (かどうかに応じて[/Yu](../build/reference/yu-use-precompiled-header-file.md)または[/Yc](../build/reference/yc-create-precompiled-header-file.md)が指定されている)。 場合*filename*パスの指定が含まれていない、プリコンパイル済みヘッダー ファイルがソース ファイルと同じディレクトリにあると見なされます。  
  
 C または C++ ファイルが含まれている場合、 **hdrstop**プラグマ/Yc でコンパイルした場合、コンパイラは、プラグマの位置までコンパイルの状態を保存します。 プラグマの後ろにあるコードのコンパイル状態は保存されません。  
  
 使用して*filename*コンパイル済みの状態が保存されるプリコンパイル済みヘッダー ファイルの名前。 間にスペース**hdrstop**と*filename*は省略可能です。 指定されたファイル名、 **hdrstop**プラグマ文字列は、そのため、C または C++ の文字列の制約を受けます。 具体的には、文字列を引用符で囲み、エスケープ文字 (円記号) を使用してディレクトリ名を指定する必要があります。 例:  
  
```  
#pragma hdrstop( "c:\\projects\\include\\myinc.pch" )  
```  
  
 プリコンパイルされたヘッダー ファイルの名前は、次の規則 (優先度順に表示) に従って決定されます。  
  
1.  /Fp コンパイラ オプションの引数  
  
2.  *Filename* # 引数**プラグマ hdrstop**  
  
3.  拡張子 .PCH を持つソース ファイルのベース名  
  
 /Yc および/Yu オプションで、次の 2 つのコンパイル オプションのどちらも、また**hdrstop**プラグマ ファイルの名前を指定する、ソース ファイルの基本名が、プリコンパイル済みヘッダー ファイルのベース名として使用します。  
  
 また、次のように、プリプロセス コマンドを使用してマクロ置換を実行することもできます。  
  
```  
#define INCLUDE_PATH "c:\\progra~`1\\devstsu~1\\vc\\include\\"  
#define PCH_FNAME "PROG.PCH"  
.  
.  
.  
#pragma hdrstop( INCLUDE_PATH PCH_FNAME )  
```  
  
 次の規則は、where、 **hdrstop**プラグマを配置することができます。  
  
-   すべてのデータ宣言、関数宣言、および定義の外にある必要があります。  
  
-   ヘッダー ファイルにではなく、ソース ファイルに指定する必要があります。  
  
## <a name="example"></a>例  
  
```  
#include <windows.h>                 // Include several files  
#include "myhdr.h"  
  
__inline Disp( char *szToDisplay )   // Define an inline function  
{  
    ...                              // Some code to display string  
}  
#pragma hdrstop  
```  
  
 この例では、 **hdrstop**プラグマは、2 つのファイルが含まれています、インライン関数が定義されている後に表示されます。 初めは、プラグマの位置が不自然に見えるかもしれません。 、ただし、その使用を検討して、手動プリコンパイル オプション/Yc および/Yu、で、 **hdrstop**プラグマにより、ソース ファイル全体をプリコンパイルする — インライン コードも含みます。 Microsoft コンパイラでは、データ宣言以外のプリコンパイルも実行できます。  
  
## <a name="see-also"></a>参照  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)