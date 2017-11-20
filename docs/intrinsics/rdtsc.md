---
title: "_ _rdtsc |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __rdtsc
dev_langs: C++
helpviewer_keywords:
- __rdtsc intrinsic
- rdtsc instruction
- Read Time Stamp Counter instruction
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fa161bcc1845ab058773ca8ebdecfb5233235e54
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="rdtsc"></a>__rdtsc
**Microsoft 固有の仕様**  
  
 生成、`rdtsc`命令で、プロセッサのタイムスタンプを返します。 プロセッサのタイムスタンプは、最後のリセット以後のクロック サイクル数を記録します。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned __int64 __rdtsc();  
```  
  
## <a name="return-value"></a>戻り値  
 ティック カウントを表す 64 ビット符号なし整数。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__rdtsc`|x86、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 このルーチンは、組み込みとしてのみ使用できます。  
  
 この世代のハードウェアで TSC 値の解釈が異なる以前のバージョンの[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]します。 詳細についてはハードウェアのマニュアルを参照してください。  
  
## <a name="example"></a>例  
  
```  
// rdtsc.cpp  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__rdtsc)  
  
int main()  
{  
    unsigned __int64 i;  
    i = __rdtsc();  
    printf_s("%I64d ticks\n", i);  
}  
```  
  
```Output  
3363423610155519 ticks  
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)