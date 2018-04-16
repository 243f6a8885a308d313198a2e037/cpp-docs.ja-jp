---
title: "_com_error::_com_error |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::_com_error
dev_langs:
- C++
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: df04357afd35b546fb43c90a102b7dc0cacdc95e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="comerrorcomerror"></a>_com_error::_com_error
**Microsoft 固有の仕様**  
  
 `_com_error` オブジェクトを構築します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      _com_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = NULL,  
   bool fAddRef=false  
) throw( );  
_com_error(  
   const _com_error& that   
) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `hr`  
 `HRESULT` 情報。  
  
 `perrinfo`  
 **IErrorInfo**オブジェクト。  
  
 **bool fAddRef = false**  
 コンス トラクターに null 以外の AddRef を呼び出すことと、 **IErrorInfo**インターフェイスです。 こうすることで、次の例のように、インターフェイスの所有権が `_com_error` オブジェクトに渡される一般的なケースで参照カウントが正しく実行されます。  
  
```  
throw _com_error(hr, perrinfo);  
```  
  
 所有権を転送するようにコードをしないかどうか、`_com_error`オブジェクト、および`AddRef`をオフセットするために必要な**リリース**で、`_com_error`デストラクター、次のように、オブジェクトの構築します。  
  
```  
_com_error err(hr, perrinfo, true);  
```  
  
 `that`  
 既存の `_com_error` オブジェクト。  
  
## <a name="remarks"></a>コメント  
 最初のコンス トラクターは、指定された新しいオブジェクトを作成、`HRESULT`と省略可能な**IErrorInfo**オブジェクト。 2 つ目のコンストラクターは、既存の `_com_error` オブジェクトのコピーを作成します。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [_com_error クラス](../cpp/com-error-class.md)