---
title: wbuffer_convert クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocmon/stdext::cvt::wbuffer_convert
dev_langs:
- C++
helpviewer_keywords:
- wbuffer_convert class
ms.assetid: 4a56f9bf-4138-4612-b516-525fea401358
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 364ae6c544f58f09208cefeec9d3984de35120e1
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965217"
---
# <a name="wbufferconvert-class"></a>wbuffer_convert クラス

バイト ストリーム バッファーとの間の要素の転送を制御するストリーム バッファーを説明します。

## <a name="syntax"></a>構文

```cpp
template <class Codecvt, class Elem = wchar_t, class Traits = std::char_traits<Elem>>
class wbuffer_convert
 : public std::basic_streambuf<Elem, Traits>
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Codecvt*|変換オブジェクトを表す[ロケール](../standard-library/locale-class.md) ファセット。|
|*Elem*|ワイド文字要素型。|
|*Traits*|*Elem* と関連付けられている特徴。|

## <a name="remarks"></a>Remarks

このテンプレート クラスは、文字の特徴がクラス `Traits` によって記述される型 `_Elem` の要素の、型 `std::streambuf` のバイト ストリーム バッファーとの間での転送を制御するストリーム バッファーについて説明します。

`Elem` 値のシーケンスとマルチバイト シーケンスとの間の変換は、クラス `Codecvt<Elem, char, std::mbstate_t>` のオブジェクトによって実行されます。このことは、標準コード変換ファセット `std::codecvt<Elem, char, std::mbstate_t>` の要件を満たしています。

このテンプレート クラスのオブジェクトは、以下のものを格納します。

- 基になるバイト ストリーム バッファーへのポインター

- 割り当てられた変換オブジェクトへのポインター ([wbuffer_convert](../standard-library/wbuffer-convert-class.md) のときに解放される)
