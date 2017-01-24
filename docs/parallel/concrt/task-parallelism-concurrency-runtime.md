---
title: "タスクの並列化 (同時実行ランタイム) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
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
  - "構造化タスク グループ [同時実行ランタイム]"
  - "構造化タスク [同時実行ランタイム]"
  - "タスク グループ [同時実行ランタイム]"
  - "タスクの並列化"
  - "タスク [同時実行ランタイム]"
ms.assetid: 42f05ac3-2098-494a-ba84-737fcdcad077
caps.latest.revision: 56
caps.handback.revision: 56
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# タスクの並列化 (同時実行ランタイム)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

同時実行ランタイムで、 *タスク* 特定のジョブを実行し、通常、他のタスクと並列で実行される作業の単位です。 タスクに分解し、タスクより細かなタスクに編成された、 *タスク グループ*します。  
  
 非同期コードを記述して、非同期操作が完了したときに操作を実行する場合に、タスクを使用します。 たとえば、ファイルから非同期的に読み取り、別のタスクを使用してタスクを使用する可能性があります:、 *継続タスク*, は、このドキュメントの後半で説明する — 使用可能になったら後にデータを処理します。 逆に、タスク グループを使用して、並列処理を分解することができます。 たとえば、残存作業を 2 つのパーティションに分割する再帰的なアルゴリズムがあるとします。 タスク グループを使用すると、これらのパーティションを同時に実行して、分割処理の完了を待つことができます。  
  
> [!TIP]
>  同じルーチンを並列でコレクションのすべての要素に適用する場合など、並列アルゴリズムの使用 [concurrency::parallel_for](../Topic/parallel_for%20Function.md), タスクまたはタスク グループではなく、します。 並列アルゴリズムの詳細については、次を参照してください。 [並列アルゴリズム](../Topic/Parallel%20Algorithms.md)します。  
  
## <a name="key-points"></a>主要なポイント  
  
-   ラムダ式に変数を渡すときに参照渡しを使用する場合、タスクが終了するまでその変数の有効期間が続くようにする必要があります。  
  
-   タスクを使用して (、 [concurrency::task](../../parallel/concrt/reference/task-class-concurrency-runtime.md) クラス) 非同期コードを記述する場合。 タスク クラスは、同時実行ランタイムではなく、Windows ThreadPool をスケジューラとして使用します。  
  
-   タスク グループを使用 (、 [concurrency::task_group](../Topic/task_group%20Class.md) クラスまたは [concurrency::parallel_invoke](../Topic/parallel_invoke%20Function.md) アルゴリズム) を並列処理に小さい部分を分解し、それらの小さな部分を完了するまで待機する場合します。  
  
-   使用して、 [concurrency::task::then](../Topic/task::then%20Method.md) 継続を作成します。 A *継続* タスクが完了した後に非同期的に実行するタスクです。 一連の非同期処理を形成するために、継続をいくつでも接続できます。  
  
-   タスク ベースの継続は、継続元タスクが取り消されたり、例外をスローした場合でも、継続元タスクが完了すると常に実行がスケジュールされます。  
  
-   使用 [concurrency:: HYPERLINK"http://msdn.microsoft.com/library/system.threading.tasks.task.whenall (v=VS.110).aspx"when_all](../Topic/when_all%20Function.md) 完了後、一連のタスクのすべてのメンバーに完了するタスクを作成します。 使用 [concurrency::when_any](../Topic/when_all%20Function.md) を一連のタスクの 1 つのメンバーが完了した後に完了するタスクを作成します。  
  
