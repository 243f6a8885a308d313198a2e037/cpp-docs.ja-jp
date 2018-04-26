---
title: asctime_s、_wasctime_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _wasctime_s
- asctime_s
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- asctime_s
- _wasctime_s
- _tasctime_s
dev_langs:
- C++
helpviewer_keywords:
- tasctime_s function
- _tasctime_s function
- time structure conversion
- wasctime_s function
- time, converting
- _wasctime_s function
- asctime_s function
ms.assetid: 17ad9b2b-a459-465d-976a-42822897688a
caps.latest.revision: 29
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a5a60bf3bae862be3b8fad98f4fa1346957b6590
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="asctimes-wasctimes"></a>asctime_s、_wasctime_s

変換、 **tm**時刻の文字列に構造体。 これらの関数は、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、[asctime、_wasctime](asctime-wasctime.md) のセキュリティが強化されたバージョンです。

## <a name="syntax"></a>構文

```C
errno_t asctime_s(
   char* buffer,
   size_t numberOfElements,
   const struct tm *tmSource
);
errno_t _wasctime_s(
   wchar_t* buffer,
   size_t numberOfElements
   const struct tm *tmSource
);
template <size_t size>
errno_t asctime_s(
   char (&buffer)[size],
   const struct tm *tmSource
); // C++ only
template <size_t size>
errno_t _wasctime_s(
   wchar_t (&buffer)[size],
   const struct tm *tmSource
); // C++ only
```

### <a name="parameters"></a>パラメーター

*バッファー*<br/>
結果の文字列を格納するバッファーへのポインター。 この関数で指定されたサイズに有効なメモリ位置へのポインターを前提としています*numberOfElements*です。

*numberOfElements*<br/>
結果を格納するために使用するバッファーのサイズ。

*tmSource*<br/>
時刻/日付の構造体。 この関数には、有効なへのポインターが前提としています**構造体** **tm**オブジェクト。

## <a name="return-value"></a>戻り値

正常終了した場合は 0。 障害が発生した場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、戻り値はエラー コードになります。 エラー コードは、ERRNO.H で定義されています。 詳細については、「[errno 定数](../../c-runtime-library/errno-constants.md)」を参照してください。 各エラー条件に対して返される実際のエラー コードを、次の表に示します。

### <a name="error-conditions"></a>エラー条件

|*バッファー*|*numberOfElements*|*tmSource*|Return|値で*バッファー*|
|--------------|------------------------|----------|------------|-----------------------|
|**NULL**|どれでも可|どれでも可|**EINVAL**|変更されない|
|いない**NULL** (有効なメモリが指す)|0|どれでも可|**EINVAL**|変更されない|
|いない**NULL**|0< サイズ < 26|どれでも可|**EINVAL**|空の文字列|
|いない**NULL**|>= 26|**NULL**|**EINVAL**|空の文字列|
|いない**NULL**|>= 26|無効な時間構造体または時間のコンポーネントの値が範囲外|**EINVAL**|空の文字列|

> [!NOTE]
> エラーの状態の**wasctime_s**のような**asctime_s**の言葉でサイズの制限が測定されることは例外です。

## <a name="remarks"></a>コメント

**Asctime**関数が、構造体を文字の文字列として格納されている時刻に変換します。 *TmSource*への呼び出しから値が取得した通常**gmtime**または**localtime**です。 どちらの関数を埋めるために使用できます、 **tm**時間で定義されている構造体します。H.

|timeptr メンバー|[値]|
|--------------------|-----------|
|**tm_hour**|午前 0 時 (0 ~ 23) 以降の時間|
|**tm_isdst**|夏時間が有効な場合は正、夏時間が無効な場合は 0、夏時間かどうかが不明な場合は負。 C ランタイム ライブラリでは、アメリカ合衆国の規則を前提に夏時間 (DST) を計算します。|
|**tm_mday**|(1 ~ 31) の月の日|
|**未満**|分 (0 ~ 59)|
|**表します。**|月 (0 ~ 11 です。年 1 月 = 0)|
|**tm_sec**|秒 (0 ~ 59)|
|**tm_wday**|曜日 (0 ~ 6 です。日曜日 = 0)|
|**tm_yday**|年 (0 ~ 365; の日付1 月 1 日 = 0)|
|**tm_year**|年 (実際の西暦から 1900 を引いた数)|

変換された文字列も、ローカル タイム ゾーンの設定に従って調整されます。 ローカル タイムの設定の詳細については、[time、_time32、_time64](time-time32-time64.md)、[_ftime、_ftime32、_ftime64](ftime-ftime32-ftime64.md)、および [localtime_s、_localtime32_s、_localtime64_s](localtime-s-localtime32-s-localtime64-s.md) の関数を参照してください。また、タイム ゾーン環境とグローバル変数の定義の詳細については、[_tzset](tzset.md) 関数を参照してください。

によって生成される結果の文字列**asctime_s** 26 文字が含まれていて、フォーム`Wed Jan 02 02:03:55 1980\n\0`です。 24 時間制が使用されます。 すべてのフィールドには一定の幅があります。 文字列の最後の 2 つの位置には、改行文字と null 文字が入ります。 2 番目のパラメーターとして渡される値は、この大きさ以上にする必要があります。 エラー コードでは、以下である場合**EINVAL**が返されます。

**_wasctime_s**のワイド文字バージョンは、 **asctime_s**です。 **_wasctime_s**と**asctime_s**それ以外の場合の動作は同じです。

### <a name="generic-text-routine-mapping"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tasctime_s**|**asctime_s**|**asctime_s**|**_wasctime_s**|

C++ では、テンプレートのオーバーロードによってこれらの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**asctime_s**|\<time.h>|
|**_wasctime_s**|\<time.h> または \<wchar.h>|

## <a name="security"></a>セキュリティ

バッファー ポインターがない場合**NULL**ポインターが有効なバッファーを指していないと、した位置にあるどの関数が上書きされます。 これによりアクセス違反が発生することもあります。

渡されるサイズ引数がバッファーの実際のサイズより大きい場合、[バッファー オーバーラン](http://msdn.microsoft.com/library/windows/desktop/ms717795)が発生する場合があります。

## <a name="example"></a>例

このプログラムは、長整数型のシステム時刻を配置**時計**、構造に変換され**newtime**し、その文字列の形式に変換の出力を使用して、および、 **asctime_s**関数。

```C
// crt_asctime_s.c
#include <time.h>
#include <stdio.h>

struct tm newtime;
__time32_t aclock;

int main( void )
{
   char buffer[32];
   errno_t errNum;
   _time32( &aclock );   // Get time in seconds.
   _localtime32_s( &newtime, &aclock );   // Convert time to struct tm form.

   // Print local time as a string.

   errNum = asctime_s(buffer, 32, &newtime);
   if (errNum)
   {
       printf("Error code: %d", (int)errNum);
       return 1;
   }
   printf( "Current date and time: %s", buffer );
   return 0;
}
```

```Output
Current date and time: Wed May 14 15:30:17 2003
```

## <a name="see-also"></a>関連項目

[時間管理](../../c-runtime-library/time-management.md)<br/>
[ctime_s、_ctime32_s、_ctime64_s、_wctime_s、_wctime32_s、_wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)<br/>
[_ftime、_ftime32、_ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime_s、_gmtime32_s、_gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s、_localtime32_s、_localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[time、_time32、_time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
