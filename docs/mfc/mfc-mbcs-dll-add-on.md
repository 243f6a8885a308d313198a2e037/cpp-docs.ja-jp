---
title: "MFC MBCS DLL アドオン |Microsoft ドキュメント"
ms.custom: 
ms.date: 1/04/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MBCS
- MFC
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d6f134110ff95956cc37d6e038a680ff27cbc298
ms.sourcegitcommit: 56f6fce7d80e4f61d45752f4c8512e4ef0453e58
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2018
---
# <a name="mfc-mbcs-dll-add-on"></a>MFC MBCS DLL アドオン

MFC のサポートとそのマルチバイト文字セット (MBCS) ライブラリは、2015、および 2017、Visual Studio 2013 での Visual Studio のインストール中に、追加の手順が必要です。

**Visual Studio 2013**: 既定では、Visual Studio 2013 でインストールされている MFC ライブラリのみ Unicode の開発をサポートします。 持つ Visual Studio 2013 で MFC プロジェクトをビルドするために、MBCS の Dll が必要があります、**文字セット**プロパティに設定**マルチ バイト文字セットを使用**または**未設定**です。 DLL をダウンロード[for Visual Studio 2013 のマルチバイト MFC ライブラリ](https://www.microsoft.com/en-us/download/details.aspx?id=40770)です。

**Visual Studio 2015**: 両方の Unicode と MBCS MFC Dll には、Visual C セットアップ コンポーネントに含まれるが、MFC は既定でインストールすることはできませんをサポートします。 Visual C++ と MFC は、Visual Studio セットアップではオプションのインストール構成です。 MFC が確実にインストールされるようにするには、セットアップで **［カスタム］** を選択して、 **［プログラミング言語］**で **［Visual C++］** と **［Microsoft Foundation Classes for C++］** が選択されていることを確認します。 既に Visual Studio がインストールされている場合は、MFC プロジェクトを作成しようとしたときに、Visual C++ や MFC のインストールを促すプロンプトが表示されます。

**Visual Studio 2017**: と Unicode と MBCS MFC Dll がインストールされている、 **C++ を使用したデスクトップ開発**ワークロードを選択すると**MFC および ATL サポート**から、 **省略可能なコンポーネント**ウィンドウです。 インストーラーを起動するには、インストールにこれらのコンポーネントが含まれていない場合、**新しいプロジェクト**ダイアログを使用して、**開いている Visual Studio インストーラー**リンクします。

## <a name="see-also"></a>関連項目

[MFC ライブラリのバージョン](../mfc/mfc-library-versions.md)

