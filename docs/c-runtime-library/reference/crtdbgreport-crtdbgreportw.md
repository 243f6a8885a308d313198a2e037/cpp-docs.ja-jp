---
title: _CrtDbgReport、_CrtDbgReportW | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _CrtDbgReport
- _CrtDbgReportW
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
apitype: DLLExport
f1_keywords:
- CrtDbgReport
- CrtDbgReportW
- _CrtDbgReportW
- _CrtDbgReport
dev_langs:
- C++
helpviewer_keywords:
- debug reporting
- _CrtDbgReport function
- CrtDbgReport function
- CrtDbgReportW function
- _CrtDbgReportW function
ms.assetid: 6e581fb6-f7fb-4716-9432-f0145d639ecc
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6857f264618065c6d88a5efa92ee5a19abbc0c67
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="crtdbgreport-crtdbgreportw"></a>_CrtDbgReport、_CrtDbgReportW

デバッグ メッセージのあるレポートを生成し、3 つの宛先 (デバッグ バージョンのみ) にレポートを送信します。

## <a name="syntax"></a>構文

```C
int _CrtDbgReport(
   int reportType,
   const char *filename,
   int linenumber,
   const char *moduleName,
   const char *format [,
   argument] ...
);
int _CrtDbgReportW(
   int reportType,
   const wchar_t *filename,
   int linenumber,
   const wchar_t *moduleName,
   const wchar_t *format [,
   argument] ...
);
```

### <a name="parameters"></a>パラメーター

*reportType*<br/>
レポートの種類:**前述**、 **_CRT_ERROR**、および **_CRT_ASSERT**です。

*ファイル名*<br/>
アサート/レポートが発生したソース ファイルの名前へのポインターまたは**NULL**です。

*行番号*<br/>
アサート/レポートが発生したソース ファイルの数の行または**NULL**です。

*moduleName*<br/>
アサートまたはレポートが発生したモジュール (.exe または .dll) 名へのポインター。

*format*<br/>
ユーザー メッセージの作成に使用される書式指定文字列へのポインター。

*argument*<br/>
使用される省略可能な代用引数*形式*です。

## <a name="return-value"></a>戻り値

すべてのレポート送信先 **_CrtDbgReport**と **_CrtDbgReportW**エラーが発生しなかった場合、エラーが発生した場合は-1、0 を返します。 ただし、レポートの宛先がデバッグ メッセージ ウィンドウで、ユーザーが **[再試行]** をクリックすると、これらの関数は 1 を返します。 ユーザーがデバッグ メッセージ ウィンドウの **[中止]** をクリックすると、関数はすぐに中止され、値は返されません。

[_RPT、_RPTF](rpt-rptf-rptw-rptfw-macros.md)マクロ呼び出しをデバッグ **_CrtDbgReport**レポートをデバッグを生成します。 これらのマクロのワイド文字バージョンと、 [_ASSERT、_ASSERTE](assert-asserte-assert-expr-macros.md)、 [_RPTW](rpt-rptf-rptw-rptfw-macros.md)と[_RPTFW](rpt-rptf-rptw-rptfw-macros.md)を使用して **_CrtDbgReportW**にデバッグ レポートを生成します。 ときに **_CrtDbgReport**または **_CrtDbgReportW** 1 を返してジャスト イン タイム (JIT) デバッグが有効になっていれば、これらのマクロは、デバッガーを起動します。

## <a name="remarks"></a>コメント

**_CrtDbgReport**と **_CrtDbgReportW** 3 種類の宛先へデバッグ レポートを送信できます。 デバッグ レポート ファイル、デバッグ モニター (Visual Studio デバッガー)、またはデバッグ メッセージ ウィンドウです。 2 つの構成関数 [_CrtSetReportMode](crtsetreportmode.md) および [_CrtSetReportFile](crtsetreportfile.md) は、各レポートの種類の出力先を指定するために使用されます。 これらの関数では、各レポートの種類に対するレポートの宛先を個別に管理できます。 たとえば、ことを指定することは、 *reportType*の**前述**にのみ、デバッグ モニターに送信中に、 *reportType*の **_CRT_ASSERT**デバッグ メッセージ ウィンドウとユーザー定義のレポート ファイルに送信されます。

