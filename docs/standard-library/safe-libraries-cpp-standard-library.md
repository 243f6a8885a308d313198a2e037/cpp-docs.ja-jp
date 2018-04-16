---
title: "安全なライブラリ: C++ 標準ライブラリ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
dev_langs:
- C++
helpviewer_keywords:
- Safe Libraries
- Safe Libraries, C++ Standard Library
- Safe C++ Standard Library
ms.assetid: 3993340f-1f29-4d81-b3f5-52a52bc8e148
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6e53abd44312ea40eef68c39450ba63746f9c42e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="safe-libraries-c-standard-library"></a>安全なライブラリ: C++ 標準ライブラリ
Visual C++ に付属しているライブラリ (C++ 標準ライブラリを含む) には、安全性を向上するためのいくつかの機能強化が加えられています。  
  
 C++ 標準ライブラリに含まれる一部のメソッドは、バッファー オーバーランが発生する可能性のあるものや、コードに欠陥があることによる潜在的な危険性が確認されています。 こうしたメソッドの使用はお勧めできません。また、それらに置き換わる、新しい安全性の高いメソッドが作成されています。 これに該当する新しいメソッドのすべてには、末尾に `_s`が付いています。  
  
 反復子とアルゴリズムにも、安全性を向上するためのいくつかの機能強化が行われています。 詳細については、「[チェックを行う反復子](../standard-library/checked-iterators.md)」、「[反復子のデバッグのサポート](../standard-library/debug-iterator-support.md)」、および「[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 次の表に、潜在的な危険性のある C++ 標準ライブラリのメソッドと、それと同等な安全なメソッドを示します。  
  
|潜在的に危険なメソッド|安全な同等のメソッド|  
|-------------------------------|----------------------|  
|[copy](../standard-library/basic-string-class.md#copy)|[basic_string::_Copy_s](../standard-library/basic-string-class.md#copy_s)|  
|[copy](../standard-library/char-traits-struct.md#copy)|[char_traits::_Copy_s](../standard-library/char-traits-struct.md#copy_s)|  
  
 上記の潜在的に危険なメソッドのいずれかを呼び出したり、不適切に反復子を使用したりすると、コンパイラは[コンパイラの警告 (レベル 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) を生成します。 これらの警告を無効にする方法の詳細については、「[_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)」を参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)  
  
 [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)  
  
 [Checked Iterators](../standard-library/checked-iterators.md)  
  
 [Debug Iterator Support](../standard-library/debug-iterator-support.md)  
  
## <a name="see-also"></a>参照  
 [C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)

