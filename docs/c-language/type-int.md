---
title: "int 型 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- int data type
- type int
- portability [C++], type int
- signed integers
ms.assetid: 0067ce9a-281e-491a-ae63-632952981e13
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: cdf2a76e75b7ca453b908af586954454f7ce09f2
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="type-int"></a>int 型
符号付きまたは符号なし `int` 項目のサイズは、特定のコンピューターの整数の標準サイズです。 たとえば、16 ビット オペレーティング システムでは、通常、`int` 型は 16 ビットつまり 2 バイトです。 32 ビット オペレーティング システムでは、通常、`int` 型は 32 ビットつまり 4 バイトです。 したがって、ターゲット環境によって、`int` 型は `short int` または **long int** 型のいずれかに相当し、`unsigned int` 型は **unsigned short** または `unsigned long` 型のいずれかに相当します。 `int` 型はすべて、特に指定しない限り、符号付きの値を表します。  
  
 型指定子 `int` と `unsigned int` (または単に `unsigned`) は、C 言語の特定の機能 (`enum` 型など) を定義します。 このような場合、特定の実装における `int` と unsigned int の定義が、実際のストレージを決定します。  
  
 **Microsoft 固有の仕様**  
  
 符号付き整数は、2 の補数形式で表されます。 最上位ビットは符号を表し、負の数ならば 1、正の数とゼロならば 0 です。 値の範囲は、「[C++ 整数の制限](../c-language/cpp-integer-limits.md)」に示されており、LIMITS.H ヘッダー ファイルから取得されます。  
  
 **END Microsoft 固有の仕様**  
  
> [!NOTE]
>  int 型指定子と unsigned int 型指定子は、コンピューターで最も効率的に整数値を処理できるので、C プログラムで広く使用されます。 ただし、int 型と unsigned int 型のサイズは固定されていないため、特定の int サイズに依存するプログラムは、他のコンピューターに移植できない場合があります。 プログラムの移植可能性を高めるには、ハードコーディングされたデータ サイズではなく、sizeof 演算子 (「[sizeof 演算子](../c-language/sizeof-operator-c.md)」で説明) を式で使用します。  
  
## <a name="see-also"></a>関連項目  
 [基本型の格納](../c-language/storage-of-basic-types.md)
