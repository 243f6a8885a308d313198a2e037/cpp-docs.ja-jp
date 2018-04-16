---
title: "&lt;参照してください&gt;(Visual C) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <see>
- see
dev_langs:
- C++
helpviewer_keywords:
- <see> C++ XML tag
- see C++ XML tag
ms.assetid: 20ef66f4-b278-45cf-8613-63919edf5720
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 15e1aedefe6d20c181ff208f76a61f49e15f5214
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ltseegt-visual-c"></a>&lt;参照してください&gt;(Visual C)
\<see> タグを使用すると、テキスト内でリンクを指定できます。 使用して[ \<seealso >](../ide/seealso-visual-cpp.md) 「参照」セクションに表示するテキストを示すためにします。  
  
## <a name="syntax"></a>構文  
  
```  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a>パラメーター  
 `member`  
 現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。  名前は、一重引用符または二重引用符で囲みます。  
  
 コンパイラは、指定されたコード要素が存在し、解決されることを確認`member`出力 XML 内の要素名にします。  コンパイラは、`member` が見つからない場合に警告を発行します。  
  
## <a name="remarks"></a>コメント  
 コンパイル時に [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) を指定して、ドキュメント コメントをファイルに出力します。  
  
 参照してください[\<概要 >](../ide/summary-visual-cpp.md)の使用例については\<を参照してください >。  
  
 Visual C++ コンパイラは、ドキュメント コメントを通じて 1 回渡すことで cref 参照の解決を試みます。  したがって、C++ のルックアップ規則を使用する場合、コンパイラによってシンボルが見つからないと、参照が未解決としてマークされます。 参照してください[ \<seealso >](../ide/seealso-visual-cpp.md)詳細についてはします。  
  
## <a name="example"></a>例  
 コンパイラは、参照を解決するように、次の例は、ジェネリック型に cref 参照を作成する方法を示します。  
  
```  
// xml_see_cref_example.cpp  
// compile with: /LD /clr /doc  
// the following cref shows how to specify the reference, such that,  
// the compiler will resolve the reference  
/// <see cref="C{T}">  
/// </see>  
ref class A {};  
  
// the following cref shows another way to specify the reference,   
// such that, the compiler will resolve the reference  
/// <see cref="C < T >"/>  
  
// the following cref shows how to hard-code the reference  
/// <see cref="T:C`1">  
/// </see>  
ref class B {};  
  
/// <see cref="A">  
/// </see>  
/// <typeparam name="T"></typeparam>  
generic<class T>  
ref class C {};  
```  
  
## <a name="see-also"></a>参照  
 [XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)