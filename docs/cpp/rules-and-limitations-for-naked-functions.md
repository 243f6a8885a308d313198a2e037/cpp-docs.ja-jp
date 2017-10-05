---
title: "Naked 関数の規則と制限 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- naked functions
ms.assetid: ff203858-2dd3-4a76-8a57-d0d06817adef
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: a02eb245ffae169f75f5d8edb261d0af9618856d
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="rules-and-limitations-for-naked-functions"></a>naked 関数の規則と制限
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 次の規則と制約が naked 関数に適用されます。  
  
-   `return` ステートメントは許可されていません。  
  
-   構造化例外処理コンストラクトと C++ の例外処理コンストラクトは、スタック フレームを越えてアンワインドする必要があるため許可されていません。  
  
-   同じ理由で、`setjmp` の形式は禁止されています。  
  
-   `_alloca` 関数の使用は禁止されています。  
  
-   プロローグ シーケンスの前にローカル変数の初期化コードが出現しないように、初期化されたローカル変数は関数のスコープ内では許可されません。 特に、C++ オブジェクトの宣言は関数のスコープでは許可されません。 ただし、入れ子になったスコープ内には初期化されたデータが含まれる場合があります。  
  
-   フレーム ポインター最適化 (/Oy コンパイラ オプション) は推奨されていませんが、naked 関数に対しては自動的に抑制されます。  
  
-   関数の構文スコープでは C++ クラス オブジェクトを宣言できません。 ただし、入れ子になったブロックではオブジェクトを宣言できます。  
  
-   `naked`でコンパイルするときに、キーワードは無視されます[/clr](../build/reference/clr-common-language-runtime-compilation.md)です。  
  
-   [_ _Fastcall](../cpp/fastcall.md) naked 関数は、レジスタ引数のいずれかにコードと C/C++ コードの参照があるたびに、プロローグ コードがその変数のスタックの場所にそのレジスタの値を格納する必要があります。 例:  
  
```  
// nkdfastcl.cpp  
// compile with: /c  
// processor: x86  
__declspec(naked) int __fastcall  power(int i, int j) {  
   // calculates i^j, assumes that j >= 0  
  
   // prolog  
   __asm {  
      push ebp  
      mov ebp, esp  
      sub esp, __LOCAL_SIZE  
     // store ECX and EDX into stack locations allocated for i and j  
     mov i, ecx  
     mov j, edx  
   }  
  
   {  
      int k = 1;   // return value  
      while (j-- > 0)   
         k *= i;  
      __asm {   
         mov eax, k   
      };  
   }  
  
   // epilog  
   __asm {  
      mov esp, ebp  
      pop ebp  
      ret  
   }  
}  
```  
  
**END Microsoft 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [naked 関数呼び出し](../cpp/naked-function-calls.md)
