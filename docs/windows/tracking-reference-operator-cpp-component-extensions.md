---
title: "演算子の追跡参照 (C++ コンポーネント拡張) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '%'
dev_langs:
- C++
helpviewer_keywords:
- tracking references
- '% tracking reference [C++]'
ms.assetid: 142a7269-ab69-4b54-a6d7-833bef06228f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 71389a622b02d5c0379b2be1a91783e8235077bb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="tracking-reference-operator-c-component-extensions"></a>参照演算子の追跡 (C++ コンポーネント拡張)
A*追跡参照*(`%`) 通常の C++ 参照のように動作 (`&`) オブジェクトの参照カウントがインクリメントされますが、オブジェクトが追跡参照に割り当てられている場合、します。  
  
## <a name="all-platforms"></a>すべてのプラットフォーム  
 追跡参照には次の特徴があります。  
  
-   オブジェクトを追跡参照に割り当てると、オブジェクトの参照カウントがインクリメントされます。  
  
-   ネイティブ参照 (&) は * を逆参照した結果です。 追跡参照 (%) は ^ を逆参照した結果です。 オブジェクトに対する % がある限り、そのオブジェクトはメモリに残り続けることになります。  
  
-   ドット (`.`) メンバー アクセス演算子は、オブジェクトのメンバーにアクセスするために使用されます。  
  
-   追跡参照は、値型およびハンドル (たとえば `String^`) に対して有効です。  
  
-   追跡参照に null 値または `nullptr` 値を割り当てることはできません。 追跡参照は、必要に応じて何度でも、別の有効なオブジェクトに再割り当てされる場合があります。  
  
-   追跡参照は、アドレスを受け取る単項演算子としては使用できません。  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 追跡参照は、% が参照カウントされている点を除くと、標準 C++ 参照のように動作します。 次のスニペットでは、% 型と ^ 型の間で変換を行う方法を示します。  
  
```  
Foo^ spFoo = ref new Foo();  
Foo% srFoo = *spFoo;  
Foo^ spFoo2 = %srFoo;  
```  
  
 次の例では、% を受け取る関数に ^ を渡す方法を示します。  
  
```  
  
ref class Foo sealed {};  
  
    // internal or private  
    void UseFooHelper(Foo% f)  
    {  
        auto x = %f;  
    }  
  
    // public method on ABI boundary  
    void UseFoo(Foo^ f)  
    {  
        if (f != nullptr) { UseFooHelper(*f); }  
    }  
```  
  
## <a name="common-language-runtime"></a>共通言語ランタイム 
 C++/CLI では、ガベージ コレクション ヒープ上の CLR 型オブジェクトにバインドする場合、ハンドルへの追跡参照を使用できます。  
  
 CLR では、ガベージ コレクターが参照先オブジェクトを移動させるたびに、追跡参照変数の値が自動的に更新されます。  
  
 追跡参照はスタック上でのみ宣言できます。 追跡参照をクラスのメンバーにすることはできません。  
  
 ガベージ コレクション ヒープ上のオブジェクトへのネイティブ C++ 参照を持つことはできません。  
  
 C++/CLI での追跡参照の詳細については、以下を参照してください。  
  
-   [方法: C++/CLI で追跡参照を使用する](../dotnet/how-to-use-tracking-references-in-cpp-cli.md)
  
### <a name="examples"></a>使用例  
 **例**  
  
 次の C++/CLI の例では、ネイティブ型およびマネージ型で追跡参照を使用する方法を示します。  
  
```  
// tracking_reference_1.cpp  
// compile with: /clr  
ref class MyClass {  
public:  
   int i;  
};  
  
value struct MyStruct {  
   int k;  
};  
  
int main() {  
   MyClass ^ x = ref new MyClass;  
   MyClass ^% y = x;   // tracking reference handle to reference object   
  
   int %ti = x->i;   // tracking reference to member of reference type  
  
   int j = 0;  
   int %tj = j;   // tracking reference to object on the stack  
  
   int * pi = new int[2];  
   int % ti2 = pi[0];   // tracking reference to object on native heap  
  
   int *% tpi = pi;   // tracking reference to native pointer  
  
   MyStruct ^ x2 = ref new MyStruct;  
   MyStruct ^% y2 = x2;   // tracking reference to value object  
  
   MyStruct z;  
   int %tk = z.k;   // tracking reference to member of value type  
  
   delete[] pi;  
}  
  
```  
  
 **例**  
  
 次の C++/CLI の例では、配列に追跡参照をバインドする方法を示します。  
  
```  
// tracking_reference_2.cpp  
// compile with: /clr  
using namespace System;  
  
int main() {  
   array<int> ^ a = ref new array< Int32 >(5);  
   a[0] = 21;  
   Console::WriteLine(a[0]);  
   array<int> ^% arr = a;  
   arr[0] = 222;  
   Console::WriteLine(a[0]);  
}  
```  
  
 **出力**  
  
```Output  
21  
222  
```