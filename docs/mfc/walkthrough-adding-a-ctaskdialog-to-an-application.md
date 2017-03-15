---
title: "チュートリアル: アプリケーションへの CTaskDialog の追加 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTaskDialog, 追加"
  - "チュートリアル [C++], ダイアログ"
ms.assetid: 3a62abb8-2d86-4bec-bdb8-5784d5f9a9f8
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# チュートリアル: アプリケーションへの CTaskDialog の追加
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このチュートリアルでは、[CTaskDialog クラス](../mfc/reference/ctaskdialog-class.md)の概要と、そのクラスをアプリケーションに追加する方法について説明します。  
  
 `CTaskDialog` は、[!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)] の Windows メッセージ ボックスに代わるタスク ダイアログ ボックスです。`CTaskDialog` は Windows メッセージ ボックスを改良したものであり、機能も追加されます。[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] では、Windows メッセージ ボックスも引き続きサポートされます。  
  
> [!NOTE]
>  [!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)] より前のバージョンの Windows は、`CTaskDialog` をサポートしていません。 以前のバージョンの Windows でアプリケーションを実行するユーザーにもメッセージを表示するには、代替のダイアログ ボックス オプションをプログラミングしておく必要があります。 静的メソッドである [CTaskDialog::IsSupported](../Topic/CTaskDialog::IsSupported.md) を使用することで、ユーザーのコンピューターで `CTaskDialog` を表示できるかどうかを実行時に判断できます。 また、`CTaskDialog` を使用できるのは、アプリケーションが Unicode ライブラリを使用してビルドされている場合に限られます。  
  
 `CTaskDialog` では、情報を収集して表示するためのオプション要素がいくつかサポートされています。 たとえば、`CTaskDialog` では、コマンド リンク、カスタマイズされたボタン、カスタマイズされたアイコン、およびフッターを表示できます。 さらに、`CTaskDialog` には、タスク ダイアログ ボックスの状態を照会して、ユーザーが選択したオプション要素を確認するためのメソッドもいくつか用意されています。  
  
## 必須コンポーネント  
 このチュートリアルを実行するには、次のコンポーネントが必要です。  
  
-   [!INCLUDE[vs_dev10_long](../build/includes/vs_dev10_long_md.md)]  
  
