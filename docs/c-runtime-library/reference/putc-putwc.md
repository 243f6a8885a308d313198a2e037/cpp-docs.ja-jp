---
title: putc、putwc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- putwc
- putc
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _puttc
- putwc
- putc
dev_langs:
- C++
helpviewer_keywords:
- streams, writing characters to
- characters, writing
- putwc function
- putc function
- _puttc function
- puttc function
ms.assetid: a37b2e82-9d88-4565-8190-ff8d04c0ddb9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 931a1a586f46327dd800ca5e1b2ef9a0b22f469d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="putc-putwc"></a>putc、putwc

ストリームに文字を書き込みます。

## <a name="syntax"></a>構文

```C
int putc(
   int c,
   FILE *stream
);
wint_t putwc(
   wchar_t c,
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*c*<br/>
書き込む文字。

*ストリーム*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

書き込まれた文字を返します。 エラーまたはファイルの終端状態を示すために**putc**と**putchar**返します * * EOF`; **putwc`と**putwchar**返す**WEOF**です。 4 つすべてのルーチンで、[ferror](ferror.md) または [feof](feof.md) を使用して、エラーまたはファイルの終端を確認します。 Null ポインターを渡された場合*ストリーム*で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 これらの関数を返すかどうかは、引き続き実行が許可された、 **EOF**または**WEOF**設定と**errno**に**EINVAL**です。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>コメント

**Putc**ルーチンは、単一の文字を書き込みます*c*出力に*ストリーム*現在位置にあります。 任意の整数に渡すことが**putc**が下位の 8 ビットのみに書き込まれます。 **Putchar**ルーチンと同じ**putc (** * c ***、stdout)** です。 各ルーチンでは、読み取りエラーが発生すると、ストリームのエラー インジケーターが設定されます。 **putc**と**putchar**のような**fputc**と **_fputchar**、それぞれ、関数およびマクロとして実装されますが、(を参照してください[関数とマクロの使い分け](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md))。 **putwc**と**putwchar**のワイド文字バージョンは、 **putc**と**putchar**、それぞれします。 **putwc**と**putc**ストリームが ANSI モードで開かれている場合の動作は同じです。 **putc** UNICODE ストリームへの出力はサポートされていません。

**_nolock** サフィックスが付いているバージョンは同じものですが、他のスレッドによる干渉から保護されない点が異なります。 詳細については、「**_putc_nolock、_putwc_nolock**」をご覧ください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_puttc**|**putc**|**putc**|**putwc**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**putc**|\<stdio.h>|
|**putwc**|\<stdio.h> または \<wchar.h>|

コンソールは、ユニバーサル Windows プラットフォーム (UWP) アプリではサポートされていません。 コンソールに関連付けられている標準ストリームのハンドル**stdin**、 **stdout**、および**stderr**、C ランタイム関数が UWP アプリで使用する前にリダイレクトする必要があります. 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

```C
// crt_putc.c
/* This program uses putc to write buffer
* to a stream. If an error occurs, the program
* stops before writing the entire buffer.
*/

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char *p, buffer[] = "This is the line of output\n";
   int  ch;

   ch = 0;
   /* Make standard out the stream and write to it. */
   stream = stdout;
   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )
      ch = putc( *p, stream );
}
```

### <a name="output"></a>出力

```Output
This is the line of output
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fputc、fputwc](fputc-fputwc.md)<br/>
[getc、getwc](getc-getwc.md)<br/>
