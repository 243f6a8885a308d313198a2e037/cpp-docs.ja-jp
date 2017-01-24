---
title: "is、isw 系ルーチン | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "isw"
  - "is"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "is ルーチン"
  - "isw ルーチン"
ms.assetid: 1e171a57-2cde-41f6-a75f-a080fa3c12e5
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is、isw 系ルーチン
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

|||  
|-|-|  
|[isalnum、iswalnum、\_isalnum\_l、\_iswalnum\_l](../Topic/isalnum,%20iswalnum,%20_isalnum_l,%20_iswalnum_l.md)|[isgraph、iswgraph、\_isgraph\_l、\_iswgraph\_l](../Topic/isgraph,%20iswgraph,%20_isgraph_l,%20_iswgraph_l.md)|  
|[isalpha、iswalpha、\_isalpha\_l、\_iswalpha\_l](../Topic/isalpha,%20iswalpha,%20_isalpha_l,%20_iswalpha_l.md)|[isleadbyte、\_isleadbyte\_l](../c-runtime-library/reference/isleadbyte-isleadbyte-l.md)|  
|[isascii、\_ \_isascii、iswascii](../c-runtime-library/reference/isascii-isascii-iswascii.md)|[islower、iswlower、\_islower\_l、\_iswlower\_l](../Topic/islower,%20iswlower,%20_islower_l,%20_iswlower_l.md)|  
|[isblank、iswblank、\_isblank\_l、\_iswblank\_l](../c-runtime-library/reference/isblank-iswblank-isblank-l-iswblank-l.md)|[isprint、iswprint、\_isprint\_l、\_iswprint\_l](../c-runtime-library/reference/isprint-iswprint-isprint-l-iswprint-l.md)|  
|[iscntrl、iswcntrl、\_iscntrl\_l、\_iswcntrl\_l](../c-runtime-library/reference/iscntrl-iswcntrl-iscntrl-l-iswcntrl-l.md)|[ispunct、iswpunct、\_ispunct\_l、\_iswpunct\_l](../c-runtime-library/reference/ispunct-iswpunct-ispunct-l-iswpunct-l.md)|  
|[iscsym、iscsymf、\_ \_iscsym、\_ \_iswcsym、\_ \_iscsymf、\_ \_iswcsymf、\_iscsym\_l、\_iswcsym\_l、\_iscsymf\_l、\_iswcsymf\_l](../c-runtime-library/reference/iscsym-functions.md)|[isspace、iswspace、\_isspace\_l、\_iswspace\_l](../c-runtime-library/reference/isspace-iswspace-isspace-l-iswspace-l.md)|  
|[\_isctype、iswctype、\_isctype\_l、\_iswctype\_l](../Topic/_isctype,%20iswctype,%20_isctype_l,%20_iswctype_l.md)|[isupper、\_isupper\_l、iswupper、\_iswupper\_l](../Topic/isupper,%20_isupper_l,%20iswupper,%20_iswupper_l.md)|  
|[isdigit、iswdigit、\_isdigit\_l、\_iswdigit\_l](../c-runtime-library/reference/isdigit-iswdigit-isdigit-l-iswdigit-l.md)|[isxdigit、iswxdigit、\_isxdigit\_l、\_iswxdigit\_l](../c-runtime-library/reference/isxdigit-iswxdigit-isxdigit-l-iswxdigit-l.md)|  
  
## 解説  
 これらのルーチンは、文字が指定条件を満たしているかどうかをテストします。  
  
 **is** ルーチンは、–1 \(`EOF`\) から **UCHAR\_MAX** \(0xFF\) までの任意の整数の引数に対して意味のある結果を生成します。  `int` 型の引数が必要です。  
  
