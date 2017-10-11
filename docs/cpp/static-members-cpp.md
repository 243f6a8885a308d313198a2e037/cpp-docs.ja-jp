---
title: "静的メンバー (C++) |Microsoft ドキュメント"
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
- class members [C++], static
- instance constructors, static members
- class members [C++], shared
- members [C++], static data members
- static members [C++], data members
- static data members [C++]
- data members [C++], static data members
- class instances [C++], shared members
- instance constructors, shared members
- class instances [C++], static members
ms.assetid: 9cc8cf0f-d74c-46f2-8e83-42d4e42c8370
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 568ceedfcc3cd470cdd9003dfb41c691f9986f25
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="static-members-c"></a>静的メンバー (C++)
クラスには、静的なメンバー データとメンバー関数を含めることができます。 データ メンバーとして宣言されて**静的**クラスのすべてのオブジェクトのデータの 1 つだけのコピーが保持されます。
  
 静的データ メンバーは、特定のクラス型のオブジェクトの一部ではありません。 その結果、静的データ メンバーの宣言は定義とは見なされません。 データ メンバーはクラス スコープで宣言されますが、定義はファイル スコープで行われます。 これらの静的メンバーは外部リンケージを持ちます。 次に例を示します。  
  
```  
// static_data_members.cpp  
class BufferedOutput  
{  
public:  
   // Return number of bytes written by any object of this class.  
   short BytesWritten()  
   {  
      return bytecount;  
   }  
  
   // Reset the counter.  
   static void ResetCount()  
   {  
      bytecount = 0;  
   }  
  
   // Static member declaration.  
   static long bytecount;  
};  
  
// Define bytecount in file scope.  
long BufferedOutput::bytecount;  
  
int main()  
{  
}  
```  
  
 上記のコードで、メンバー `bytecount` は、クラス `BufferedOutput` で宣言されていますが、クラス宣言の外側で定義する必要があります。  
  
 静的データ メンバーは、クラス型のオブジェクトを参照せずに参照できます。 `BufferedOutput` オブジェクトを使用して書き込まれたバイト数は、次のように取得できます。  
  
```  
long nBytes = BufferedOutput::bytecount;  
```  
  
 静的メンバーを存在させるために、クラス型のオブジェクトが存在する必要はありません。 静的メンバーは、メンバー選択を使用してアクセスすることもできます (**です。** および** -> **) 演算子。 例:  
  
```  
BufferedOutput Console;  
  
long nBytes = Console.bytecount;  
```  
  
 前のケースでは、オブジェクト (`Console`) への参照は評価されません。返される値は、静的オブジェクト `bytecount` の値です。  
  
 静的データ メンバーはクラス メンバーのアクセス規則に従うため、静的データ メンバーへのプライベート アクセスはクラス メンバー関数およびフレンドだけに許可されます。 これらの規則については、「[メンバー アクセス コントロール](../cpp/member-access-control-cpp.md)です。 例外は、静的データ メンバーが、そのアクセス制限にかかわらず、ファイルのスコープ内で定義されなければならないということです。 データ メンバーを明示的に初期化する場合は、初期化子を定義で指定する必要があります。  
  
 静的メンバーの型は、クラス名で修飾されていません。 そのため、`BufferedOutput::bytecount` の型は `long` です。  
  
## <a name="see-also"></a>関連項目  
 [クラスと構造体](../cpp/classes-and-structs-cpp.md)
