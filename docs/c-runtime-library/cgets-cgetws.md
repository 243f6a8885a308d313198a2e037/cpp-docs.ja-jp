---
title: "_cgets、_cgetws | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_cgetws"
  - "_cgets"
apilocation: 
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcrt.dll"
  - "msvcr110_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "cgetws"
  - "_cgetws"
  - "_cgets"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_cgets 関数"
  - "_cgetws 関数"
  - "cgets 関数"
  - "cgetws 関数"
  - "コンソール, 取得 (文字列を)"
  - "文字列 [C++], 取得 (コンソールから)"
ms.assetid: 4d5e134a-58c3-4f62-befd-5d235b0212f4
caps.latest.revision: 32
caps.handback.revision: 32
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _cgets、_cgetws
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コンソールから文字列を取得します。 これらの関数のセキュリティを強化したバージョンを使用できます。「[\_cgets\_s、\_cgetws\_s](../Topic/_cgets_s,%20_cgetws_s.md)」を参照してください。  
  
> [!IMPORTANT]
>  これらは古い関数です。 Visual Studio 2015 以降、これらは CRT で使用できません。 これらの関数のセキュリティを強化したバージョン \_cgets\_s および \_cgetws\_s は、引き続き使用できます。 これらの代替関数の詳細については、「[\_cgets\_s、\_cgetws\_s](../Topic/_cgets_s,%20_cgetws_s.md)」を参照してください。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
char *_cgets(   
   char *buffer   
);  
wchar_t *_cgetws(  
   wchar_t *buffer  
);  
template <size_t size>  
char *_cgets(   
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_cgetws(  
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### パラメーター  
 `buffer`  
 データの格納場所。  
  
## 戻り値  
 `_cgets` と `_cgetws` は文字列の先頭である `buffer[2]` へのポインターを返します。`buffer` が `NULL` の場合は、「[パラメーターの検証](../c-runtime-library/parameter-validation.md)」に説明されているように、これらの関数は無効パラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、これらは `NULL` を返し、`errno` を `EINVAL` に設定します。  
  
## 解説  
 これらの関数は、コンソールから文字列を読み込み、`buffer` が指す位置に文字列とその長さを格納します。`buffer` パラメーターは文字配列へのポインターである必要があります。 配列の最初の要素 \(`buffer[0]`\) には、読み取る文字列の最大長 \(文字数\) を格納します。 配列は、文字列、終端の null 文字 \('\\0'\)、およびその他の 2 バイト分を格納するのに十分な要素を持つ必要があります。 関数は、文字をキャリッジ リターンとライン フィード \(CR\-LF\) の組み合わせが現れるか、指定した文字数を読み取るまで文字を読み取ります。 文字列は `buffer[2]` を先頭として格納されます。 関数が CR\-LF を読み取ると、null 文字 \('\\0'\) を格納します。 次に、関数は 2 番目の配列要素である `buffer[1]` に文字列の実際の長さを格納します。  
  
 コンソール ウィンドウでは、`_cgets` または`_cgetws` が呼び出されたときにはすべての編集キーがアクティブになっているため、F3 キーを押すと最後に入力したエントリが繰り返されます。  
  
 C\+\+ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_cgetts`|`_cgets`|`_cgets`|`_cgetws`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_cgets`|\<conio.h\>|  
|`_cgetws`|\<conio.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「[互換性](../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_cgets.c // compile with: /c /W3 // This program creates a buffer and initializes // the first byte to the size of the buffer. Next, the // program accepts an input string using _cgets and displays // the size and text of that string. #include <conio.h> #include <stdio.h> #include <errno.h> int main( void ) { char buffer[83] = { 80 };  // Maximum characters in 1st byte char *result; printf( "Input line of text, followed by carriage return:\n"); // Input a line of text: result = _cgets( buffer ); // C4996 // Note: _cgets is deprecated; consider using _cgets_s if (!result) { printf( "An error occurred reading from the console:" " error code %d\n", errno); } else { printf( "\nLine length = %d\nText = %s\n", buffer[1], result ); } }  
```  
  
```Output  
  
A line of input.Input line of text, followed by carriage return: Line Length = 16 Text = A line of input.  
```  
  
## 参照  
 [コンソール入出力とポート入出力](../c-runtime-library/console-and-port-i-o.md)   
 [\_getch、\_getwch](../Topic/_getch,%20_getwch.md)