> [!CAUTION]
>  **is** ルーチンで `char` 型の引数を渡すと、予測できない結果が発生する可能性があります。  0x7F よりも大きい値を持つ `char` 型の SBCS または MBCS の 1 バイト文字は負になります。  `char` が渡されると、コンパイラはその値を符号付き `int` または符号付き **long** に変換することがあります。  この値は、コンパイラによって符号拡張されることがあり、予想外の結果になることがあります。  
  
 **isw** ルーチンは、\-1 \(**WEOF**\) から 0xFFFF までの任意の整数値に対して意味のある結果を生成します。  **wint\_t** データ型は、WCHAR.H で **unsigned short** として定義されており、任意のワイド文字またはワイド文字のファイル終端 \(**WEOF**\) 値を保持できます。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定で決まります。詳細については、「[setlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  **\_l** サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。**\_l** サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。  
  
 "C" ロケールでは、**is** ルーチンのテスト条件は次のようになります。  
  
 `isalnum`  
 英数字 \(A ～ Z、a ～ z、または 0 ～ 9\)。  
  
 `isalpha`  
 英字 \(A ～ Z または a ～ z\)。  
  
 `__isascii`  
 ASCII 文字 \(0x00 ～ 0x7F\)。  
  
 `isblank`  
 水平タブまたは空白文字 \(0x09 または 0x20\)。  
  
 `iscntrl`  
 制御文字 \(0x00 ～ 0x1F または 0x7F\)。  
  
 `__iscsym`  
 文字、アンダースコア、または数字。  
  
 `__iscsymf`  
 文字またはアンダースコア。  
  
 **isdigit**  
 10 進数 \(0 ～ 9\)。  
  
 `isgraph`  
 空白 \( \) を除く印刷できる文字。  
  
 `islower`  
 小文字 \(a ～ z\)。  
  
 `isprint`  
 空白を含む印刷できる文字 \(0x20 ～ 0x7E\)。  
  
 `ispunct`  
 区切り記号。  
  
 `isspace`  
 空白文字 \(0x09 ～ 0x0D または 0x20\)。  
  
 `isupper`  
 大文字 \(A ～ Z\)。  
  
 `isxdigit`  
 16 進数字 \(A ～ F、a ～ f、または 0 ～ 9\)。  
  
 **isw** ルーチンでは、指定条件に基づくテストの結果は、ロケールに依存しません。  **isw** 関数のテスト条件は次のとおりです。  
  
 `iswalnum`  
 `iswalpha` または `iswdigit`。  
  
 `iswalpha`  
 `iswcntrl`、`iswdigit`、`iswpunct`、または `iswspace` がいずれも 0 になる実装定義セットに含まれる任意のワイド文字。  `iswalpha` は、`iswupper` または `iswlower` が 0 以外の値になるワイド文字に対してのみ、0 以外の値を返します。  
  
 `iswascii`  
 ASCII 文字のワイド文字表現 \(0x0000 ～ 0x007F\)。  
  
 `iswblank`  
 標準の空白文字に対応するワイド文字、または `iswalnum` が false になるワイド文字の実装定義セットに含まれるワイド文字。  標準の空白文字は空白 \(L' '\) と水平タブ \(L'\\t'\) です。  
  
 `iswcntrl`  
 制御ワイド文字。  
  
 **\_\_iswcsym**  
 **isalnum** が true になる任意のワイド文字または '\_' 文字。  
  
 **\_\_iswcsymf**  
 `iswalpha` が true である任意のワイド文字または '\_' 文字。  
  
 `iswctype`  
 文字には、`desc` 引数で指定されたプロパティがあります。  `iswctype` の `desc` 引数の有効な値には、次の表に示すようにそれぞれ同等のワイド文字分類ルーチンがあります。  
  
 **iswctype\(**   
 ***c, desc* \) と同等のその他の isw テスト ルーチン**  
  
|*desc* 引数の値|iswctype\( *c, desc* \) と同等のルーチン|  
|-----------------|--------------------------------------|  
|**\_ALPHA**|**iswalpha\(** `c` **\)**|  
|**\_ALPHA** &#124; **\_DIGIT**|**iswalnum\(** `c` **\)**|  
|**\_BLANK**|**iswblank\(** `c` **\)**|  
|**\_CONTROL**|**iswcntrl\(** `c` **\)**|  
|**\_DIGIT**|**iswdigit\(** `c` **\)**|  
|**\_ALPHA** &#124; **\_DIGIT** &#124; **\_PUNCT**|**iswgraph\(** `c` **\)**|  
|**\_LOWER**|**iswlower\(** `c` **\)**|  
|**\_ALPHA** &#124; **\_BLANK** &#124; **\_DIGIT** &#124; **\_PUNCT**|**iswprint\(** `c` **\)**|  
|**\_PUNCT**|**iswpunct\(** `c` **\)**|  
|**\_BLANK**|**iswblank\(** `c` **\)**|  
|**\_SPACE**|**iswspace\(** `c` **\)**|  
|**\_UPPER**|**iswupper\(** `c` **\)**|  
|**\_HEX**|**iswxdigit\(** `c` **\)**|  
  
 `iswdigit`  
 10 進数字に対応するワイド文字。  
  
 `iswgraph`  
 空白ワイド文字 \(L' '\) を除く印刷できるワイド文字。  
  
 `iswlower`  
 小文字、または `iswcntrl`、`iswdigit`、`iswpunct`、`iswspace` がいずれも 0 になるワイド文字の実装定義セットに含まれる文字。  `iswlower` は、小文字に対応するワイド文字に対してのみ、0 以外の値を返します。  
  
 `iswprint`  
 空白ワイド文字 \(L' '\) を含む印刷できるワイド文字。  
  
 `iswpunct`  
 空白ワイド文字 \(L' '\) および `iswalnum` が 0 以外になるワイド文字を除く、印刷できるワイド文字。  
  
 `iswspace`  
 標準の空白文字に対応するワイド文字、または `iswalnum` が false になるワイド文字の実装定義セットに含まれるワイド文字。  標準の空白文字は、空白 \(L' '\)、フォーム フィード \(L'\\f'\)、改行 \(L'\\n'\)、復帰 \(L'\\r'\)、水平タブ \(L'\\t'\)、および垂直タブ \(L'\\v'\) です。  
  
 `iswupper`  
 大文字のワイド文字、または `iswcntrl`、`iswdigit`、`iswpunct`、または `iswspace` がいずれも 0 になるワイド文字の実装定義セットに含まれるワイド文字。  `iswupper` は、大文字に対応するワイド文字に対してのみ、0 以外の値を返します。  
  
 `iswxdigit`  
 16 進数字に対応するワイド文字。  
  
## 使用例  
  
```  
// crt_isfam.c  
/* This program tests all characters between 0x0  
 * and 0x7F, then displays each character with abbreviations  
 * for the character-type codes that apply.  
 */  
  
#include <stdio.h>  
#include <ctype.h>  
  
int main( void )  
{  
   int ch;  
   for( ch = 0; ch <= 0x7F; ch++ )  
   {  
      printf( "%.2x  ", ch );  
      printf( " %c", isprint( ch )  ? ch   : ' ' );  
      printf( "%4s", isalnum( ch )  ? "AN" : "" );  
      printf( "%3s", isalpha( ch )  ? "A"  : "" );  
      printf( "%3s", __isascii( ch )  ? "AS" : "" );  
      printf( "%3s", iscntrl( ch )  ? "C"  : "" );  
      printf( "%3s", __iscsym( ch )  ? "CS "  : "" );  
      printf( "%3s", __iscsymf( ch )  ? "CSF"  : "" );  
      printf( "%3s", isdigit( ch )  ? "D"  : "" );  
      printf( "%3s", isgraph( ch )  ? "G"  : "" );  
      printf( "%3s", islower( ch )  ? "L"  : "" );  
      printf( "%3s", ispunct( ch )  ? "PU" : "" );  
      printf( "%3s", isspace( ch )  ? "S"  : "" );  
      printf( "%3s", isprint( ch )  ? "PR" : "" );  
      printf( "%3s", isupper( ch )  ? "U"  : "" );  
      printf( "%3s", isxdigit( ch ) ? "X"  : "" );  
      printf( ".\n" );  
   }  
}  
```  
  
## 出力  
  
```  
00            AS  C                              .  
01            AS  C                              .  
02            AS  C                              .  
03            AS  C                              .  
04            AS  C                              .  
05            AS  C                              .  
06            AS  C                              .  
07            AS  C                              .  
08            AS  C                              .  
09            AS  C                    S         .  
0a            AS  C                    S         .  
0b            AS  C                    S         .  
0c            AS  C                    S         .  
0d            AS  C                    S         .  
0e            AS  C                              .  
0f            AS  C                              .  
10            AS  C                              .  
11            AS  C                              .  
12            AS  C                              .  
13            AS  C                              .  
14            AS  C                              .  
15            AS  C                              .  
16            AS  C                              .  
17            AS  C                              .  
18            AS  C                              .  
19            AS  C                              .  
1a            AS  C                              .  
1b            AS  C                              .  
1c            AS  C                              .  
1d            AS  C                              .  
1e            AS  C                              .  
1f            AS  C                              .  
20            AS                       S PR      .  
21   !        AS              G    PU    PR      .  
22   "        AS              G    PU    PR      .  
23   #        AS              G    PU    PR      .  
24   $        AS              G    PU    PR      .  
25   %        AS              G    PU    PR      .  
26   &        AS              G    PU    PR      .  
27   '        AS              G    PU    PR      .  
28   (        AS              G    PU    PR      .  
29   )        AS              G    PU    PR      .  
2a   *        AS              G    PU    PR      .  
2b   +        AS              G    PU    PR      .  
2c   ,        AS              G    PU    PR      .  
2d   -        AS              G    PU    PR      .  
2e   .        AS              G    PU    PR      .  
2f   /        AS              G    PU    PR      .  
30   0  AN    AS   CS      D  G          PR     X.  
31   1  AN    AS   CS      D  G          PR     X.  
32   2  AN    AS   CS      D  G          PR     X.  
33   3  AN    AS   CS      D  G          PR     X.  
34   4  AN    AS   CS      D  G          PR     X.  
35   5  AN    AS   CS      D  G          PR     X.  
36   6  AN    AS   CS      D  G          PR     X.  
37   7  AN    AS   CS      D  G          PR     X.  
38   8  AN    AS   CS      D  G          PR     X.  
39   9  AN    AS   CS      D  G          PR     X.  
3a   :        AS              G    PU    PR      .  
3b   ;        AS              G    PU    PR      .  
3c   <        AS              G    PU    PR      .  
3d   =        AS              G    PU    PR      .  
3e   >        AS              G    PU    PR      .  
3f   ?        AS              G    PU    PR      .  
40   @        AS              G    PU    PR      .  
41   A  AN  A AS   CS CSF     G          PR  U  X.  
42   B  AN  A AS   CS CSF     G          PR  U  X.  
43   C  AN  A AS   CS CSF     G          PR  U  X.  
44   D  AN  A AS   CS CSF     G          PR  U  X.  
45   E  AN  A AS   CS CSF     G          PR  U  X.  
46   F  AN  A AS   CS CSF     G          PR  U  X.  
47   G  AN  A AS   CS CSF     G          PR  U   .  
48   H  AN  A AS   CS CSF     G          PR  U   .  
49   I  AN  A AS   CS CSF     G          PR  U   .  
4a   J  AN  A AS   CS CSF     G          PR  U   .  
4b   K  AN  A AS   CS CSF     G          PR  U   .  
4c   L  AN  A AS   CS CSF     G          PR  U   .  
4d   M  AN  A AS   CS CSF     G          PR  U   .  
4e   N  AN  A AS   CS CSF     G          PR  U   .  
4f   O  AN  A AS   CS CSF     G          PR  U   .  
50   P  AN  A AS   CS CSF     G          PR  U   .  
51   Q  AN  A AS   CS CSF     G          PR  U   .  
52   R  AN  A AS   CS CSF     G          PR  U   .  
53   S  AN  A AS   CS CSF     G          PR  U   .  
54   T  AN  A AS   CS CSF     G          PR  U   .  
55   U  AN  A AS   CS CSF     G          PR  U   .  
56   V  AN  A AS   CS CSF     G          PR  U   .  
57   W  AN  A AS   CS CSF     G          PR  U   .  
58   X  AN  A AS   CS CSF     G          PR  U   .  
59   Y  AN  A AS   CS CSF     G          PR  U   .  
5a   Z  AN  A AS   CS CSF     G          PR  U   .  
5b   [        AS              G    PU    PR      .  
5c   \        AS              G    PU    PR      .  
5d   ]        AS              G    PU    PR      .  
5e   ^        AS              G    PU    PR      .  
5f   _        AS   CS CSF     G    PU    PR      .  
60   `        AS              G    PU    PR      .  
61   a  AN  A AS   CS CSF     G  L       PR     X.  
62   b  AN  A AS   CS CSF     G  L       PR     X.  
63   c  AN  A AS   CS CSF     G  L       PR     X.  
64   d  AN  A AS   CS CSF     G  L       PR     X.  
65   e  AN  A AS   CS CSF     G  L       PR     X.  
66   f  AN  A AS   CS CSF     G  L       PR     X.  
67   g  AN  A AS   CS CSF     G  L       PR      .  
68   h  AN  A AS   CS CSF     G  L       PR      .  
69   i  AN  A AS   CS CSF     G  L       PR      .  
6a   j  AN  A AS   CS CSF     G  L       PR      .  
6b   k  AN  A AS   CS CSF     G  L       PR      .  
6c   l  AN  A AS   CS CSF     G  L       PR      .  
6d   m  AN  A AS   CS CSF     G  L       PR      .  
6e   n  AN  A AS   CS CSF     G  L       PR      .  
6f   o  AN  A AS   CS CSF     G  L       PR      .  
70   p  AN  A AS   CS CSF     G  L       PR      .  
71   q  AN  A AS   CS CSF     G  L       PR      .  
72   r  AN  A AS   CS CSF     G  L       PR      .  
73   s  AN  A AS   CS CSF     G  L       PR      .  
74   t  AN  A AS   CS CSF     G  L       PR      .  
75   u  AN  A AS   CS CSF     G  L       PR      .  
76   v  AN  A AS   CS CSF     G  L       PR      .  
77   w  AN  A AS   CS CSF     G  L       PR      .  
78   x  AN  A AS   CS CSF     G  L       PR      .  
79   y  AN  A AS   CS CSF     G  L       PR      .  
7a   z  AN  A AS   CS CSF     G  L       PR      .  
7b   {        AS              G    PU    PR      .  
7c   |        AS              G    PU    PR      .  
7d   }        AS              G    PU    PR      .  
7e   ~        AS              G    PU    PR      .  
7f            AS  C                              .  
```  
  
## 参照  
 [文字分類](../c-runtime-library/character-classification.md)   
 [ロケール](../c-runtime-library/locale.md)   
 [setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [マルチバイト文字のシーケンスの解釈](../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [to 系関数](../c-runtime-library/to-functions.md)