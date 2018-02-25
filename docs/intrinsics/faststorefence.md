---
title: "_ _faststorefence の |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __faststorefence_cpp
- __faststorefence
dev_langs:
- C++
helpviewer_keywords:
- __faststorefence intrinsic
- sfence instruction
ms.assetid: 6c6eb973-3cf0-4306-b3af-cfde9b0210a5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 70999adc4bba03b3a8b00ad10330b18c68695af8
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="faststorefence"></a>__faststorefence
**Microsoft 固有の仕様**  
  
 メモリ参照の読み込みと格納の両方を含む、以前の各メモリ参照が、後続のメモリ参照の前に全体に対して参照可能になっていることを保証します。  
  
## <a name="syntax"></a>構文  
  
```  
void __faststorefence();  
```  
  
## <a name="requirements"></a>必要条件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__faststorefence`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 この組み込みの前に発生した読み込みおよび格納操作が、実行が続行する前に全体に対して参照可能になっていることを保証する、完全なメモリ バリアの命令シーケンスを生成します。 効果は、すべての x64 プラットフォームにおける `_mm_mfence` の組み込みと同等ですが、それよりも高速になります。  
  
 AMD64 プラットフォームでは、このルーチンは、`sfence` 命令よりも高速なストア フェンスである命令を生成します。 タイム クリティカル コードでは、`_mm_sfence` ではなくこの組み込みを使用します (AMD64 プラットフォームのみ)。 Intel x64 プラットフォームでは、 `_mm_sfence` 命令は高速化します。  
  
 このルーチンは、組み込みとしてのみ使用できます。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)