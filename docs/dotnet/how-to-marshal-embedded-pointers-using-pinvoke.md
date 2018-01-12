---
title: "方法: 埋め込み PInvoke を使用してポインターをマーシャ リングする. |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- embedded pointers [C++]
- interop [C++], embedded pointers
- platform invoke [C++], embedded pointers
- marshaling [C++], embedded pointers
- data marshaling [C++], embedded pointers
ms.assetid: f12c1b9a-4f82-45f8-83c8-3fc9321dbb98
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c8ae331bb6bb6b35fc4353ad08240fd3d23136a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-marshal-embedded-pointers-using-pinvoke"></a>方法: PInvoke を使用して埋め込みポインターをマーシャリングする
アンマネージ Dll に実装されている関数は、Platform Invoke (P/invoke) 機能を使用してマネージ コードから呼び出すことができます。 DLL のソース コードが使用できない場合は、相互運用するための唯一のオプションは P/invoke です。 ただし、Visual C は、他の .NET 言語とは異なり、P/invoke する代わりを提供します。 詳細については、次を参照してください。[を使用して C++ Interop (暗黙の PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)と[する方法: マーシャ リング埋め込みポインターを使用して C++ Interop](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)です。  
  
## <a name="example"></a>例  
 ネイティブ コードに構造体を渡すには、データ レイアウトの観点からネイティブ構造体と同じであるマネージ構造体を作成する必要があります。 ただし、ポインターを含む構造には、特別な処理が必要です。 構造体のマネージのバージョンのネイティブ構造体に埋め込まれた各ポインターのインスタンスを含める必要があります、<xref:System.IntPtr>型です。 また、メモリのこれらのインスタンスは、明示的に割り当てられる必要があります、初期化され、リリースを使用して、 <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A>、 <xref:System.Runtime.InteropServices.Marshal.StructureToPtr%2A>、および<xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A>メソッドです。  
  
 次のコードはアンマネージとマネージ モジュールで構成されます。 アンマネージ モジュールをポインターを含む ListString と呼ばれる構造体を受け取る関数と TakesListStruct に呼び出される関数を定義する DLL です。 TakesListStruct 関数をインポートし、倍 * で表示する点を除いてネイティブ ListStruct に相当する MListStruct と呼ばれる構造体を定義するコマンド ライン アプリケーションは、マネージ モジュールは、<xref:System.IntPtr>インスタンス。 TakesListStruct を呼び出す前に、メイン関数を割り当ててこのフィールドを参照するメモリを初期化します。  
  
 マネージ モジュールは、/clr は/clr でコンパイル: 純粋なが動作します。 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で使用されていません。  
  
```cpp  
// TraditionalDll6.cpp  
// compile with: /EHsc /LD  
#include <stdio.h>  
#include <iostream>  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
#pragma pack(push, 8)  
struct ListStruct {  
   int count;  
   double* item;  
};  
#pragma pack(pop)  
  
extern "C" {  
   TRADITIONALDLL_API void TakesListStruct(ListStruct);  
}  
  
void TakesListStruct(ListStruct list) {  
   printf_s("[unmanaged] count = %d\n", list.count);  
   for (int i=0; i<list.count; i++)  
      printf_s("array[%d] = %f\n", i, list.item[i]);  
}  
```  
  
```cpp  
// EmbeddedPointerMarshalling.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[StructLayout(LayoutKind::Sequential, Pack=8)]  
value struct MListStruct {  
   int count;  
   IntPtr item;  
};  
  
value struct TraditionalDLL {  
    [DllImport("TraditionalDLL6.dll")]  
   static public void TakesListStruct(MListStruct);  
};  
  
int main() {  
   array<double>^ parray = gcnew array<double>(10);  
   Console::WriteLine("[managed] count = {0}", parray->Length);  
  
   Random^ r = gcnew Random();  
   for (int i=0; i<parray->Length; i++) {  
      parray[i] = r->NextDouble() * 100.0;  
      Console::WriteLine("array[{0}] = {1}", i, parray[i]);  
   }  
  
   int size = Marshal::SizeOf(double::typeid);  
   MListStruct list;  
   list.count = parray->Length;  
   list.item = Marshal::AllocCoTaskMem(size * parray->Length);  
  
   for (int i=0; i<parray->Length; i++) {  
      IntPtr t = IntPtr(list.item.ToInt32() + i * size);  
      Marshal::StructureToPtr(parray[i], t, false);  
   }  
  
   TraditionalDLL::TakesListStruct( list );  
   Marshal::FreeCoTaskMem(list.item);  
}  
```  
  
 従来を使用してマネージ コードに、DLL の一部は公開されていませんことに注意してください #include ディレクティブです。 実際には、DLL は実行時にのみでの機能に問題が取り込まれるように<xref:System.Runtime.InteropServices.DllImportAttribute>はコンパイル時に、検出されません。  
  
## <a name="see-also"></a>参照  
 [C++ での明示的な PInvoke (DllImport 属性) の使用方法](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)