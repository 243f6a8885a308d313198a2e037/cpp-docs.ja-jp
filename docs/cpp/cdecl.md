---
title: "_ _cdecl |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __cdecl
- __cdecl_cpp
dev_langs:
- C++
helpviewer_keywords:
- __cdecl keyword [C++]
ms.assetid: 1ff1d03e-fb4e-4562-8be1-74f1ad6427f1
caps.latest.revision: 16
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
ms.openlocfilehash: 5216462ad00d332aec2d00eba78f5d84cdfd7c82
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="cdecl"></a>__cdecl
**Microsoft 固有の仕様**  
  
 `__cdecl` は、C および C++ プログラムの既定の呼び出し規約です。 実行できるため、呼び出し元によって、スタックがクリーンアップ**vararg**関数。 `__cdecl`よりも大きな実行可能ファイルを作成する呼び出し規約[_ _stdcall](../cpp/stdcall.md)、各関数呼び出しにスタック クリーンアップ コードを含める必要があります。 次の一覧は、この呼び出し規則の実装例を示しています。  
  
|要素|実装|  
|-------------|--------------------|  
|引数を渡す順序|右から左。|  
|スタック メンテナンスの役割|呼び出し元の関数によって、スタックから引数がポップされます。|  
|名前装飾規約|アンダー スコア文字 (_) は、名前の先頭に、場合を除き\_C リンケージを使用する _cdecl 関数がエクスポートされます。|  
|大文字と小文字の変換規約|大文字小文字は変換されません。|  
  
> [!NOTE]
>  関連情報については、次を参照してください。[装飾名](../build/reference/decorated-names.md)です。  
  
 変数名または関数名の前に `__cdecl` 修飾子を置きます。 C の名前と呼び出し規則は、既定値であるためにのみ行う必要があります`__cdecl`x86 コードで指定したときに、 **/Gv** (vectorcall)、 **/Gz** (stdcall)、または**/Gr** (fastcall) コンパイラ オプション。 [/Gd](../build/reference/gd-gr-gv-gz-calling-convention.md)コンパイラ オプションの強制、`__cdecl`呼び出し規約です。  
  
 ARM と x64 のプロセッサでは、`__cdecl` はコンパイラによって受け入れられますが、通常は無視されます。 ARM と x64 の規約に基づいて、引数は可能であればレジスタで渡され、残りの引数はスタックで渡されます。 X64 のコードは、使用`__cdecl`を上書きする、 **/Gv**コンパイラ オプションと、既定の x64 呼び出し規約を使用します。  
  
 静的でないクラス関数がアウトオブラインで宣言されている場合、アウトオブラインの宣言で呼び出し規則の修飾子を指定する必要はありません。 つまり、クラスの静的でないメンバー メソッドの場合は、宣言時に指定された呼び出し規約が定義の時点で仮定されます。 次のクラス定義があるとします。  
  
```cpp  
struct CMyClass {  
   void __cdecl mymethod();  
};  
```  
  
 ここで、  
  
```cpp  
void CMyClass::mymethod() { return; }  
```  
  
 は次の記述と同じです。  
  
```cpp  
void __cdecl CMyClass::mymethod() { return; }  
```  
  
## <a name="example"></a>例  
 次の例では、コンパイラは、`system` 関数に対して C の命名規則と呼び出し規約を使用するように指示されます。  
  
```cpp  
// Example of the __cdecl keyword on function  
int __cdecl system(const char *);  
// Example of the __cdecl keyword on function pointer  
typedef BOOL (__cdecl *funcname_ptr)(void * arg1, const char * arg2, DWORD flags, ...);  
```  
  
## <a name="see-also"></a>関連項目  
 [引数の渡し規則と名前付け規則](../cpp/argument-passing-and-naming-conventions.md)   
 [キーワード](../cpp/keywords-cpp.md)
