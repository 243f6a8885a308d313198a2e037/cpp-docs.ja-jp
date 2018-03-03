---
title: "コンパイラ エラー C2346 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2346
dev_langs:
- C++
helpviewer_keywords:
- C2346
ms.assetid: 246145be-5645-4cd6-867c-e3bc39e33dca
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 769d5addc47ead8ffb338d5fbef313cd46735d31
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2346"></a>コンパイラ エラー C2346
'function' はネイティブとしてコンパイルできません: 理由  
  
 コンパイラは、MSIL に関数をコンパイルできませんでした。  
  
 詳細については、次を参照してください。[マネージ、アンマネージ](../../preprocessor/managed-unmanaged.md)と[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)です。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  MSIL にコンパイルすることはできません、関数内のコードを削除します。  
  
2.  いずれかのモジュールはコンパイルされません**/clr**、またはアンマネージのプラグマでアンマネージ関数をマークします。  
  
## <a name="example"></a>例  
 次の例では、C2346 を生成します。  
  
```  
// C2346.cpp  
// processor: x86  
// compile with: /clr   
// C2346 expected  
struct S  
{  
   S()  
   {  
      { __asm { nop } }  
   }  
   virtual __clrcall ~S() { }  
};  
  
void main()  
{  
   S s;  
}  
```