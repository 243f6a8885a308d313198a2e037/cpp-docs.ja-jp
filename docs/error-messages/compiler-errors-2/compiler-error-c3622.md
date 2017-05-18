---
title: "コンパイラ エラー C3622 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3622
dev_langs:
- C++
helpviewer_keywords:
- C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
caps.latest.revision: 11
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: ed81cc21e3c3ae574a0c83a692f75638d24111de
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3622"></a>コンパイラ エラー C3622
'class': 'キーワード' をインスタンス化できないように宣言されたクラス  
  
としてマークされたクラスをインスタンス化が試み[抽象](../../windows/abstract-cpp-component-extensions.md)します。 クラスととしてマークした`abstract`基本クラスを指定できますが、インスタンス化することはできません。  
  
## <a name="example"></a>例  
次の例では、c3622 エラーを生成します。  
  
```  
// C3622.cpp  
// compile with: /clr  
ref class a abstract {};  
  
int main() {  
   a aa;   // C3622  
}  
```  
