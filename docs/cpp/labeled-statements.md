---
title: "ラベル付きステートメント | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "goto"
  - "case"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "labeled ステートメント"
  - "ステートメント, labeled"
ms.assetid: 456a26d5-0fcc-4d1a-b71f-fa9ff3d73b91
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# ラベル付きステートメント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ラベルはプログラムの制御を特定のステートメントに直接移動するために使用されます。  
  
```  
identifier :  statement  
case constant-expression :  statement  
default :  statement  
```  
  
 ラベルのスコープはラベルが宣言されている関数全体です。  
  
## 解説  
 次の 3 種類のラベル付きステートメントがあります。  すべての種類で、そのタイプのラベルをステートメントと区切るためにコロンが使用されます。  case ラベルと default ラベルは、case ステートメントに固有です。  
  
```cpp  
#include <iostream>   
using namespace std;   
  
void test_label(int x) {  
  
    if (x == 1){  
        goto label1;  
    }  
    goto label2;  
  
label1:  
    cout << "in label1" << endl;  
    return;  
  
label2:  
    cout << "in label2" << endl;  
    return;  
}  
  
int main() {  
    test_label(1);  // in label1   
    test_label(2);  // in label2  
}  
  
```  
  
 **GoTo ステートメント**  
  
 ソース プログラム内の *identifier* ラベルは、ラベルを宣言します。  [identifier](../cpp/goto-statement-cpp.md) ラベルにコントロールを移動できるのは、*goto* ステートメントのみです。  次のコードでは `goto` ステートメントと *identifier* ラベルの使用方法を示します。  
  
 ラベルは単独では使用できず、常にステートメントと一緒に使用する必要があります。  ラベルのみが必要な場合は、ラベルの後に null ステートメントを置きます。  
  
 ラベルには関数スコープがあるため、同じ関数内で再宣言できません。  ただし、違う関数内に同じ名前をラベルとして使用することはできます。  
  
```  
// labels_with_goto.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   using namespace std;  
   goto Test2;  
  
   cout << "testing" << endl;  
  
   Test2:  
      cerr << "At Test2 label." << endl;  
}  
  
//Output: At Test2 label.  
```  
  
 **Case ステートメント**  
  
 **case** キーワードの後のラベルは、`switch` のステートメントの外側に表示することもできません   \(この制限は、**default** キーワードにも適用されます\)。 次のコード片では、**case** ラベルの正しい使用例を示します。  
  
```  
// Sample Microsoft Windows message processing loop.  
switch( msg )  
{  
   case WM_TIMER:    // Process timer event.  
      SetClassWord( hWnd, GCW_HICON, ahIcon[nIcon++] );  
      ShowWindow( hWnd, SW_SHOWNA );  
      nIcon %= 14;  
      Yield();  
      break;  
  
   case WM_PAINT:  
      memset( &ps, 0x00, sizeof(PAINTSTRUCT) );  
      hDC = BeginPaint( hWnd, &ps );   
      EndPaint( hWnd, &ps );  
      break;  
  
   default:  
      // This choice is taken for all messages not specifically  
      //  covered by a case statement.  
  
      return DefWindowProc( hWnd, Message, wParam, lParam );  
      break;  
}  
```  
  
## Case ステートメント内のラベル  
 **case** キーワードの後のラベルは、`switch` のステートメントの外側に表示することもできません   \(この制限は、**default** キーワードにも適用されます\)。 次のコード片では、**case** ラベルの正しい使用例を示します。  
  
```  
// Sample Microsoft Windows message processing loop.  
switch( msg )  
{  
   case WM_TIMER:    // Process timer event.  
      SetClassWord( hWnd, GCW_HICON, ahIcon[nIcon++] );  
      ShowWindow( hWnd, SW_SHOWNA );  
      nIcon %= 14;  
      Yield();  
      break;  
  
   case WM_PAINT:  
      // Obtain a handle to the device context.  
      // BeginPaint will send WM_ERASEBKGND if appropriate.  
  
      memset( &ps, 0x00, sizeof(PAINTSTRUCT) );  
      hDC = BeginPaint( hWnd, &ps );  
  
      // Inform Windows that painting is complete.  
  
      EndPaint( hWnd, &ps );  
      break;  
  
   case WM_CLOSE:  
      // Close this window and all child windows.  
  
      KillTimer( hWnd, TIMER1 );  
      DestroyWindow( hWnd );  
      if ( hWnd == hWndMain )  
         PostQuitMessage( 0 );  // Quit the application.  
      break;  
  
   default:  
      // This choice is taken for all messages not specifically  
      //  covered by a case statement.  
  
      return DefWindowProc( hWnd, Message, wParam, lParam );  
      break;  
}  
```  
  
## GoTo ステートメント内のラベル  
 ソース プログラム内の *identifier* ラベルは、ラベルを宣言します。  [identifier](../cpp/goto-statement-cpp.md) ラベルにコントロールを移動できるのは、*goto* ステートメントのみです。  次のコードでは `goto` ステートメントと *identifier* ラベルの使用方法を示します。  
  
 ラベルは単独では使用できず、常にステートメントと一緒に使用する必要があります。  ラベルのみが必要な場合は、ラベルの後に null ステートメントを置きます。  
  
 ラベルには関数スコープがあるため、同じ関数内で再宣言できません。  ただし、違う関数内に同じ名前をラベルとして使用することはできます。  
  
```  
// labels_with_goto.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   using namespace std;  
   goto Test2;  
  
   cout << "testing" << endl;  
  
   Test2:  
      cerr << "At Test2 label." << endl;  
// At Test2 label.  
}  
  
```  
  
## 参照  
 [C\+\+ ステートメントの概要](../cpp/overview-of-cpp-statements.md)   
 [switch ステートメント \(C\+\+\)](../cpp/switch-statement-cpp.md)