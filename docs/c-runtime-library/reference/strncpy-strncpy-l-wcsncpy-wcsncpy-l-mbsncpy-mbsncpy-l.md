---
title: strncpy、_strncpy_l、wcsncpy、_wcsncpy_l、_mbsncpy、_mbsncpy_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- strncpy
- _strncpy_l
- _mbsncpy
- wcsncpy
- _mbsncpy_l
- _wcsncpy_l
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
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _fstrncpy
- strncpy
- _ftcsncpy
- _tcsnccpy_l
- _tcsnccpy
- _mbsncpy
- wcsncpy
- _tcsncpy
- _strncpy_l
- _mbsncpy_l
- _wcsncpy_l
dev_langs:
- C++
helpviewer_keywords:
- wcsncpy_l function
- characters [C++], copying
- mbsncpy_l function
- strncpy_l function
- wcsncpy function
- tcsnccpy function
- ftcsncpy function
- copying characters of strings
- _wcsncpy_l function
- _tcsnccpy function
- _tcsnccpy_l function
- strncpy function
- _tcsncpy function
- mbsncpy function
- _fstrncpy function
- _mbsncpy_l function
- tcsncpy_l function
- tcsnccpy_l function
- fstrncpy function
- strings [C++], copying
- _ftcsncpy function
- _tcsncpy_l function
- _mbsncpy function
- tcsncpy function
- _strncpy_l function
ms.assetid: ac4345a1-a129-4f2f-bb8a-373ec58ab8b0
caps.latest.revision: 42
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 219fe2a9c163da1a7653568675b9c776ecad9d66
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="strncpy-strncpyl-wcsncpy-wcsncpyl-mbsncpy-mbsncpyl"></a>strncpy、_strncpy_l、wcsncpy、_wcsncpy_l、_mbsncpy、_mbsncpy_l

文字列の文字を別の文字列にコピーします。 これらの関数のセキュリティを強化したバージョンを使用できます。「[strncpy_s、_strncpy_s_l、wcsncpy_s、_wcsncpy_s_l、_mbsncpy_s、_mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)」をご覧ください。

