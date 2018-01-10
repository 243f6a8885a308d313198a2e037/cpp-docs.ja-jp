---
title: "チュートリアル: をコンパイルする C + +/CLI プログラムのコマンドラインで |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: cef41c88-faf9-439d-8423-25aa3f5674dd
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d509bc9890f4fa5ccebbd6ae3d1e3bcb3dbb0d93
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-compiling-a-ccli-program-on-the-command-line"></a>チュートリアル: コマンド ラインでの C++/CLI プログラムのコンパイル
共通言語ランタイム (CLR) を対象とし、.NET Framework を使用する Visual C++ プログラムを作成して、コマンド ラインでビルドできます。 Visual C++ では C++/CLI プログラミング言語がサポートされます。このプログラミング言語には、.NET プログラミング モデルを対象とする追加の型と演算子があります。 概要については、C + + CLI 言語の場合を参照してください[Pure C: こんにちは, C++ + CLI](http://msdn.microsoft.com/magazine/cc163681.aspx)です。 一般情報は、次を参照してください。 [C + での .NET プログラミング +/CLI (Visual c)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)です。  
  
 このチュートリアルでは、テキスト エディターを使って基本的な C++/CLI プログラムを作成し、コマンド ラインでコンパイルします。 (表示されているプログラムをタイプするのではなく、自分の C++/CLI プログラムを使用するか、別のヘルプ記事の C++/CLI コード サンプルを使用できます。 この手法は UI 要素が含まれていない小さなモジュールをビルドおよびテストするのに便利です。)  
  
> [!NOTE]
>  Visual Studio IDE を使用して C++/CLI プログラムをコンパイルすることもできます。 詳細については、次を参照してください。[チュートリアル: Visual Studio で CLR を対象とする C++ プログラムのコンパイル](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md)です。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 C++ 言語の基本を理解している必要があります。  
  
## <a name="compiling-a-ccli-program"></a>C++/CLI プログラムのコンパイル  
 次の手順は、.NET Framework クラスを使用する C++/CLI コンソール アプリケーションをコンパイルする方法を示します。  
  
 C + のコンパイルを有効にする +/CLI で行う必要があります、 [/clr](../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプション。 Visual C++ コンパイラは、MSIL コードまたは MSIL とネイティブ コードの混合を含む .exe ファイルを生成し、必要な .NET Framework ライブラリにリンクします。  
  
#### <a name="to-compile-a-ccli-application-on-the-command-line"></a>C++/CLI アプリケーションをコマンド ラインでコンパイルするには  
  
1.  開く、**開発者コマンド プロンプト**ウィンドウです。 具体的な手順については、次を参照してください。[開発者コマンド プロンプト ウィンドウを開く](../build/building-on-the-command-line.md#developer_command_prompt)です。  
  
     コンピューターのオペレーティング システムと構成によっては、コードを正常にコンパイルするために管理者の資格情報が必要な場合があります。 管理者としてコマンド プロンプト ウィンドウを実行して、右クリックして、コマンド プロンプトのショートカット メニューを開き、選択**詳細**、**管理者として実行**です。  
  
2.  コマンド プロンプトで次のように入力します。**メモ帳 basicclr.cpp**です。  
  
     選択**はい**されたら、ファイルを作成します。  
  
3.  メモ帳で、次の行を入力します。  
  
    ```  
    int main()  
    {  
        System::Console::WriteLine("This is a C++/CLI program.");  
    }  
    ```  
  
4.  メニュー バーで、次のように選択します。**ファイル**、**保存**です。  
  
     <xref:System.Console> 名前空間にある、.NET Framework クラス (<xref:System>) を使用する Visual C++ ソース ファイルを作成しました。  
  
5.  コマンド プロンプトで次のように入力します。 **cl/clr basicclr.cpp**です。 cl.exe コンパイラによって、ソース コードは MSIL を含む .obj ファイルにコンパイルされ、リンカーが実行されて basicclr.exe という名前の実行可能プログラムが生成されます。  
  
6.  コマンド プロンプトで、basicclr.exe プログラムを実行する入力**basicclr**です。  
  
     プログラムは、次のテキストを表示して終了します。  
  
    ```Output  
    This is a C++/CLI program.  
    ```  
  
## <a name="see-also"></a>参照  
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C/C++ プログラムのビルド](../build/building-c-cpp-programs.md)   
 [コンパイラ オプション](../build/reference/compiler-options.md)