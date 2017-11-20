---
title: "Hstring::operator! = 演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HString::operator!=
dev_langs: C++
ms.assetid: dcdd2aca-e7d6-4bf1-b2de-03efbb430a93
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9f7042b7ade41fe20d003a50e2d44360f2d74754
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="hstringoperator-operator"></a>HString::Operator!= 演算子
2 つのパラメーターが異なるかどうかを示します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
inline bool operator!=( const HString& lhs,   
                        const HString& rhs) throw()  
  
inline bool operator!=( const HStringReference& lhs,   
                        const HString& rhs) throw()  
  
inline bool operator!=( const HString& lhs,   
                        const HStringReference& rhs) throw()  
  
inline bool operator!=( const HSTRING& lhs,   
                        const HString& rhs) throw()  
  
inline bool operator!=( const HString& lhs,   
                        const HSTRING& rhs) throw()  
```  
  
#### <a name="parameters"></a>パラメーター  
 `lhs`  
 比較する最初のパラメーター。 `lhs`HString または HStringReference オブジェクト、または HSTRING ハンドルを指定できます。  
  
 `rhs`  
 比較する 2 番目のパラメーターです。`rhs` HString または HStringReference オブジェクト、または HSTRING ハンドルを指定できます。  
  
## <a name="return-value"></a>戻り値  
 `true`場合、`lhs`と`rhs`パラメーターが等しくない。 それ以外の場合、`false`です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HString クラス](../windows/hstring-class.md)