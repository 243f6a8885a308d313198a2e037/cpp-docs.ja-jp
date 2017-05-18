---
title: "コンパイラ エラー C3270 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3270
dev_langs:
- C++
helpviewer_keywords:
- C3270
ms.assetid: 70e6e76b-7415-48f5-a61e-2ed50caf08e4
caps.latest.revision: 8
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 13ef4bca19de5b1dcda8fd0c22a15d43f00257b7
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3270"></a>コンパイラ エラー C3270
'field': FieldOffset 属性は、必要な場合は StructLayout(Explicit) のコンテキストでのみ使用できます  
  
フィールドに指定された**FieldOffset**、いる時のみ許可**StructLayout(Explicit)**有効にします。  
  
次の例では C3270 が生成されます。  
  
```  
// C3270_2.cpp  
// compile with: /clr /c  
using namespace System::Runtime::InteropServices;  
  
[ StructLayout(LayoutKind::Sequential) ]  
// try the following line instead  
// [ StructLayout(LayoutKind::Explicit) ]  
public value struct MYUNION  
{  
   [FieldOffset(0)] int a;   // C3270  
   // ...  
};  
```  