> [!IMPORTANT]
> **_mbsncpy**と **_mbsncpy_l** Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
char *strncpy(
   char *strDest,
   const char *strSource,
   size_t count
);
char *_strncpy_l(
   char *strDest,
   const char *strSource,
   size_t count,
   locale_t locale
);
wchar_t *wcsncpy(
   wchar_t *strDest,
   const wchar_t *strSource,
   size_t count
);
wchar_t *_wcsncpy_l(
   wchar_t *strDest,
   const wchar_t *strSource,
   size_t count,
   locale_t locale
);
unsigned char *_mbsncpy(
   unsigned char *strDest,
   const unsigned char *strSource,
   size_t count
);
unsigned char *_mbsncpy_l(
   unsigned char *strDest,
   const unsigned char *strSource,
   size_t count,
   _locale_t locale
);
template <size_t size>
char *strncpy(
   char (&strDest)[size],
   const char *strSource,
   size_t count
); // C++ only
template <size_t size>
char *_strncpy_l(
   char (&strDest)[size],
   const char *strSource,
   size_t count,
   locale_t locale
); // C++ only
template <size_t size>
wchar_t *wcsncpy(
   wchar_t (&strDest)[size],
   const wchar_t *strSource,
   size_t count
); // C++ only
template <size_t size>
wchar_t *_wcsncpy_l(
   wchar_t (&strDest)[size],
   const wchar_t *strSource,
   size_t count,
   locale_t locale
); // C++ only
template <size_t size>
unsigned char *_mbsncpy(
   unsigned char (&strDest)[size],
   const unsigned char *strSource,
   size_t count
); // C++ only
template <size_t size>
unsigned char *_mbsncpy_l(
   unsigned char (&strDest)[size],
   const unsigned char *strSource,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>パラメーター

*strDest*<br/>
対象文字列。

*strSource*<br/>
ソース文字列。

*count*<br/>
コピーする文字数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

返します*追加される文字*です。 エラーを示す戻り値は予約されていません。

## <a name="remarks"></a>コメント

**Strncpy**関数は、初期コピー*カウント*の文字*strSource*に*追加される文字*し、返します*追加される文字*. 場合*カウント*がの長さ未満*strSource*、コピーされた文字列に null 文字が自動的に追加されません。 場合*カウント*がの長さより大きい*strSource*、コピー先文字列が長さまで null 文字が埋め込まれた*カウント*です。 動作**strncpy**元とコピー先文字列が重なり合っている場合に定義されていません。

> [!IMPORTANT]
> **strncpy**に十分な領域をチェックしません*追加される文字*です。 これにより、バッファー オーバーランの潜在的な原因です。 *カウント*引数がコピーされた文字の数を制限は、サイズの制限ではなく*追加される文字*です。 次の例を参照してください。 詳しくは、「 [バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。

場合*追加される文字*または*strSource*は、 **NULL**ポインター、または*カウント*と同じかそれよりも少ないには、0 は無効なパラメーター ハンドラーが呼び出される、」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、これらの関数は-1 を返します設定と**errno**に**EINVAL**です。

**wcsncpy**と **_mbsncpy**のワイド文字とマルチバイト文字バージョンは、 **strncpy**です。 引数と戻り値の**wcsncpy**と **_mbsncpy**がそれに応じて異なります。 それ以外では、これらの関数の動作は同じです。

これらの関数のバージョン、 **_l**そのロケールに依存する動作に現在のロケールの代わりに渡されたロケール パラメーターを使用する点を除いて、サフィックスは同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

C++ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsncpy**|**strncpy**|**_mbsnbcpy**|**wcsncpy**|
|**_tcsncpy_l**|**_strncpy_l**|**_mbsnbcpy_l**|**_wcsncpy_l**|

> [!NOTE]
> **_strncpy_l**と **_wcsncpy_l**ロケールの依存関係を持ちません。 だけで提供される **_tcsncpy_l**直接呼び出されるものではありません。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**strncpy**|\<string.h>|
|**wcsncpy**|\<string.h> または \<wchar.h>|
|**_mbsncpy**、 **_mbsncpy_l**|\<mbstring.h>|

プラットフォーム互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

次の例で使用する**strncpy**方法、悪用される可能性がプログラムのバグやセキュリティの問題が発生するとします。 呼び出しごとに、コンパイラで警告**strncpy**に似て**crt_strncpy_x86.c(15): C4996 が警告: 'strncpy': この関数または変数がセーフである可能性があります。代わりに strncpy_s の使用を検討してください。使用されなくなったことの警告を無効にするには、_CRT_SECURE_NO_WARNINGS を使用します。詳しくは、オンライン ヘルプをご覧ください。**

```C
// crt_strncpy_x86.c
// Use this command in an x86 developer command prompt to compile:
// cl /TC /W3 crt_strncpy_x86.c

#include <stdio.h>
#include <string.h>

int main() {
   char t[20];
   char s[20];
   char *p = 0, *q = 0;

   strcpy_s(s, sizeof(s), "AA BB CC");
   // Note: strncpy is deprecated; consider using strncpy_s instead
   strncpy(s, "aa", 2);     // "aa BB CC"         C4996
   strncpy(s + 3, "bb", 2); // "aa bb CC"         C4996
   strncpy(s, "ZZ", 3);     // "ZZ",              C4996
                            // count greater than strSource, null added
   printf("%s\n", s);

   strcpy_s(s, sizeof(s), "AA BB CC");
   p = strstr(s, "BB");
   q = strstr(s, "CC");
   strncpy(s, "aa", p - s - 1);   // "aa BB CC"   C4996
   strncpy(p, "bb", q - p - 1);   // "aa bb CC"   C4996
   strncpy(q, "cc",  q - s);      // "aa bb cc"   C4996
   strncpy(q, "dd", strlen(q));   // "aa bb dd"   C4996
   printf("%s\n", s);

   // some problems with strncpy
   strcpy_s(s, sizeof(s), "test");
   strncpy(t, "this is a very long string", 20 ); // C4996
   // Danger: at this point, t has no terminating null,
   // so the printf continues until it runs into one.
   // In this case, it will print "this is a very long test"
   printf("%s\n", t);

   strcpy_s(t, sizeof(t), "dogs like cats");
   printf("%s\n", t);

   strncpy(t + 10, "to chase cars.", 14); // C4996
   printf("%s\n", t);

   // strncpy has caused a buffer overrun and corrupted string s
   printf("Buffer overrun: s = '%s' (should be 'test')\n", s);
   // Since the stack grows from higher to lower addresses, buffer
   // overruns can corrupt function return addresses on the stack,
   // which can be exploited to run arbitrary code.
}
```

出力

```Output
ZZ
aa bb dd
this is a very long test
dogs like cats
dogs like to chase cars.
Buffer overrun: s = 'ars.' (should be 'test')
```

自動変数のレイアウトや、エラー検出とコード保護のレベルは、コンパイラの設定を変更すると変わることがあります。 この例は、他のコンパイル環境で、または他のコンパイラ オプションを指定してビルドすると、出力の結果が異なることがあります。

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbsnbcpy、_mbsnbcpy_l](mbsnbcpy-mbsnbcpy-l.md)<br/>
[strcat、wcscat、_mbscat](strcat-wcscat-mbscat.md)<br/>
[strcmp、wcscmp、_mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcpy、wcscpy、_mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[strncat、_strncat_l、wcsncat、_wcsncat_l、_mbsncat、_mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr、wcsrchr、_mbsrchr、_mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset、_strset_l、_wcsset、_wcsset_l、_mbsset、_mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn、wcsspn、_mbsspn、_mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
[strncpy_s、_strncpy_s_l、wcsncpy_s、_wcsncpy_s_l、_mbsncpy_s、_mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
[strcpy_s、wcscpy_s、_mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md)<br/>
