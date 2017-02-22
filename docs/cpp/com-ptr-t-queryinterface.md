---
title: "_com_ptr_t::QueryInterface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t::QueryInterface"
  - "_com_ptr_t.QueryInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "QueryInterface メソッド"
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_ptr_t::QueryInterface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 カプセル化されたインターフェイス ポインターで **IUnknown** の `QueryInterface` メンバー関数を呼び出します。  
  
## 構文  
  
```  
  
      template<typename _InterfaceType> HRESULT QueryInterface (  
   const IID& iid,  
   _InterfaceType*& p   
) throw ( );  
template<typename _InterfaceType> HRESULT QueryInterface (  
   const IID& iid,  
   _InterfaceType** p  
) throw( );  
```  
  
#### パラメーター  
 `iid`  
 インターフェイス ポインターの **IID**。  
  
 `p`  
 生のインターフェイス ポインター。  
  
## 解説  
 指定した **IID** を持つカプセル化されたインターフェイス ポインターで **IUnknown::QueryInterface** を呼び出し、結果として得られる生のインターフェイス ポインターを `p` に返します。  このルーチンは、成功または失敗を示すために、`HRESULT` を返します。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_com\_ptr\_t クラス](../cpp/com-ptr-t-class.md)