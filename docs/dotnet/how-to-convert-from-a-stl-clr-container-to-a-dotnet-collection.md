---
title: "方法: STL/CLR コンテナーを .NET コレクションに変換 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- STL/CLR Containers [STL/CLR]
- STL/CLR, converting to .NET collections
ms.assetid: 70b2dfd9-869c-4e0f-9a29-b1ee0cb0d107
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: aa58c8db46d1443ca5b39449222cc22e31eafb5c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-convert-from-a-stlclr-container-to-a-net-collection"></a>方法: STL/CLR コンテナーを .NET コレクションに変換する
このトピックでは、同等の .NET のコレクションを STL/CLR コンテナーに変換する方法を示します。 例として、STL/CLR に変換する方法を示します[ベクター](../dotnet/vector-stl-clr.md) .net <xref:System.Collections.Generic.ICollection%601> 、STL/CLR を変換する方法および[マップ](../dotnet/map-stl-clr.md).net<xref:System.Collections.Generic.IDictionary%602>プロシージャはすべてのコレクションと似ていますが、およびコンテナーです。  
  
### <a name="to-create-a-collection-from-a-container"></a>コンテナーからコレクションを作成するには  
  
1.  次の方法のいずれかを使用します。  
  
    -   コンテナーの一部を変換するには、呼び出し、 [make_collection](../dotnet/make-collection-stl-clr.md)関数、および .NET コレクションにコピーするのには、begin の反復子と STL/CLR コンテナーの末尾の反復子に渡します。 STL/CLR 反復子は、このテンプレート関数は、テンプレート引数として受け取ります。 最初の例では、この方法を示します。  
  
    -   コンテナー全体を変換するには、.NET コレクションに適切なインターフェイスまたはインターフェイスのコレクション コンテナーをキャストします。 2 番目の例では、この方法を示します。  
  
## <a name="example"></a>例  
 この例では、作成、STL/CLR`vector`し 5 つの要素を追加します。 その後、呼び出すことによって .NET コレクションを作成、`make_collection`関数。 最後に、新しく作成されたコレクションの内容を表示します。  
  
```  
// cliext_convert_vector_to_icollection.cpp  
// compile with: /clr  
  
#include <cliext/adapter>  
#include <cliext/vector>  
  
using namespace cliext;  
using namespace System;  
using namespace System::Collections::Generic;  
  
int main(array<System::String ^> ^args)  
{  
    cliext::vector<int> primeNumbersCont;  
    primeNumbersCont.push_back(2);  
    primeNumbersCont.push_back(3);  
    primeNumbersCont.push_back(5);  
    primeNumbersCont.push_back(7);  
    primeNumbersCont.push_back(11);  
  
    System::Collections::Generic::ICollection<int> ^iColl =  
        make_collection<cliext::vector<int>::iterator>(  
            primeNumbersCont.begin() + 1,  
            primeNumbersCont.end() - 1);  
  
    Console::WriteLine("The contents of the System::Collections::Generic::ICollection are:");  
    for each (int i in iColl)  
    {  
        Console::WriteLine(i);  
    }  
}  
```  
  
```Output  
The contents of the System::Collections::Generic::ICollection are:  
3  
5  
7  
```  
  
## <a name="example"></a>例  
 この例では、作成、STL/CLR`map`し 5 つの要素を追加します。 .NET を作成し、<xref:System.Collections.Generic.IDictionary%602>を割り当てると、`map`に直接できます。 最後に、新しく作成されたコレクションの内容を表示します。  
  
```  
// cliext_convert_map_to_idictionary.cpp  
// compile with: /clr  
  
#include <cliext/adapter>  
#include <cliext/map>  
  
using namespace cliext;  
using namespace System;  
using namespace System::Collections::Generic;  
  
int main(array<System::String ^> ^args)  
{  
    cliext::map<float, int> ^aMap = gcnew cliext::map<float, int>;  
    aMap->insert(cliext::make_pair<float, int>(42.0, 42));  
    aMap->insert(cliext::make_pair<float, int>(13.0, 13));  
    aMap->insert(cliext::make_pair<float, int>(74.0, 74));  
    aMap->insert(cliext::make_pair<float, int>(22.0, 22));  
    aMap->insert(cliext::make_pair<float, int>(0.0, 0));  
  
    System::Collections::Generic::IDictionary<float, int> ^iDict = aMap;  
  
    Console::WriteLine("The contents of the IDictionary are:");  
    for each (KeyValuePair<float, int> ^kvp in iDict)  
    {  
        Console::WriteLine("Key: {0:F} Value: {1}", kvp->Key, kvp->Value);  
    }  
}  
```  
  
```Output  
The contents of the IDictionary are:  
Key: 0.00 Value: 0  
Key: 13.00 Value: 13  
Key: 22.00 Value: 22  
Key: 42.00 Value: 42  
Key: 74.00 Value: 74  
```  
  
## <a name="see-also"></a>参照  
 [STL/CLR ライブラリ リファレンス](../dotnet/stl-clr-library-reference.md)   
 [方法: STL/CLR コンテナーを .NET コレクションに変換](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)   
 [range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)