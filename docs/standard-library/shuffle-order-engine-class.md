---
title: shuffle_order_engine クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- random/std::shuffle_order_engine
- random/std::shuffle_order_engine::base
- random/std::shuffle_order_engine::discard
- random/std::shuffle_order_engine::operator()
- random/std::shuffle_order_engine::base_type
- random/std::shuffle_order_engine::seed
dev_langs:
- C++
helpviewer_keywords:
- std::shuffle_order_engine [C++]
- std::shuffle_order_engine [C++], base
- std::shuffle_order_engine [C++], discard
- std::shuffle_order_engine [C++], base_type
- std::shuffle_order_engine [C++], seed
ms.assetid: 0bcd1fb0-44d7-4e59-bb1b-4a9b673a960d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 13b46bcd29624d696ae22494c394fa028d58fa8a
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38961975"
---
# <a name="shuffleorderengine-class"></a>shuffle_order_engine クラス

ベースのエンジンから返された値を並べ替えることで、ランダム シーケンスを生成します。

## <a name="syntax"></a>構文

```cpp
template <class Engine, size_t K>
class shuffle_order_engine;
```

### <a name="parameters"></a>パラメーター

*エンジン*ベース エンジンの種類。

*K* **テーブル サイズ**します。 バッファー (テーブル) 内の要素の数。 **前提条件**: `0 < K`

## <a name="members"></a>メンバー

||||
|-|-|-|
|`shuffle_order_engine::shuffle_order_engine`|`shuffle_order_engine::base`|`shuffle_order_engine::discard`|
|`shuffle_order_engine::operator()`|`shuffle_order_engine::base_type`|`shuffle_order_engine::seed`|

エンジンのメンバーの詳細については、[\<random>](../standard-library/random.md) をご覧ください。

## <a name="remarks"></a>Remarks

このテンプレート クラスは、ベースのエンジンによって返される値を並べ替えることで値を生成する*エンジン アダプター*を表します。 各コンス トラクターを内部テーブルに格納*K*ベースのエンジンによって返される値と値が要求されたときに、テーブルからランダムに要素が選択されています。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<random>

**名前空間:** std

## <a name="see-also"></a>関連項目

[\<random>](../standard-library/random.md)<br/>
