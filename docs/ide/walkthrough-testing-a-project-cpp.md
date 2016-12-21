---
title: "チュートリアル: プロジェクトのテスト (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "プロジェクトのテスト [C++]"
  - "プロジェクト [C++], テスト"
  - "テスト (プロジェクトを)"
ms.assetid: 88cdd377-c5c8-4201-889d-32f5653ebead
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# チュートリアル: プロジェクトのテスト (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

デバッグ モードでプログラムを実行すると、ブレークポイントを使用してプログラムを停止し、変数およびオブジェクトの状態を調べることができます。  
  
 このチュートリアルでは、プログラムの実行による変数の値の変化を観察し、予測どおりの値にならない理由を推測します。  
  
## 必須コンポーネント  
  
-   このチュートリアルは、C\+\+ 言語の基本を理解していることを前提としています。  
  
-   また、これまでの関連チュートリアル \(「[C\+\+ デスクトップ開発のための Visual Studio IDE の使用](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)」を参照\) を完了していることも必要です。  
  
### プログラムをデバッグ モードで実行するには  
  
1.  編集する TestGames.cpp を開きます。  
  
2.  次のコード行を選択します。  
  
     `Cardgame.solitaire(1);`  
  
3.  その行にブレークポイントを設定するには、メニュー バーで **\[デバッグ\]**、**\[ブレークポイントの設定\/解除\]** の順に選択するか、F9 キーを押します。  赤い円が行の左側に表示されて、その行にブレークポイントが設定されていることを示します。  ブレークポイントを削除するには、もう一度メニュー コマンドを選択するか F9 キーを押します。  
  
     マウスを使用している場合は、左の余白をクリックすることでブレークポイントを設定\/解除できます。  
  
4.  メニュー バーで **\[デバッグ\]**、**\[デバッグ開始\]** の順に選択するか、F5 キーを押します。  
  
     プログラムがブレークポイントの行に到達すると、実行が一時的に停止されます。プログラムが中断モードであるためです。  コード行の左側の黄色の矢印は、次に実行される行を示します。  
  
5.  `Cardgame::totalParticipants` 変数の値を調べるには、ポインターを `Cardgame` に移動し、ヒント ウィンドウの左側にある展開コントロールに移動します。  変数の名前 "`totalParticipants`" とその値 "12" が表示されます。  
  
     `Cardgame::totalParticipants` のショートカット メニューを開き、**\[ウォッチ式の追加\]** を選択して、その変数を **\[ウォッチ 1\]** ウィンドウに表示します。  変数を選択して **\[ウォッチ 1\]** ウィンドウにドラッグしてもかまいません。  
  
6.  コードの次の行に進むために、メニュー バーで **\[デバッグ\]**、**\[ステップ オーバー\]** の順に選択するか、F10 キーを押します。  
  
     `Cardgame::totalParticipants` の値が **\[ウォッチ 1\]** ウィンドウに "13" と表示されます。  
  
7.  `return 0;` ステートメントのショートカット メニューを開き、**\[カーソル行の前まで実行\]** を選択します。  コード左側の黄色の矢印は、次に実行されるステートメントを示します。  
  
8.  `Cardgame::totalParticipants` の値は Cardgame が終了すると減ります。  この時点では、すべての Cardgame インスタンスが削除されているため `Cardgame::totalParticipants` は 0 のはずですが、**\[ウォッチ 1\]** ウィンドウには `Cardgame::totalparticipants` が "18" と表示されています。  これは、コードにバグがあることを示しています。次の「[チュートリアル: プロジェクトのデバッグ \(C\+\+\)](../ide/walkthrough-debugging-a-project-cpp.md)」チュートリアルを完了することで、そのバグを検出して修正できます。  
  
9. プログラムを停止するために、メニュー バーで **\[デバッグ\]**、**\[デバッグの停止\]** の順に選択するか、Shift \+ F5 キーボード ショートカットを使用します。  
  
## 次の手順  
 **前へ :** [チュートリアル: プロジェクトの構築 \(C\+\+\)](../ide/walkthrough-building-a-project-cpp.md) &#124; **次へ :** [チュートリアル: プロジェクトのデバッグ \(C\+\+\)](../ide/walkthrough-debugging-a-project-cpp.md)  
  
## 参照  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/ja-jp/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [DELETE\_PENDING\_Building and Debugging](http://msdn.microsoft.com/ja-jp/9f6ba537-5ea0-46fb-b6ba-b63d657d84f1)