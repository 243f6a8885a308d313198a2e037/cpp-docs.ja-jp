---
title: "Hstring::makereference メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HString::MakeReference
dev_langs: C++
ms.assetid: 9e1fd2b2-66ad-4a50-b647-a20ab10e522f
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 026b036e3a4dad0fb88600cb64ac3da892eba2b3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="hstringmakereference-method"></a>HString::MakeReference メソッド
指定した文字列パラメーターから HStringReference オブジェクトを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
template<unsigned int sizeDest>  
    static HStringReference MakeReference(  
              wchar_t const (&str)[ sizeDest]);  
  
    template<unsigned int sizeDest>  
    static HStringReference MakeReference(  
              wchar_t const (&str)[sizeDest],   
              unsigned int len);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `sizeDest`  
 コピー先の HStringReference バッファーのサイズを指定するテンプレート パラメーター。  
  
 `str`  
 ワイド文字の文字列への参照。  
  
 `len`  
 最大長、`str`この操作で使用するパラメーター バッファーです。 場合、`len`パラメーターが指定されていない全体`str`パラメーターを使用します。  
  
## <a name="return-value"></a>戻り値  
 指定したのと同じ値を持つは HStringReference オブジェクト`str`パラメーター。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [HString クラス](../windows/hstring-class.md)