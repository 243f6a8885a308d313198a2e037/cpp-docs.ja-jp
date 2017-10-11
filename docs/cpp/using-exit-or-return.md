---
title: "使用して終了するかを返す |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
- return keyword [C++], using for program termination
ms.assetid: b5136c5c-2505-4229-8691-2a1d6a98760b
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 9fc6588a6593559314774e30a4d65c5a60779eb5
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="using-exit-or-return"></a>exit または return の使用
呼び出すと**終了**またはを実行、`return`ステートメントから**メイン**、静的オブジェクトは、初期化の逆の順序で破棄されます。 次の例は、こうした初期化やクリーンアップがどのように機能するのかを示します。  
  
## <a name="example"></a>例  
  
```  
// using_exit_or_return1.cpp  
#include <stdio.h>  
class ShowData {  
public:  
   // Constructor opens a file.  
   ShowData( const char *szDev ) {  
   errno_t err;  
      err = fopen_s(&OutputDev, szDev, "w" );  
   }  
  
   // Destructor closes the file.  
   ~ShowData() { fclose( OutputDev ); }  
  
   // Disp function shows a string on the output device.  
   void Disp( char *szData ) {   
      fputs( szData, OutputDev );  
   }  
private:  
   FILE *OutputDev;  
};  
  
//  Define a static object of type ShowData. The output device  
//   selected is "CON" -- the standard output device.  
ShowData sd1 = "CON";  
  
//  Define another static object of type ShowData. The output  
//   is directed to a file called "HELLO.DAT"  
ShowData sd2 = "hello.dat";  
  
int main() {  
   sd1.Disp( "hello to default device\n" );  
   sd2.Disp( "hello to file hello.dat\n" );  
}  
```  
  
 前の例では、静的オブジェクト `sd1` と `sd2` は、`main` に入る前に作成および初期化されます。 このプログラムが `return` ステートメントを使用して終了した後、最初に `sd2` が破棄され、その後に `sd1` が破棄されます。 `ShowData` クラスのデストラクターは、これらの静的オブジェクトに関連付けられたファイルを閉じます    
  
 このコードを作成するもう 1 つの方法は、ブロック スコープを持つ `ShowData` オブジェクトを宣言して、スコープ外に出ると破棄できるようにすることです。  
  
```  
int main() {  
   ShowData sd1, sd2( "hello.dat" );  
  
   sd1.Disp( "hello to default device\n" );  
   sd2.Disp( "hello to file hello.dat\n" );  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [終了に関するその他の考慮事項](../cpp/additional-termination-considerations.md)