**_CrtDbgReportW**のワイド文字バージョンは、 **_CrtDbgReport**です。 すべての出力および文字列のパラメーターは、ワイド文字列内にあり、それ以外の場合は 1 バイト文字バージョンと同じです。

**_CrtDbgReport**と **_CrtDbgReportW**で置き換えることによって、デバッグ レポートのユーザー メッセージを作成、*引数***[n]**、引数*形式*文字列、によって定義されている同じ規則を使用して、 **printf**または**wprintf**関数。 に対して定義されているファイルとこれらの関数はデバッグ レポートを生成し、決定、宛先、現在のレポート モードに基づく*reportType*です。 レポートは、デバッグ メッセージ ウィンドウに送信されるときに、 *filename*、 **lineNumber**と*moduleName*ウィンドウに表示される情報に含まれます。

次の表は、レポートのモードまたはモードおよびファイル サービスおよび結果の動作で使用できる選択肢 **_CrtDbgReport**と **_CrtDbgReportW**です。 これらのオプションは、\<crtdbg.h> でビット フラグとして定義されています。

|レポート モード|レポート ファイル|**_CrtDbgReport**、 **_CrtDbgReportW**動作|
|-----------------|-----------------|------------------------------------------------|
|**_CRTDBG_MODE_DEBUG**|利用不可|Windows [OutputDebugString](http://msdn.microsoft.com/library/windows/desktop/aa363362.aspx) API にメッセージを書き込みます。|
|**_CRTDBG_MODE_WNDW**|利用不可|Windows [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) API を呼び出して、メッセージおよび **[中止]**、**[再試行]**、**[無視]** の各ボタンを表示するメッセージ ボックスを作成します。 クリックすると**中止**、 **_CrtDbgReport**または **_CrtDbgReport**すぐに中止します。 ユーザーが **[再試行]** をクリックすると、1 を返します。 クリックすると**無視**、実行が継続と **_CrtDbgReport**と **_CrtDbgReportW** 0 を返します。 エラー状況が存在するときに **[無視]** をクリックすると、"未定義の動作" という結果になることがよくあります。|
|**_CRTDBG_MODE_FILE**|**__HFILE**|ユーザーが指定したメッセージを書き込みます**処理**、Windows を使用して[WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747.aspx) API との機能はファイル ハンドルの有効性を確認できませんアプリケーションは、レポート ファイルを開くと、有効なファイルを渡します。処理します。|
|**_CRTDBG_MODE_FILE**|**_CRTDBG_FILE_STDERR**|メッセージを書き込みます**stderr**です。|
|**_CRTDBG_MODE_FILE**|**_CRTDBG_FILE_STDOUT**|メッセージを書き込みます**stdout**です。|

レポートは 1 つ、2 つ、または 3 つの宛先に送信できます。またどの宛先にも送信しないこともできます。 レポート モードおよびレポート ファイルを指定する方法の詳細については、「[_CrtSetReportMode](crtsetreportmode.md)」および「[_CrtSetReportFile](crtsetreportfile.md)」関数を参照してください。 デバッグ マクロおよびレポート関数の使用方法の詳細については、「[レポート用マクロの使用](/visualstudio/debugger/macros-for-reporting)」を参照してください。

によって提供されるより柔軟に処理が、アプリケーションに必要なかどうかは **_CrtDbgReport**と **_CrtDbgReportW**、独自のレポート関数を作成し、C ランタイム ライブラリのレポートにフックできますメカニズムを使用して、 [_CrtSetReportHook](crtsetreporthook.md)関数。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_CrtDbgReport**|\<crtdbg.h>|
|**_CrtDbgReportW**|\<crtdbg.h>|

**_CrtDbgReport**と **_CrtDbgReportW** Microsoft の拡張機能です。 詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="example"></a>例

```C
// crt_crtdbgreport.c
#include <crtdbg.h>

int main(int argc, char *argv[]) {
#ifdef _DEBUG
   _CrtDbgReport(_CRT_ASSERT, __FILE__, __LINE__, argv[0], NULL);
#endif
}
```

レポート関数を変更する方法の例については、「[crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2)」を参照してください。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetReportMode](crtsetreportmode.md)<br/>
[_CrtSetReportFile](crtsetreportfile.md)<br/>
[printf、_printf_l、wprintf、_wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
