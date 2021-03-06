---
title: ベース ポインター (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __based
- __based_cpp
dev_langs:
- C++
helpviewer_keywords:
- __based keyword [C++]
- based pointers
- pointers, based
ms.assetid: 1e5f2e96-c52e-4738-8e14-87278681205e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 57dc254bab0acd875378dfd26ba3fe6e8d5650f4
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407511"
---
# <a name="based-pointers-c"></a>ベース ポインター (C++)
**Microsoft 固有の仕様**  
  
 **_ _Based**キーワードでは、ポインター (既存のポインターからのオフセットであるポインター) に基づくポインターを宣言できます。  
  
## <a name="syntax"></a>構文  
  
```  
  
type __based( base ) declarator   
```  
  
## <a name="remarks"></a>Remarks  
 ポインター アドレスに基づくポインターは唯一の形式では、 **_ _based** 32 ビットまたは 64 ビット コンパイルで有効なキーワード。 Microsoft の 32 ビット C/C++ コンパイラでは、based ポインターは 32 ビットのポインター ベースからの 32 ビットのオフセットになります。 同様の制限は 64 ビット環境にもあり、based ポインターは 64 ビット ベースからの 64 ビット オフセットになります。  
  
 ポインターに基づいたポインターの使用方法の 1 つは、ポインターを含む永続的な識別子での使用です。 ポインターに基づくポインターで構成されるリンク リストをディスクに保存でき、メモリ内の別の場所に再読み込みしても、ポインターは有効なままです。 例えば:  
  
```cpp 
// based_pointers1.cpp  
// compile with: /c  
void *vpBuffer;  
struct llist_t {  
   void __based( vpBuffer ) *vpData;  
   struct llist_t __based( vpBuffer ) *llNext;  
};  
```  
  
 ポインター `vpBuffer` には、プログラムの後の段階で割り当てられるメモリ アドレスが代入されます。 リンク リストは `vpBuffer` の値を基準として再配置されます。  
  
> [!NOTE]
>  使用してポインターを含む識別子の永続化を行うことできますも[メモリ マップト ファイル](http://msdn.microsoft.com/library/windows/desktop/aa366556)します。  
  
 based ポインターを逆参照する場合、ベースは、明示的に指定されているか、または宣言によって暗黙的に認識されている必要があります。  
  
 以前のバージョンとの互換性のため **_based**のシノニムです **_ _based**します。  
  
## <a name="example"></a>例  
 次のコードは、ベースの変更による based ポインターの変更を示します。  
  
```cpp 
// based_pointers2.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int a1[] = { 1,2,3 };  
int a2[] = { 10,11,12 };  
int *pBased;  
  
typedef int __based(pBased) * pBasedPtr;  
  
using namespace std;  
int main() {  
   pBased = &a1[0];  
   pBasedPtr pb = 0;  
  
   cout << *pb << endl;  
   cout << *(pb+1) << endl;  
  
   pBased = &a2[0];  
  
   cout << *pb << endl;  
   cout << *(pb+1) << endl;  
}  
```  
  
```Output  
1  
2  
10  
11  
```  
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)   
 [alloc_text](../preprocessor/alloc-text.md)