---
title: char_traits&lt;char32_t&gt; 構造体 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- iosfwd/std::char_traits<char_32t>
- char_traits<char32_t>
dev_langs:
- C++
helpviewer_keywords:
- char_traits<char32_t> class
ms.assetid: c0315466-45d0-4a99-b83e-3b1dbfbfbbc3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6caffb278fbcb94eff1042716adc384b56ae6050
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33847014"
---
# <a name="chartraitsltchar32tgt-struct"></a>char_traits&lt;char32_t&gt; 構造体

テンプレート構造体 **char_traits\<CharType>** を `char32_t` 型の要素に特殊化した構造体。

## <a name="syntax"></a>構文

```cpp
template <>
struct char_traits<char32_t>;
```

## <a name="remarks"></a>コメント

特殊化により、構造体でこの型 `char32_t` のオブジェクトを操作するライブラリ関数を利用できます。

## <a name="requirements"></a>要件

**ヘッダー:** \<string>

**名前空間:** std

## <a name="see-also"></a>関連項目

[\<string>](../standard-library/string.md)<br/>
[char_traits 構造体](../standard-library/char-traits-struct.md)<br/>