-   タスクとタスク グループは、並列パターン ライブラリ (PPL) の取り消し機構に参加できます。 詳細については、次を参照してください。 [キャンセル](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md#cancellation_in_the_ppl)します。  
  
-   タスクとタスク グループによってスローされる例外をランタイムが処理する方法については、次を参照してください。 [例外処理](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md)します。  
  
## <a name="in-this-document"></a>目次  
  
- [ラムダ式の使用](#lambdas)  
  
- [Task クラス](#task-class)  
  
- [継続タスク](#continuations)  
  
- [値ベースの継続とタスク ベースの継続](#value-versus-task)  
  
- [タスクを構成します。](#composing-tasks)  
  
    - [When_all 関数](#when-all)  
  
    - [When_any 関数](#when-any)  
  
- [遅延したタスク実行](#delayed-tasks)  
  
- [タスク グループ](#task-groups)  
  
- [Task_group structured_task_group の違いを比較します。](#comparing-groups)  
  
- [使用例](#example)  
  
- [信頼性の高いプログラミング](#robust)  
  
##  <a name="a-namelambdasa-using-lambda-expressions"></a><a name="lambdas"></a> ラムダ式の使用  
 ラムダ式は簡潔な構文であるため、タスクおよびタスク グループで実行される作業を定義する一般的な方法です。 使用のヒントを次に示します。  
  
-   通常、タスクはバックグラウンド スレッドで実行されるため、ラムダ式の変数をキャプチャする場合にはオブジェクトの有効期間に注意してください。 変数を値でキャプチャすると、その変数のコピーがラムダの本体に作成されます。 参照によってキャプチャする場合には、コピーは作成されません。 したがって、参照によってキャプチャするすべての変数の有効期間が、それを使用するタスクのために十分であるように注意します。  
  
-   タスクにラムダ式を渡す場合、スタックに割り当てられた変数を参照によってキャプチャしないようにします。  
  
-   ラムダ式でキャプチャする変数を明示して、値でのキャプチャと参照でのキャプチャを識別できるようにします。 このため、ラムダ式に対して `[=]` または `[&]` オプションを使用しないことをお勧めします。  
  
 一般的なパターンは、継続のチェーンの 1 つのタスクが変数に割り当てられ、別のタスクがその変数を読み取る場合です。 各継続タスクが変数のそれぞれのコピーを保持するため、値によるキャプチャができません。 スタック割り当て変数においても、変数が有効でなくなる場合があるため、参照によるキャプチャができません。  
  
 この問題を解決する場合など、スマート ポインターを使用して [std::shared_ptr](../../standard-library/shared-ptr-class.md), しをラップして、変数値によって、スマート ポインターを渡します。 この方法を使用すると、基になるオブジェクトが割り当てられ、読み込むことができ、それを使用するタスクのために十分な有効期間となります。 変数が Windows ランタイム オブジェクトへのポインターであったり、参照カウント ハンドル (`^`) である場合でも、この方法を使用できます。 基本的な例は次のとおりです。  
  
 [!code-cpp[concrt-lambda-task-lifetime#1](../../parallel/concrt/codesnippet/CPP/task-parallelism-concurrency-runtime_1.cpp)]  
  
 ラムダ式の詳細については、次を参照してください。 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)します。  
  
##  <a name="a-nametask-classa-the-task-class"></a><a name="task-class"></a> Task クラス  
 使用することができます、 [concurrency::task](../../parallel/concrt/reference/task-class-concurrency-runtime.md) に依存する操作の一連のタスクを構成するクラス。 このコンポジション モデルがの概念によってサポートされている *継続*します。 ときに実行される継続できるようにコード前、または *継続元*, 、タスクが完了します。 継続元タスクの結果は、1 つ以上の継続タスクへの入力として渡されます。 継続元タスクが完了すると、それを待っているすべての継続タスクが実行のためにスケジュールされます。 各継続タスクは継続元タスクの結果のコピーを受信します。 また、これらの継続タスクが、他の継続の継続元タスクである場合もあり、このようにしてタスクのチェーンが作成されます。 継続を使うと、特定の依存関係を持つ、任意の長さのタスクのチェーンを作成できます。 また、タスクは開始前または実行中に協調的に、取り消しに参加できます。 この取り消しモデルの詳細については、次を参照してください。 [キャンセル](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md#cancellation_in_the_ppl)します。  
  
 `task` はテンプレート クラスです。 型パラメーター `T` は、タスクで生成される結果の型です。 タスクが値を返さない場合には、この型は `void` となります。 `T` は `const` 修飾子を使用できません。  
  
 指定したタスクを作成するときに、 *処理関数* タスクの本体を実行します。 この処理関数には、ラムダ関数、関数ポインター、または関数オブジェクトを使用できます。 タスクの結果を取得することがなく完了を待機するを呼び出す、 [concurrency::task::wait](../Topic/task::wait%20Method.md) メソッドです。  `task::wait` メソッドが返される、 [concurrency::task_status](../Topic/task_group_status%20Enumeration.md) タスクが完了または取り消されたかどうかを示す値。 タスクの結果を取得する、 [concurrency::task_canceled](../Topic/task::get%20Method.md) メソッドです。 このメソッドは、`task::wait` を呼び出してタスクの完了を待ち、結果が使用できるようになるまで現在のスレッドの実行をブロックします。  
  
 次の例では、タスクを作成し、結果を待って、値を表示する方法を示します。 このドキュメントの例では、より簡潔な構文を提供するため、ラムダ関数を使用しています。 しかし、タスクを使用する場合には、関数ポインター、および関数オブジェクトを使用することも可能です。  
  
 [!code-cpp[concrt-basic-task#1](../../parallel/concrt/codesnippet/CPP/task-parallelism-concurrency-runtime_2.cpp)]  
  
 使用すると、 [concurrency::create_task](../Topic/create_task%20Function.md) 使用する関数、 `auto` キーワード、型を宣言するのではなく。 たとえば、単位行列を作成して印刷する、次のコードを考えてみます。  
  
 [!code-cpp[concrt-create-task#1](../../parallel/concrt/codesnippet/CPP/task-parallelism-concurrency-runtime_3.cpp)]  
  
 `create_task` 関数を使用して同等の操作を行うことができます。  
  
 [!code-cpp[concrt-create-task#2](../../parallel/concrt/codesnippet/CPP/task-parallelism-concurrency-runtime_4.cpp)]  
  
 タスクの実行時に例外がスローされた場合、ランタイムは、それ以降の `task::get` または `task::wait` の呼び出し、またはタスク ベースの継続への呼び出しで、その例外をマーシャリングします。 タスクの例外処理機構の詳細については、次を参照してください。 [例外処理](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md)します。  
  
 使用例について `task`, 、[concurrency::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md), 、キャンセルを参照してください [チュートリアル: を使用してタスクの接続および XML HTTP 要求](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)します。 (`task_completion_event` クラスについてはドキュメントの後の部分で説明されています。)  
  
> [!TIP]
>  タスクに固有の詳細については、 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 、アプリを参照してください [C++ での非同期プログラミング](http://msdn.microsoft.com/ja-jp/512700b7-7863-44cc-93a2-366938052f31) と [Windows ストア アプリ用 C++ で非同期操作を行う](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)します。  
  
##  <a name="a-namecontinuationsa-continuation-tasks"></a><a name="continuations"></a> 継続タスク  
 非同期プログラミングでは、非同期操作で完了時に 2 番目の操作を呼び出してデータを渡すのが一般的です。 これまで、この処理はコールバック メソッドを使用して行っていました。 によって、同時実行ランタイムで同じ機能が提供される *継続タスク*します。 継続タスクを (だけ継続とも呼ばれます) と呼ばれる別のタスクによって呼び出される非同期タスク、 *継続元*, 、継続元が完了したときにします。 継続を使用して、次の操作を行うことができます。  
  
-   継続元のデータを継続に渡します。  
  
-   継続を呼び出す場合、呼び出さない場合についての正確な条件を指定します。  
  
-   継続が開始される前、または継続の実行中に、継続を取り消します。  
  
-   継続をスケジュールする方法についてのヒントを提供します。 (この方法は、[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリケーションだけで使用できます。 詳細については、次を参照してください [Windows ストア アプリ用 C++ で非同期操作を行う](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)。)。  
  
-   同じ継続元から複数の継続を呼び出します。  
  
-   複数の継続元のすべてまたはいずれかが完了したときに 1 つの継続を呼び出します。  
  
-   任意の長さで連続して継続を実行します。  
  
-   継続元によってスローされた例外を処理するために継続を使用します。  
  
 これらの機能を使うと、最初のタスクが完了したときに、1 つ以上のタスクを実行できます。 たとえば、最初のタスクがディスクからデータを読み取った後に、ファイルを圧縮する継続を作成できます。  
  
 次の例を使用する 1 つ前の変更、 [concurrency::task::then](../Topic/task::then%20Method.md) メソッドがある場合は、継続元タスクの値を出力する継続をスケジュールします。  
  
 [!code-cpp[concrt-basic-continuation#1](../../parallel/concrt/codesnippet/CPP/task-parallelism-concurrency-runtime_5.cpp)]  
  
 タスクを任意の長さにチェーンしたり、入れ子にできます。 またタスクは、複数の継続を持つことができます。 次の例では、前のタスクの値を 3 回インクリメントする、基本的な継続のチェーンを示しています。  
  
 [!code-cpp[concrt-continuation-chain#1](../../parallel/concrt/codesnippet/CPP/task-parallelism-concurrency-runtime_6.cpp)]  
  
 継続は、別のタスクを返すこともできます。 取り消されない場合、このタスクは後続の継続の前に実行されます。 この手法と呼ばれる *非同期ラッピング解除*します。 非同期ラッピング解除は、追加の作業をバックグラウンドで実行するときに、現在のタスクが現在のスレッドをブロックしないようにする場合に役立ちます。 (これは、継続が UI スレッドで実行される [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリケーションで共通です。) 次の例は、3 つのタスクを示しています。 最初のタスクは、継続タスクの前に実行される、別のタスクを返します。  
  
 [!code-cpp[concrt-async-unwrapping#1](../../parallel/concrt/codesnippet/CPP/task-parallelism-concurrency-runtime_7.cpp)]  
  
> [!IMPORTANT]
>  タスクの継続が `N` 型の入れ子のタスクを返す場合、結果のタスクは `N` 型でなく `task<N>` 型となり、入れ子のタスクが完了すると終了します。 つまり、継続は入れ子のタスクのラッピング解除を行います。  
  
##  <a name="a-namevalue-versus-taska-value-based-versus-task-based-continuations"></a><a name="value-versus-task"></a> 値ベースの継続とタスク ベースの継続  
 `task` オブジェクトは戻り値の型が `T` であるため、その継続タスクに `T` または `task<T>` 型の値を指定できます。 型を受け取る継続 `T` と呼ばれる、 *値ベースの継続*します。 値ベースの継続は、継続元タスクがエラーなしに完了して取り消されない場合に、実行のためにスケジュールされます。 型を受け取る継続 `task<T>` ように、パラメーターと呼ばれる、 *タスク ベースの継続*します。 タスク ベースの継続は、継続元タスクが取り消されたり、例外をスローした場合でも、継続元タスクが完了すると常に実行がスケジュールされます。 次に `task::get` を呼び出して、継続元タスクの結果を取得できます。 継続元タスクが取り消された場合 `task::get` スロー [concurrency::task_canceled](../../parallel/concrt/reference/task-canceled-class.md)します。 継続元タスクが例外をスローすると、`task::get` は再度、例外をスローします。 タスク ベースの継続は、その継続元タスクが取り消された場合、取り消し済みとしてマークされません。  
  
##  <a name="a-namecomposing-tasksa-composing-tasks"></a><a name="composing-tasks"></a> タスクを構成します。  
 このセクションで説明、 [concurrency::when_all](../Topic/when_all%20Function.md) と [concurrency::when_any](../Topic/when_all%20Function.md) するのに役立つ関数は、一般的なパターンを実装するための複数のタスクを作成します。  
  
###  <a name="a-namewhen-alla-the-whenall-function"></a><a name="when-all"></a> When_all 関数  
 `when_all` 関数は、一連のタスクの完了後に完了するタスクを生成します。 この関数は、std を返します::[ベクトル](../../standard-library/vector-class.md) 、セット内の各タスクの結果を含むオブジェクト。 次の基本的な例では、`when_all` を使用して、3 つの他のタスクの完了を表すタスクを作成します。  
  
 [!code-cpp[concrt-join-tasks#1](../../parallel/concrt/codesnippet/CPP/task-parallelism-concurrency-runtime_8.cpp)]  
  
> [!NOTE]
>  `when_all` に渡すタスクは均一である必要があります。 つまり、これらはすべて同じ型を返す必要があります。  
  
 次に示す例のように、`&&` 構文を使用して、一連のタスクの完了後に完了するタスクを生成することもできます。  
  
 `auto t = t1 && t2; // same as when_all`  
  
 通常は、継続を `when_all` と共に使用して、一連のタスクが終了した後に操作を実行します。 前の例を変更した次の例では、それぞれが `int` の結果を生成する、3 つのタスクの合計を印刷します。  
  
 [!code-cpp[concrt-join-tasks#2](../../parallel/concrt/codesnippet/CPP/task-parallelism-concurrency-runtime_9.cpp)]  
  
 この例で指定することも`task<vector<int>>` タスク ベースの継続を作成します。  
  
 一連のタスクのいずれかのタスクが取り消されたり、例外をスローした場合、`when_all` は残りのタスクを完了を待たずに、直ちに終了します。 例外がスローされた場合、`task::get` を返すタスク オブジェクトで `task::wait` または `when_all` を呼び出すと、ランタイムは再度、例外をスローします。 複数のタスクからスローすると、ランタイムはその中の 1 つを選択します。 したがって、すべてのタスクが完了してからすべての例外を確認するようにします。タスクの例外がハンドルされない場合、アプリケーションは終了します。  
  
 プログラムがすべての例外を確認するために使用できるユーティリティ関数を次に示します。 指定された範囲のタスクごとに、`observe_all_exceptions` は再スローされる例外をトリガーし、その例外を受け取ります。  
  
 [!code-cpp[concrt-eh-when_all#1](../../parallel/concrt/codesnippet/CPP/task-parallelism-concurrency-runtime_10.cpp)]  
  
 C++ と XAML を使用し、ディスクに一連のファイルを書き込む [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリケーションを考えてみます。 次の例は、`when_all` と `observe_all_exceptions` を使用して、プログラムがすべての例外を確認する方法を示します。  
  
 [!code-cpp[concrt-eh-when_all#2](../../parallel/concrt/codesnippet/CPP/task-parallelism-concurrency-runtime_11.cpp)]  
  
##### <a name="to-run-this-example"></a>この例を実行するには  
  
1.  MainPage.xaml で、`Button` コントロールを追加します。  
  
 [!code-xml[concrt-eh-when_all#3](../../parallel/concrt/codesnippet/Xaml/task-parallelism-concurrency-runtime_12.xaml)]  
  
2.  MainPage.xaml.h で、これらの事前宣言を `private` クラス宣言の `MainPage` セクションに追加します。  
  
 [!code-cpp[concrt-eh-when_all#4](../../parallel/concrt/codesnippet/CPP/task-parallelism-concurrency-runtime_13.h)]  
  
3.  MainPage.xaml.cpp で、`Button_Click` イベント ハンドラーを実装します。  
  
 [!code-cpp[concrt-eh-when_all#5](../../parallel/concrt/codesnippet/CPP/task-parallelism-concurrency-runtime_14.cpp)]  
  
4.  MainPage.xaml.cpp で、例に示すように `WriteFilesAsync` を実装します。  
  
> [!TIP]
> `when_all` は、その結果、`task` を生成する、非ブロッキング関数です。 異なり [task::wait](../Topic/task::wait%20Method.md), でこの関数の呼び出しは安全では、 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 、ASTA (アプリケーション STA) スレッド上のアプリケーションです。  
  
###  <a name="a-namewhen-anya-the-whenany-function"></a><a name="when-any"></a> When_any 関数  
 `when_any` 関数は、一連のタスクの最初のタスクの完了後に完了するタスクを生成します。 この関数が返す、 [std::pair](../../standard-library/pair-structure.md) 完了したタスクの結果と、セット内には、そのタスクのインデックスを含むオブジェクト。  
  
 `when_any` 関数は、特に次のシナリオに役立ちます。  
  
-   重複した操作。 多くの方法で実行できるアルゴリズムまたは操作を検討してください。 `when_any` 関数を使用すると、最初の操作を完了して残りの操作を取り消すように、操作を選択できます。  
  
-   インタリーブされた操作。 複数の操作を開始して、それらの操作のすべてが完了し、各操作が完了したら `when_any` 関数を使って結果を処理するようにできます。 1 つの操作が完了したら、1 つ以上の追加タスクを開始できます。  
  
-   制限された操作。 `when_any` 関数を使用して、前のシナリオを拡張し、同時操作の数を制限することができます。  
  
-   有効期限切れの操作。 `when_any` 関数を使用して、1 つ以上のタスクと特定の時間以降に完了する 1 つのタスクから選択することができます。  
  
 `when_all` と同様に、通常は継続を `when_any` と共に使用して、一連タスクの最初のタスクが終了した後に操作を実行します。 次の基本的な例では、`when_any` を使用して、他の 3 つのタスクの最初のタスクが完了したときに完了するタスクを作成します。  
  
 [!code-cpp[concrt-select-task#1](../../parallel/concrt/codesnippet/CPP/task-parallelism-concurrency-runtime_15.cpp)]  
  
 この例では、タスク ベースの継続を作成するために `task<pair<int, size_t>>` を指定することもできます。  
  
> [!NOTE]
>  `when_all` と同様に、`when_any` に渡すタスクはすべて同じ型を返す必要があります。  
  
 次に示す例のように、`||` 構文を使用して、一連のタスクの最初のタスクの完了後に完了するタスクを生成することもできます。  
  
 `auto t = t1 || t2; // same as when_any`  
  
> [!TIP]
>  `when_all` と同様に、`when_any` は非ブロッキングであり、ASTA スレッドの [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリケーションで呼び出しても安全です。  
  
##  <a name="a-namedelayed-tasksa-delayed-task-execution"></a><a name="delayed-tasks"></a> 遅延したタスク実行  
 条件が満たされるまで、または外部イベントに応答してタスクを開始するまで、タスクの実行を遅延する必要がある場合があります。 たとえば、非同期プログラミングでは、I/O 完了のイベントに応答してタスクを開始する必要があります。  
  
 これを実現する 2 とおりの方法は、継続を使用するか、タスクを開始してタスクの処理関数の中でイベントを待つことです。 しかし、これらの方法の 1 つを使用できない場合もあります。 たとえば、継続を作成するためには、継続元タスクが必要です。 ただし、継続元タスクがない、作成、 *タスクの完了イベント* し、後で使用可能になったらときに、継続元タスクには、その完了イベントをチェーンします。 また、待機中のタスクはスレッドをブロックするため、タスクの完了イベントを使用して、非同期操作が完了したときに処理を行い、スレッドを解放することもできます。  
  
  [Concurrency::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md) クラスは、このようなタスクの構成を簡略化します。 `task` クラスと同様に、型パラメーター `T` は、タスクで生成される結果の型です。 タスクが値を返さない場合には、この型は `void` となります。 `T` は `const` 修飾子を使用できません。 通常、`task_completion_event` オブジェクトは、値が使用できるようになると通知する、スレッドまたはタスクに提供されます。 同時に、1 つ以上のタスクは、そのイベントのリスナーとして設定されます。 イベントが設定されると、リスナー タスクが完了し、継続が実行されるようにスケジュールされます。  
  
 使用例について `task_completion_event` 、遅延後に完了するタスクを実装するのを参照してください。 [方法: その完了後に、遅延にタスクを作成](../../parallel/concrt/how-to-create-a-task-that-completes-after-a-delay.md)します。  
  
##  <a name="a-nametask-groupsa-task-groups"></a><a name="task-groups"></a> タスク グループ  
 A *タスク グループ* タスクのコレクションを整理します。 タスク グループでは、ワーク スティーリング キューにタスクを置きます。 スケジューラはこのキューからタスクを削除し、使用できるコンピューティング リソースでそのタスクを実行します。 タスク グループにタスクを追加した場合、すべてのタスクが終了するまで待機することも、まだ開始されていないタスクを取り消すこともできます。  
  
 PPL を使用して、 [concurrency::task_group](../Topic/task_group%20Class.md) と [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) タスク グループを表すクラス、および [concurrency::task_handle](../../parallel/concrt/reference/task-handle-class.md) をこれらのグループで実行されるタスクを表すクラス。 `task_handle` クラスは、処理を行うコードをカプセル化します。 `task` クラスと同様に、この処理関数には、ラムダ関数、関数ポインター、または関数オブジェクトを使用できます。 通常、`task_handle` オブジェクトを直接操作する必要はありません。 代わりに、タスク グループに処理関数を渡します。タスク グループによって `task_handle` オブジェクトが作成および管理されます。  
  
 タスク グループこれら 2 つのカテゴリに分類: *非構造化タスク グループ* と *タスク グループを構造化*します。 PPL では、`task_group` クラスを使用して非構造化タスク グループを表し、`structured_task_group` クラスを使用して構造化タスク グループを表します。  
  
> [!IMPORTANT]
>  PPL も定義、 [concurrency::parallel_invoke](../Topic/parallel_invoke%20Function.md) 使用するアルゴリズムを `structured_task_group` 一連のタスクを並列に実行するクラス。 `parallel_invoke` アルゴリズムにはより簡潔な構文が用意されているため、可能であれば `structured_task_group` クラスの代わりに使用することをお勧めします。 トピック [並列アルゴリズム](../Topic/Parallel%20Algorithms.md) 説明 `parallel_invoke` さらに詳しくします。  
  
 `parallel_invoke` は、同時に実行する独立したタスクが複数あり、すべてのタスクが終了するまで待機してから処理を続行する必要がある場合に使用します。 この手法と呼ば *分岐と結合* 並列処理します。 `task_group` は、同時に実行する独立したタスクが複数あり、それらのタスクが終了するタイミングがまだ先である場合に使用します。 たとえば、`task_group` オブジェクトにタスクを追加して、それらのタスクが別の関数や別のストレッドで終了するまで待機できます。  
  
 タスク グループでは、キャンセル処理の概念がサポートされています。 キャンセル処理を使用すると、操作全体を取り消すことをアクティブなすべてのタスクに通知できます。 また、キャンセル処理により、まだ開始されていないタスクが実行されるのを防止できます。 キャンセルの詳細については、次を参照してください。 [キャンセル](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md#cancellation_in_the_ppl)します。  
  
 また、ランタイムでは、例外処理モデルを使用することによって、タスクから例外をスローし、関連するタスク グループが終了するまで待機しているときにその例外を処理できます。 この例外処理モデルの詳細については、次を参照してください。 [例外処理](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md)します。  
  
##  <a name="a-namecomparing-groupsa-comparing-taskgroup-to-structuredtaskgroup"></a><a name="comparing-groups"></a> Task_group structured_task_group の違いを比較します。  
 `task_group` クラスの代わりに `parallel_invoke` または `structured_task_group` を使用することが推奨されますが、可変個のタスクを実行する並列アルゴリズムやキャンセル処理のサポートが必要な並列アルゴリズムを記述する場合など、`structured_task_group` を使用した方がよい場合もあります。 ここでは、`task_group` クラスと `structured_task_group` クラスの違いについて説明します。  
  
 `task_group` クラスはスレッド セーフです。 したがって、複数のスレッドから `task_group` オブジェクトにタスクを追加したり、複数のスレッドから `task_group` オブジェクトに対して待機や取り消しの操作を行ったりしてもかまいません。 `structured_task_group` オブジェクトの構築と破棄は、同じ構文のスコープで行う必要があります。 また、`structured_task_group` オブジェクトに対する操作はすべて同じスレッドで行う必要があります。 このルールの例外は、 [concurrency::structured_task_group::cancel](../Topic/structured_task_group::cancel%20Method.md) と [:is_canceling](../Topic/structured_task_group::is_canceling%20Method.md) メソッドです。 子タスクでこれらのメソッドを呼び出すことで、任意のタイミングで親タスク グループを取り消したり、取り消し処理をチェックしたりできます。  
  
 その他のタスクを実行する、 `task_group` オブジェクトを呼び出した後、 [:wait](../Topic/task_group::wait%20Method.md) または [concurrency::task_group::run_and_wait](../Topic/task_group::run_and_wait%20Method.md) メソッドです。 逆でその他のタスクを実行する場合、 `structured_task_group` オブジェクトを呼び出した後、 [:structured_task_group](../Topic/structured_task_group::wait%20Method.md) または [concurrency::structured_task_group::run_and_wait](../Topic/structured_task_group::run_and_wait%20Method.md) メソッド、動作は未定義です。  
  
 `structured_task_group` クラスはスレッド間で同期されないため、実行に伴うオーバーヘッドが `task_group` クラスよりも少なくなります。 したがって、複数のスレッドから処理をスケジュールする必要のない問題に対処する場合に、`parallel_invoke` アルゴリズムを使用できないときは、`structured_task_group` クラスを使用すると、よりパフォーマンスの高いコードを作成できます。  
  
 `structured_task_group` オブジェクトを別の `structured_task_group` オブジェクト内で使用する場合は、外部オブジェクトが終了する前に内部オブジェクトが終了して破棄される必要があります。 `task_group` クラスの場合、外部グループが終了する前に、入れ子になったタスク グループが終了する必要はありません。  
  
 非構造化タスク グループと構造化タスク グループでは、さまざまな方法でタスク ハンドルを操作します。 `task_group` オブジェクトには処理関数を直接渡すことができます。`task_group` オブジェクトによってタスク ハンドルが自動的に作成および管理されます。 `structured_task_group` クラスを使用する場合は、タスクごとに `task_handle` オブジェクトを管理する必要があります。 各 `task_handle` オブジェクトは、関連する `structured_task_group` オブジェクトの有効期間を通じて有効である必要があります。 使用して、 [concurrency::make_task](../Topic/make_task%20Function.md) を作成する関数、 `task_handle` オブジェクトを次の基本的な例で示すようにします。  
  
 [!code-cpp[concrt-make-task-structure#1](../../parallel/concrt/codesnippet/CPP/task-parallelism-concurrency-runtime_16.cpp)]  
  
 可変個のタスクがある場合のタスク ハンドルを管理する場合は、などのスタック割り当てルーチンを使用して [_malloca](../../c-runtime-library/reference/malloca.md) または std などのコンテナー クラス::[ベクトル](../../standard-library/vector-class.md)します。  
  
 `task_group` と `structured_task_group` の両方でキャンセル処理がサポートされています。 キャンセルの詳細については、次を参照してください。 [キャンセル](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md#cancellation_in_the_ppl)します。  
  
##  <a name="a-nameexamplea-example"></a><a name="example"></a> 使用例  
 次の簡単な例では、タスク グループの操作方法を示します。 この例では、`parallel_invoke` アルゴリズムを使用して、2 つのタスクを同時に実行します。 各タスクでは、サブタスクを `task_group` オブジェクトに追加します。 `task_group` クラスを使用した場合、複数のタスクでタスクを同時に追加できることに注意してください。  
  
 [!code-cpp[concrt-using-task-groups#1](../../parallel/concrt/codesnippet/CPP/task-parallelism-concurrency-runtime_17.cpp)]  
  
 この例のサンプル出力を次に示します。  
  
```Output  
Message from task: Hello  
Message from task: 3.14  
Message from task: 42  
```  
  
 `parallel_invoke` アルゴリズムではタスクを同時に実行するため、出力メッセージの順序が変わる可能性があります。  
  
 使用する方法を示す完全な例について、 `parallel_invoke` アルゴリズムを参照してください [方法: parallel.invoke を使用して並列並べ替えルーチンを記述する](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md) と [方法: 並列操作を実行する parallel.invoke を使用して](../Topic/How%20to:%20Use%20parallel_invoke%20to%20Execute%20Parallel%20Operations.md)します。 使用する完全な例については、 `task_group` を参照してください、非同期フューチャを実装するクラス [チュートリアル: フューチャの実装](../../parallel/concrt/walkthrough-implementing-futures.md)します。  
  
##  <a name="a-namerobusta-robust-programming"></a><a name="robust"></a> 信頼性の高いプログラミング  
 タスク、タスク グループ、および並列アルゴリズムを使用する場合は、キャンセル処理と例外処理の役割を十分に理解しておいてください。 たとえば、並列処理ツリーでタスクを取り消すと、子タスクも実行されなくなります。 そのため、アプリケーションで重要となる操作 (リソースの解放など) が子タスクのいずれかで実行されるような場合に問題となります。 また、子タスクが例外をスローすると、その例外がオブジェクトのデストラクターを介して反映され、アプリケーションで未定義の動作が発生する可能性があります。 をこれらのポイントを示す例を参照してください。、 [理解する方法のキャンセル機能と例外処理に影響を与えるオブジェクトが破棄ついて](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md#object-destruction) 並列パターン ライブラリのドキュメントのベスト プラクティスです。 キャンセルと PPL での例外処理モデルの詳細については、次を参照してください。 [キャンセル](../../parallel/concrt/cancellation-in-the-ppl.md) と [例外処理](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md)します。  
  
## <a name="related-topics"></a>関連トピック  
  
|タイトル|説明|  
|-----------|-----------------|  
|[方法: parallel.invoke を使用して並列並べ替えルーチンを記述するには](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)|`parallel_invoke` アルゴリズムを使用して、バイトニック ソート アルゴリズムのパフォーマンスを向上させる方法について説明します。|  
|[方法: 並列操作を実行する parallel.invoke を使用して](../Topic/How%20to:%20Use%20parallel_invoke%20to%20Execute%20Parallel%20Operations.md)|`parallel_invoke` アルゴリズムを使用して、共有データ ソースに対して複数の操作を実行するプログラムのパフォーマンスを向上させる方法について説明します。|  
|[方法: 遅延後に完了するタスクを作成します。](../../parallel/concrt/how-to-create-a-task-that-completes-after-a-delay.md)|使用する方法を示しています、 `task`, 、`cancellation_token_source`, 、`cancellation_token`, 、および `task_completion_event` 、遅延後に完了するタスクを作成するクラス。|  
|[チュートリアル: フューチャの実装](../../parallel/concrt/walkthrough-implementing-futures.md)|同時実行ランタイムの既存の機能を組み合わせて、より効果的に使用する方法を示します。|  
|[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|同時実行アプリケーションの開発に不可欠なプログラミング モデルを提供する PPL について説明します。|  
  
## <a name="reference"></a>参照  
 [task クラス (同時実行ランタイム)](../../parallel/concrt/reference/task-class-concurrency-runtime.md)  
  
 [task_completion_event クラス](../../parallel/concrt/reference/task-completion-event-class.md)  
  
 [when_all 関数](../Topic/when_all%20Function.md)  
  
 [when_any 関数](../Topic/when_any%20Function.md)  
  
 [task_group クラス](../Topic/task_group%20Class.md)  
  
 [parallel_invoke 関数](../Topic/parallel_invoke%20Function.md)  
  
 [structured_task_group クラス](../../parallel/concrt/reference/structured-task-group-class.md)
