---
title: "_ _vmx_vmread |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __vmx_vmread
dev_langs: C++
helpviewer_keywords:
- VMREAD instruction
- __vmx_vmread intrinsic
ms.assetid: 08bdd7a0-6435-4ea6-b9a0-f592d870e5aa
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2ff3bfba5409715f2e5022e62dd74fa94360d10b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="vmxvmread"></a>__vmx_vmread
**Microsoft 固有の仕様**  
  
 現在仮想マシン制御構造 (VMCS) から、指定したフィールドを読み取り、指定した場所に配置します。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned char __vmx_vmread(  
   size_t Field,  
   size_t *FieldValue  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `Field`|読み取る VMCS のフィールドです。|  
|[入力] `FieldValue`|指定された VMCS フィールドから値を格納する場所へのポインターの読み取り、`Field`パラメーター。|  
  
## <a name="return-value"></a>戻り値  
  
|値|説明|  
|-----------|-------------|  
|0|操作が成功しました。|  
|1|現在 VMCS の `VM-instruction error field` で有効な拡張状態が発生したため、操作は失敗しました。|  
|2|有効な状態がないため操作は失敗しました。|  
  
## <a name="remarks"></a>コメント  
 `__vmx_vmread`関数と同じ、`VMREAD`マシン語命令します。 値、`Field`パラメーターは、Intel のドキュメントに記載されているエンコードのフィールドのインデックス。 詳細については、「Intel 仮想化技術仕様の「ia-32 Intel アーキテクチャ」、ドキュメントの検索に番号 C97063 002 を文書化、 [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127)サイト、し、そのドキュメントの「付録 C を参照してください.  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__vmx_vmread`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmwrite](../intrinsics/vmx-vmwrite.md)