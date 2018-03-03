---
title: "アプリケーションの設定、ATL プロジェクト ウィザード |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.appwiz.atl.com.appset
dev_langs:
- C++
helpviewer_keywords:
- ATL Project Wizard, application settings
ms.assetid: d48c9fc5-f439-49fd-884c-8bcfa7d52991
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 12b7e383716d7cfa330bdfdebe21c33550669cc2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="application-settings-atl-project-wizard"></a>[アプリケーションの設定] (ATL プロジェクト ウィザード)
使用して、**アプリケーション設定**ATL プロジェクト ウィザードのページを設計して新しい ATL プロジェクトに基本的な機能を追加します。  
  
## <a name="server-type"></a>サーバーの種類  
 次の 3 つのサーバーの種類のいずれかから選択します。  
  
 **ダイナミック リンク ライブラリ (DLL)**  
 プロセスでサーバーを作成するを選択します。  
  
 **実行可能 (EXE)**  
 ローカルのアウト プロセス サーバーを作成するを選択します。 このオプションでは、MFC または COM + 1.0 のサポートは許可されません。 プロキシ/スタブ コードのマージのことはできません。  
  
 **サービス (EXE)**  
 Windows の起動時に、バック グラウンドで実行される Windows アプリケーションの作成を選択します。 このオプションは、MFC または COM + 1.0 のサポートを許可しないか、プロキシ/スタブ コードのマージの許可していません。  
  
## <a name="additional-options"></a>[追加オプション]  
  
> [!NOTE]
>  その他のオプションは、DLL プロジェクトのみで使用可能です。  
  
 **プロキシ/スタブ コードのマージを許可します。**  
 選択、**プロキシ/スタブ コードのマージを許可する**インターフェイスのマーシャ リングすることが必要な場合の便宜を図って チェック ボックスです。 このオプションによって、MIDL で生成されたプロキシとスタブ コードを同じ実行可能ファイル サーバーとして。  
  
 **MFC のサポート**  
 オブジェクトが、MFC サポートが含まれることを選択します。 このオプションは、クラスおよび関数が含まれているのいずれかがアクセスできるように、プロジェクトを MFC ライブラリにリンクします。  
  
 **COM + 1.0 のサポート**  
 COM + 1.0 コンポーネントをサポートするためにプロジェクトのビルド設定の変更を選択します。 標準の一覧に加えて、ライブラリ、COM + 1.0 コンポーネントに固有のライブラリ comsvcs.lib が追加されます。  
  
 さらに、mtxex.dll は、アプリケーションが起動されたときに、ホスト システムに読み込まれる遅延です。  
  
-   **コンポーネント レジスタをサポートして**ATL プロジェクトに COM + 1.0 コンポーネントに対するサポートが含まれている場合は、このオプションを設定することができます。 コンポーネント レジスタは、COM + 1.0 オブジェクトをコンポーネントの一覧を取得、コンポーネントを登録またはコンポーネントの登録を解除して (個別にまたはすべてを一度に) を使用します。  
  
## <a name="see-also"></a>参照  
 [ATL プロジェクト ウィザード](../../atl/reference/atl-project-wizard.md)   
 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)   
 [ATL プロジェクトの既定の構成](../../atl/reference/default-atl-project-configurations.md)