-   [!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
## Windows メッセージ ボックスを CTaskDialog に置き換える  
 次の手順では、`CTaskDialog` の最も基本的な使用法である、Windows メッセージ ボックスの置き換えについて説明します。 この例では、タスク ダイアログ ボックスに関連付けられているアイコンも変更します。 アイコンを変更することで、`CTaskDialog` の外観が Windows メッセージ ボックスと同じになります。  
  
#### Windows メッセージ ボックスを CTaskDialog に置き換えるには  
  
1.  既定の設定で、新しい MFC アプリケーション プロジェクトを作成します。 このプロジェクトに `MyProject` という名前を付けます。  
  
2.  **ソリューション エクスプローラー**を使用して、MyProject.cpp ファイルを開きます。  
  
3.  一連の include の末尾に、`#include "afxtaskdialog.h"` を追加します。  
  
4.  `CMyProjectApp::InitInstance` メソッドを探します。 次のコード行を `return TRUE;` ステートメントの前に挿入します。 このコードにより、Windows メッセージ ボックスまたは `CTaskDialog` で使用する文字列が作成されます。  
  
    ```  
    CString message("My message to the user");  
    CString dialogTitle("My Task Dialog title");  
    CString emptyString;  
    ```  
  
5.  手順 4. のコードの後に、次のコードを追加します。 このコードによって、ユーザーのコンピューターで `CTaskDialog` がサポートされることが保証されます。 このダイアログがサポートされない場合は、代わりに Windows メッセージ ボックスが表示されます。  
  
    ```  
    if (CTaskDialog::IsSupported())  
    {  
  
    }  
    else  
    {  
       AfxMessageBox(message);  
    }  
    ```  
  
6.  手順 5. の `if` ステートメントの後にあるかっこ内に、次のコードを挿入します。 このコードによって、`CTaskDialog` が作成されます。  
  
    ```  
    CTaskDialog taskDialog(message, emptyString, dialogTitle, TDCBF_OK_BUTTON);  
    ```  
  
7.  その次の行に、次のコードを追加します。 このコードによって、警告アイコンが設定されます。  
  
    ```  
    taskDialog.SetMainIcon(TD_WARNING_ICON);  
    ```  
  
8.  その次の行に、次のコードを追加します。 このコードによって、タスク ダイアログ ボックスが表示されます。  
  
    ```  
    taskDialog.DoModal();  
    ```  
  
 `CTaskDialog` で Windows メッセージ ボックスと同じアイコンを表示しない場合は、手順 7. を省略できます。 その手順を省略すると、`CTaskDialog` が表示されるときにアイコンは表示されません。  
  
 アプリケーションをコンパイルして実行します。 アプリケーションの起動後、タスク ダイアログ ボックスが表示されます。  
  
## CTaskDialog に機能を追加する  
 次の手順では、前の手順で作成した `CTaskDialog` に機能を追加する方法を説明します。 コード例は、ユーザーの選択に基づいて特定の指示を実行する方法を示しています。  
  
#### CTaskDialog に機能を追加するには  
  
1.  **\[リソース ビュー\]** 移動します。**\[リソース ビュー\]** が表示されていない場合は、**\[表示\]** メニューから開くことができます。  
  
2.  **\[リソース ビュー\]** を展開して、**\[ストリング テーブル\]** フォルダーを選択します。 そのフォルダーを展開し、**\[ストリング テーブル\]** エントリをダブルクリックします。  
  
3.  ストリング テーブルの一番下までスクロールし、新しいエントリを追加します。 ID を `TEMP_LINE1` に変更します。 キャプションを「**Command Line 1**」に設定します。  
  
4.  新しいエントリをもう 1 つ追加します。 ID を `TEMP_LINE2` に変更します。 キャプションを「**Command Line 2**」に設定します。  
  
5.  MyProject.cpp に戻ります。  
  
6.  `CString emptyString;` の後に、次のコードを追加します。  
  
    ```  
    CString expandedLabel("Hide extra information");  
    CString collapsedLabel("Show extra information");  
    CString expansionInfo("This is the additional information to the user,\nextended over two lines.");  
    ```  
  
7.  `taskDialog.DoModal()` ステートメントを探し、そのステートメントを次のコードに置き換えます。 このコードによってタスク ダイアログ ボックスが更新され、新しいコントロールが追加されます。  
  
    ```  
    taskDialog.SetMainInstruction(L"Warning");  
    taskDialog.SetCommonButtons(TDCBF_YES_BUTTON | TDCBF_NO_BUTTON | TDCBF_CANCEL_BUTTON);  
    taskDialog.LoadCommandControls(TEMP_LINE1, TEMP_LINE2);  
    taskDialog.SetExpansionArea(expansionInfo, collapsedLabel, expandedLabel);  
    taskDialog.SetFooterText(L"This is the a small footnote to the user");  
    taskDialog.SetVerificationCheckboxText(L"Remember your selection");  
    ```  
  
8.  ユーザーにタスク ダイアログ ボックスを表示し、ユーザーの選択内容を取得する次のコード行を追加します。  
  
    ```  
    INT_PTR result = taskDialog.DoModal();  
    ```  
  
9. 次のコードを `taskDialog.DoModal()` の呼び出しの後に挿入します。 このコード セクションで、ユーザーの入力が処理されます。  
  
    ```  
    if (taskDialog.GetVerificationCheckboxState() )  
    {  
       // PROCESS IF the user selects the verification checkbox   
    }  
  
    switch (result)  
    {  
       case TEMP_LINE1:  
          // PROCESS IF the first command line  
          break;  
       case TEMP_LINE2:  
          // PROCESS IF the second command line  
          break;  
       case IDYES:  
          // PROCESS IF the user clicks yes  
          break;  
       case IDNO:  
          // PROCESS IF the user clicks no  
          break;  
       case IDCANCEL:  
          // PROCESS IF the user clicks cancel  
          break;  
       default:  
          // This case should not be hit because closing the dialog box results in IDCANCEL  
          break;  
    }  
    ```  
  
 手順 9. のコード内で、PROCESS IF で始まるコメント行を、指定された条件で実行するコードに置き換えます。  
  
 アプリケーションをコンパイルして実行します。 新しいコントロールと追加した情報を使用するタスク ダイアログ ボックスが表示されます。  
  
## CTaskDialog オブジェクトを作成せずに CTaskDialog を表示する  
 次の手順では、最初に `CTaskDialog` オブジェクトを作成せずに `CTaskDialog` を表示する方法を説明します。 この例は、前述の手順の続きです。  
  
#### CTaskDialog オブジェクトを作成せずに CTaskDialog を表示するには  
  
1.  MyProject.cpp ファイルが開いていない場合は、そのファイルを開きます。  
  
2.  `if (CTaskDialog::IsSupported())` ステートメントの右角かっこにカーソルを移動します。  
  
3.  `if` ステートメントの右角かっこの直前 \(`else` ブロックの前\) に、次のコードを挿入します。  
  
    ```  
    HRESULT result2 = CTaskDialog::ShowDialog(L"My error message", L"Error", L"New Title", TEMP_LINE1, TEMP_LINE2);  
    ```  
  
 アプリケーションをコンパイルして実行します。 2 つのタスク ダイアログ ボックスが表示されます。 最初のダイアログ ボックスは「CTaskDialog に機能を追加するには」の手順で作成したものです。今回の手順で作成したのは 2 番目のダイアログ ボックスです。  
  
 上記の例では、`CTaskDialog` で使用できるオプションの一部しか紹介していませんが、開発を始めるうえで参考になるでしょう。 このクラスの詳細については、「[CTaskDialog クラス](../mfc/reference/ctaskdialog-class.md)」を参照してください。  
  
## 参照  
 [ダイアログ ボックス](../mfc/dialog-boxes.md)   
 [CTaskDialog クラス](../mfc/reference/ctaskdialog-class.md)   
 [CTaskDialog::CTaskDialog](../Topic/CTaskDialog::CTaskDialog.md)