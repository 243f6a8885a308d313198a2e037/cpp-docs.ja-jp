---
title: NMAKE の実行 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- targets, building
- response files, NMAKE
- targets
- command files
- NMAKE program, targets
- NMAKE program, running
- command files, NMAKE
ms.assetid: 0421104d-8b7b-4bf3-86c1-928d9b7c1a8c
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a6c39612cf4df47665f7ea3d529b77ee4e70ce8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="running-nmake"></a>NMAKE の実行
## <a name="syntax"></a>構文  
  
```  
NMAKE [option...] [macros...] [targets...] [@commandfile...]  
```  
  
## <a name="remarks"></a>コメント  
 のみを指定 (nmake の) ビルド*ターゲット*または、最初のターゲット メイクファイルを何も指定されていない場合。 メイクファイルの先頭のターゲットを指定できます、[疑似ターゲット](../build/pseudotargets.md)他のターゲットをビルドします。 (Nmake の) は、/F; で指定されたメイクファイルを使用します。/F が指定されていない場合は、現在のディレクトリにメイクファイル ファイルを使用します。 コマンド ライン ビルドを推論規則を使用して、メイクファイルが指定されていない場合*ターゲット*です。  
  
 `commandfile`テキスト ファイル (または応答ファイル) は、コマンドラインの入力が含まれています。 その他の入力がの前またはに従って`commandfile`です。 パスが許可されます。 `commandfile`、改行文字はスペースとして扱われます。 スペースが含まれている場合は、マクロ定義を引用符で囲みます。  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
 [NMAKE のオプション](../build/nmake-options.md)  
  
 [Tools.ini と NMAKE](../build/tools-ini-and-nmake.md)  
  
 [(Nmake の) からの終了コード](../build/exit-codes-from-nmake.md)  
  
## <a name="see-also"></a>参照  
 [NMAKE リファレンス](../build/nmake-reference.md)