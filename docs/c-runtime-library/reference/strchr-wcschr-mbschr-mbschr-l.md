---
title: "strchr、wcschr、_mbschr、_mbschr_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- strchr
- wcschr
- _mbschr_l
- _mbschr
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ntdll.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ftcschr
- strchr
- wcschr
- _tcschr
- _mbschr
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], searching
- mbschr function
- _ftcschr function
- _mbschr function
- characters [C++], finding in strings
- _mbschr_l function
- ftcschr function
- wcschr function
- strchr function
- _tcschr function
- tcschr function
- mbschr_l function
ms.assetid: 2639905d-e983-43b7-b885-abef32cfac43
caps.latest.revision: 31
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 471339844a38aed1f84e13649e49714c45ec8178
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="strchr-wcschr-mbschr-mbschrl"></a>strchr、wcschr、_mbschr、_mbschr_l
現在のロケールまたは指定された LC_CTYPE 変換状態カテゴリを使用し、文字列内の文字を探します。  
  
> [!IMPORTANT]
>  `_mbschr` および `_mbschr_l` は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
char *strchr(  
   const char *str,  
   int c   
);  // C only  
char *strchr(  
   char * str,  
   int c   
); // C++ only  
const char *strchr(  
   const char * str,  
   int c   
); // C++ only  
wchar_t *wcschr(  
   const wchar_t *str,  
   wchar_t c   
); // C only  
wchar_t *wcschr(  
   wchar_t *str,  
   wchar_t c   
);  // C++ only  
const wchar_t *wcschr(  
   const wchar_t *str,  
   wchar_t c   
);  // C++ only  
unsigned char *_mbschr(  
   const unsigned char *str,  
   unsigned int c   
); // C only  
unsigned char *_mbschr(  
   unsigned char *str,  
   unsigned int c   
); // C++ only  
const unsigned char *_mbschr(  
   const unsigned char *str,  
   unsigned int c   
); // C++ only  
unsigned char *_mbschr_l(  
   const unsigned char *str,  
   unsigned int c,  
   _locale_t locale  
); // C only   
unsigned char *_mbschr_l(  
   unsigned char *str,  
   unsigned int c,  
   _locale_t locale  
); // C++ only  
const unsigned char *_mbschr_l(  
   const unsigned char *str,  
   unsigned int c,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  
 `str`  
 NULL で終わる元の文字列。  
  
 `c`  
 検索する文字。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 これらの関数は、`c` 内で `str` が最初に出現する位置を指すポインターを返します。`NULL` が見つからない場合は、`c` を返します。  
  
## <a name="remarks"></a>コメント  
 `strchr` 関数は、`c` 内で `str` が最初に出現する位置を検索し、`NULL` が見つからない場合は `c` を返します。 検索対象には終端の null 文字が含まれます。  
  
 `wcschr` 関数、`_mbschr` 関数、および `_mbschr_l` 関数は、`strchr` 関数のワイド文字バージョンとマルチバイト文字バージョンです。 `wcschr` 関数の引数と戻り値はワイド文字列で、`_mbschr` 関数の引数と戻り値はマルチバイト文字列です。 `_mbschr` はマルチバイト文字シーケンスを認識します。 また、文字列が null ポインターの場合、`_mbschr` は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、`_mbschr` は `NULL` を返し、`errno` を `EINVAL` に設定します。 `strchr` および `wcschr` は、パラメーターを検証しません。 それ以外では、これらの関数の動作は同じです。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定に影響されます。詳細については、「[setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)」を参照してください。 `_l` サフィックスが付いていないこれらの関数のバージョンでは、このロケールに依存する動作に現在のロケールを使用します。`_l` サフィックスが付いているバージョンは、渡されたロケール パラメーターを代わりに使用する点を除いて同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 C では、これらの関数は、最初の引数に `const` ポインターを受け取ります。 C++ では、2 つのオーバーロードを使用できます。 `const` へのポインターを受け取るオーバーロードでは、`const` へのポインターが返されます。非 `const` へのポインターを受け取るバージョンでは、非 `const` へのポインターが返されます。 この関数の `const` と非 `const` の両方のバージョンが使用できる場合、_CONST_CORRECT_OVERLOADS というマクロが定義されます。 C++ のいずれのオーバーロードでも、非 `const` の動作が求められる場合は、シンボル _CONST_RETURN を定義してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcschr`|`strchr`|`_mbschr`|`wcschr`|  
|**_n/a**|**n/a**|`_mbschr_l`|**該当なし**|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`strchr`|\<string.h>|  
|`wcschr`|\<string.h> または \<wchar.h>|  
|`_mbschr`, `_mbschr_l`|\<mbstring.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_strchr.c  
//   
// This program illustrates searching for a character  
// with strchr (search forward) or strrchr (search backward).  
//  
  
#include <string.h>  
#include <stdio.h>  
  
int  ch = 'r';  
  
char string[] = "The quick brown dog jumps over the lazy fox";  
char fmt1[] =   "         1         2         3         4         5";  
char fmt2[] =   "12345678901234567890123456789012345678901234567890";  
  
int main( void )  
{  
   char *pdest;  
   int result;  
  
   printf_s( "String to be searched:\n      %s\n", string );  
   printf_s( "      %s\n      %s\n\n", fmt1, fmt2 );  
   printf_s( "Search char:   %c\n", ch );  
  
   // Search forward.   
   pdest = strchr( string, ch );  
   result = (int)(pdest - string + 1);  
   if ( pdest != NULL )  
      printf_s( "Result:   first %c found at position %d\n",   
              ch, result );  
   else  
      printf_s( "Result:   %c not found\n", ch );  
  
   // Search backward.   
   pdest = strrchr( string, ch );  
   result = (int)(pdest - string + 1);  
   if ( pdest != NULL )  
      printf_s( "Result:   last %c found at position %d\n", ch, result );  
   else  
      printf_s( "Result:\t%c not found\n", ch );  
}  
```  
  
```Output  
String to be searched:  
      The quick brown dog jumps over the lazy fox  
               1         2         3         4         5  
      12345678901234567890123456789012345678901234567890  
  
Search char:   r  
Result:   first r found at position 12  
Result:   last r found at position 30  
```  
  
## <a name="see-also"></a>関連項目  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [strcspn、wcscspn、_mbscspn、_mbscspn_l](../../c-runtime-library/reference/strcspn-wcscspn-mbscspn-mbscspn-l.md)   
 [strncat、_strncat_l、wcsncat、_wcsncat_l、_mbsncat、_mbsncat_l](../../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)   
 [strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [strncpy、_strncpy_l、wcsncpy、_wcsncpy_l、_mbsncpy、_mbsncpy_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strpbrk、wcspbrk、_mbspbrk、_mbspbrk_l](../../c-runtime-library/reference/strpbrk-wcspbrk-mbspbrk-mbspbrk-l.md)   
 [strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [strstr、wcsstr、_mbsstr、_mbsstr_l](../../c-runtime-library/reference/strstr-wcsstr-mbsstr-mbsstr-l.md)