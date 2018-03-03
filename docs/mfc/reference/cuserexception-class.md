---
title: "チェック クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUserException
dev_langs:
- C++
helpviewer_keywords:
- operations [MFC], stopping
- exceptions [MFC], throwing
- CUserException class [MFC]
- errors [MFC], trapping
- operations [MFC]
- throwing exceptions [MFC], stopping user operations
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4613f2ba06ffa697df219172b98a5cf193c1f3b2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cuserexception-class"></a>チェック クラス
エンド ユーザーの操作を中止するためにスローします。  
  
## <a name="syntax"></a>構文  
  
```  
class CUserException : public CSimpleException  
```  
  
## <a name="remarks"></a>コメント  
 使用して`CUserException`アプリケーション固有の例外のスローとキャッチ例外処理機構を使用する場合。 クラス名に「ユーザー」は、「アプリケーションのユーザーが例外を処理する必要がある」と解釈できます。  
  
 A`CUserException`グローバル関数の呼び出し後にスローされる通常`AfxMessageBox`操作が失敗したユーザーに通知します。 例外ハンドラーを記述するときに、ユーザー通常に既に通知されました、エラーのために特別に例外を処理します。 フレームワークは、場合によっては、この例外をスローします。 スローする、`CUserException`自分で、ユーザーに通知して、グローバル関数を呼び出す`AfxThrowUserException`です。  
  
 次の例で操作が失敗するを含む関数をユーザーに通知し、スロー、、`CUserException`です。 呼び出し元の関数は、例外をキャッチし、専用の処理します。  
  
 [!code-cpp[NVC_MFCExceptions#24](../../mfc/codesnippet/cpp/cuserexception-class_1.cpp)]  
  
 使用する方法についての`CUserException`、記事を参照して[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CUserException`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxwin.h  
  
## <a name="see-also"></a>参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CException クラス](../../mfc/reference/cexception-class.md)
