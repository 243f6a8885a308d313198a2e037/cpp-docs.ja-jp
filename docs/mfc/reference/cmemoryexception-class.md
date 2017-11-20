---
title: "CMemoryException クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMemoryException
- AFX/CMemoryException
- AFX/CMemoryException::CMemoryException
dev_langs: C++
helpviewer_keywords: CMemoryException [MFC], CMemoryException
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 13130321dd26612b2bbd24457e02e09ce5fe1ec6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="cmemoryexception-class"></a>CMemoryException クラス
メモリ不足例外条件を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMemoryException : public CSimpleException  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMemoryException::CMemoryException](#cmemoryexception)|`CMemoryException` オブジェクトを構築します。|  
  
## <a name="remarks"></a>コメント  
 さらに修飾には、必要になるかはありません。 によって自動的にメモリ不足例外がスローされます**新しい**です。 使用して、独自のメモリ関数を記述する場合`malloc`、後の例では、メモリ不足例外がスローされることを担当します。  
  
 詳細については`CMemoryException`、記事を参照して[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CMemoryException`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afx.h  
  
##  <a name="cmemoryexception"></a>CMemoryException::CMemoryException  
 `CMemoryException` オブジェクトを構築します。  
  
```  
CMemoryException();  
```  
  
### <a name="remarks"></a>コメント  
 このコンス トラクターを直接使用しないでくださいではなくグローバル関数を呼び出すことは[AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception)です。 このグローバル関数は、以前に割り当てられたメモリ内の例外オブジェクトを構築するので、メモリ不足の状況で成功ことができます。 例外の処理の詳細については、記事を参照してください。[例外](../exception-handling-in-mfc.md)です。  
  
## <a name="see-also"></a>関連項目  
 [CException クラス](cexception-class.md)   
 [階層図](../hierarchy-chart.md)



