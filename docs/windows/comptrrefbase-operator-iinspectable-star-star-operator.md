---
title: "Comptrrefbase::operator IInspectable * * 演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**
dev_langs: C++
helpviewer_keywords: operator IInspectable** operator
ms.assetid: 06ac1051-606c-449b-a566-cac78ca53762
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0c3b51191c6dd5627bd25a110beb6bff9a9c60f7
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2017
---
# <a name="comptrrefbaseoperator-iinspectable-operator"></a>ComPtrRefBase::operator IInspectable** 演算子

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
operator IInspectable**() const;
```

## <a name="remarks"></a>コメント

現在ではキャスト[ptr _](../windows/comptrrefbase-ptr-data-member.md)データ メンバーをポインターを-a のポインター - IInspectable インターフェイスです。

現在の ComPtrRefBase IInspectable から派生していない場合は、エラーが生成されます。

このキャストは使用可能な場合にのみ、 **&#95; &#95;です。WRL_CLASSIC_COM &#95; #95**が定義されています。

## <a name="requirements"></a>要件

**ヘッダー:** client.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[ComPtrRefBase クラス](../windows/comptrrefbase-class.md)   
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)