---
title: "nothrow_t 構造体 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- nothrow_t
dev_langs:
- C++
helpviewer_keywords:
- nothrow_t class
ms.assetid: dc7d5d42-ed5a-4919-88fe-bbad519b7a1d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4854fb4e763679a63b14147cec8f1f37310475fe
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="nothrowt-structure"></a>nothrow_t 構造体
この構造体は operator new の関数パラメーターとして使用し、関数に対して、割り当て失敗を報告する際に例外をスローするのではなく Null ポインター を返すように指定します。  
  
## <a name="syntax"></a>構文  
  
```
struct std::nothrow_t {};
```  
  
## <a name="remarks"></a>コメント  
 この構造体により、コンパイラが適切なバージョンのコンストラクターを選択できます。 [nothrow](../standard-library/new-functions.md#nothrow) は、`std::nothrow_t` 型のオブジェクトと同義です。  
  
## <a name="example"></a>例  
 `std::nothrow_t` を関数パラメーターとして使用する方法の例については、[operator new](../standard-library/new-operators.md#op_new) および [operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr) に関する記事をご覧ください。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<new>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)



