---
title: '方法: ボックス化を明示的に要求 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- boxing, explicitly requesting
ms.assetid: 1359e6e5-162d-4f5d-9b6a-1690d93df3ee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4bf869fc8742f25155a8963cd03b9a7aba571ed4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33127345"
---
# <a name="how-to-explicitly-request-boxing"></a>方法: 明示的にボックス化を要求する
型の変数に変数を割り当てることでボックス化を明示的に要求できます`Object`です。  
  
## <a name="example"></a>例  
  
```  
// vcmcppv2_explicit_boxing3.cpp  
// compile with: /clr  
using namespace System;  
  
void f(int i) {  
   Console::WriteLine("f(int i)");  
}  
  
void f(Object ^o) {  
   Console::WriteLine("f(Object^ o)");  
}  
  
int main() {  
   int i = 5;  
   Object ^ O = i;   // forces i to be boxed  
   f(i);  
   f(O);  
   f( (Object^)i );  // boxes i  
}  
```  
  
```Output  
f(int i)  
f(Object^ o)  
f(Object^ o)  
```  
  
## <a name="see-also"></a>関連項目  
 [ボックス化](../windows/boxing-cpp-component-extensions.md)