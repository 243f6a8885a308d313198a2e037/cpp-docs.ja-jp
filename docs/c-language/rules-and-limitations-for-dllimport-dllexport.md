---
title: "dllimport/dllexport に関する規則と制限 | Microsoft Docs"
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
  - "dllexport 属性 [C++]"
  - "dllexport 属性 [C++], 制約と規則"
  - "dllimport 属性 [C++], 制約と規則"
ms.assetid: 274b735f-ab9c-4b07-8d0e-fdb65d664634
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# dllimport/dllexport に関する規則と制限
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
-   **dllimport** 属性または `dllexport` 属性を指定しないで関数を宣言した場合、その関数は DLL インターフェイスの一部とは見なされません。  したがって、関数の定義は、該当のモジュール内か、同じプログラムの別のモジュール内に存在している必要があります。  関数を DLL インターフェイスに含める場合は、その関数の定義を他のモジュールで `dllexport` として宣言する必要があります。  それ以外の場合、リンカー エラーがクライアントのビルド時に生成されます。  
  
-   プログラムの 1 つのモジュールに、同じ関数の **dllimport** 宣言と `dllexport` 宣言が含まれる場合は、`dllexport` 属性が **dllimport** 属性よりも優先されます。  ただし、コンパイラの警告が生成されます。  次に例を示します。  
  
    ```  
    #define DllImport   __declspec( dllimport )  
    #define DllExport   __declspec( dllexport )  
  
       DllImport void func1( void );  
       DllExport void func1( void );   /* Warning; dllexport */  
                                       /* takes precedence. */  
  
    ```  
  
-   **dllimport** 属性で宣言されたデータ オブジェクトのアドレスで静的なデータ ポインターを初期化することはできません。  たとえば、次のコードはエラーになります。  
  
    ```  
    #define DllImport   __declspec( dllimport )  
    #define DllExport   __declspec( dllexport )  
  
       DllImport int i;  
       .  
       .  
       .  
       int *pi = &i;                           /* Error */  
  
       void func2()  
       {  
          static int *pi = &i;                   /* Error */  
       }  
  
    ```  
  
-   **dllimport** と宣言された関数のアドレスで静的関数ポインターを初期化すると、ポインターは、関数のアドレスではなく、DLL のインポート サンク \(制御を関数に渡すコード スタブ\) のアドレスに設定されます。  この代入はエラー メッセージを生成しません。  
  
    ```  
    #define DllImport   __declspec( dllimport )  
    #define DllExport   __declspec( dllexport )  
  
       DllImport void func1( void   
       .  
       .  
       .  
       static void ( *pf )( void ) = &func1;   /* No Error */  
  
       void func2()  
       {  
          static void ( *pf )( void ) = &func1;  /* No Error */  
       }  
  
    ```  
  
-   `dllexport` 属性が含まれたオブジェクト宣言のあるプログラムでは、そのオブジェクトを定義している必要があるため、グローバルまたはローカルの静的関数ポインターを、`dllexport` 関数のアドレスで初期化できます。  同様に、`dllexport` データ オブジェクトのアドレスで、グローバルまたはローカルの静的データ ポインターを初期化できます。  次に例を示します。  
  
    ```  
    #define DllImport   __declspec( dllimport )  
    #define DllExport   __declspec( dllexport )  
  
       DllImport void func1( void );  
       DllImport int i;  
  
       DllExport void func1( void );  
       DllExport int i;  
       .  
       .  
       .  
       int *pi = &i;                            /* Okay */  
       static void ( *pf )( void ) = &func1;    /* Okay */  
  
       void func2()  
       {  
          static int *pi = i;                     /* Okay */  
          static void ( *pf )( void ) = &func1;   /* Okay */  
       }  
  
    ```  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [DLL インポートおよびエクスポート関数](../Topic/DLL%20Import%20and%20Export%20Functions.md)