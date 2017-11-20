---
title: "アプリケーションおよびスレッド サポート クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.support
dev_langs: C++
helpviewer_keywords:
- application objects [MFC], thread support classes
- lock classes [MFC]
- thread support classes [MFC]
- threading [MFC]
- synchronization classes [MFC], multithreading
- application support classes [MFC]
ms.assetid: 3c1d14fd-c35c-48f1-86ce-1e0f9a32c36d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2859687c72a674f496e039a4f4b32795cfa4604d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="application-and-thread-support-classes"></a>アプリケーションおよびスレッド サポート クラス
各アプリケーションには、1 つのアプリケーション オブジェクトです。このオブジェクトは、実行中のプログラムの他のオブジェクトを調整しから派生した`CWinApp`です。  
  
 Microsoft Foundation Class (MFC) ライブラリには、複数のアプリケーション内での実行スレッドがサポートしています。 すべてのアプリケーションは、少なくとも 1 つのスレッドをいる必要があります。によって使用されるスレッド、`CWinApp`オブジェクトは、このプライマリ スレッドです。  
  
 `CWinThread`オペレーティング システムのスレッドの機能の一部をカプセル化します。 複数のスレッドをより簡単に使用するには、MFC クラスも用意されて同期オブジェクト Win32 の同期オブジェクトを C++ インターフェイスを提供します。  
  
## <a name="application-and-thread-classes"></a>アプリケーションおよびスレッド クラス  
 [CWinApp](../mfc/reference/cwinapp-class.md)  
 初期化、実行、およびアプリケーションを終了するコードをカプセル化します。 アプリケーション オブジェクトは、このクラスから派生されます。  
  
 [CWinThread](../mfc/reference/cwinthread-class.md)  
 すべてのスレッドの基本クラスです。 を直接使用するか、からクラスを派生`CWinThread`場合は、スレッドがユーザー インターフェイス機能を実行します。 `CWinApp` は、`CWinThread` から派生しています。  
  
## <a name="synchronization-object-classes"></a>同期オブジェクト クラス  
 [関数](../mfc/reference/csyncobject-class.md)  
 同期オブジェクト クラスの基本クラス。  
  
 [CCriticalSection](../mfc/reference/ccriticalsection-class.md)  
 オブジェクトにアクセスする 1 つのプロセス内のスレッドを 1 つだけを許可する同期クラスです。  
  
 [CSemaphore](../mfc/reference/csemaphore-class.md)  
 1 つと、指定した最大数のオブジェクトに同時にアクセスできるようにする同期クラスです。  
  
 [CMutex](../mfc/reference/cmutex-class.md)  
 任意の数のオブジェクトにアクセスするプロセス内のスレッドを 1 つだけを許可する同期クラスです。  
  
 [CEvent](../mfc/reference/cevent-class.md)  
 イベントが発生したときに、アプリケーションに通知する同期クラスです。  
  
 [CSingleLock](../mfc/reference/csinglelock-class.md)  
 スレッド セーフなクラスのメンバー関数で 1 つの同期オブジェクトでロックするために使用します。  
  
 [CMultiLock](../mfc/reference/cmultilock-class.md)  
 スレッド セーフなクラスのメンバー関数で使用すると、同期オブジェクトの配列から 1 つまたは複数の同期オブジェクトをロックします。  
  
## <a name="related-classes"></a>関連するクラス  
 [メンバー](../mfc/reference/ccommandlineinfo-class.md)  
 プログラムの開始、コマンドラインを解析します。  
  
 [CWaitCursor](../mfc/reference/cwaitcursor-class.md)  
 待機カーソルを画面に配置します。 時間のかかる操作中に使用します。  
  
 [変更](../mfc/reference/cdockstate-class.md)  
 永続的なストレージのドッキング コントロール バーの状態データを処理します。  
  
 [関数](../mfc/reference/crecentfilelist-class.md)  
 最近使用した (MRU) ファイルの一覧を保持します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../mfc/class-library-overview.md)

