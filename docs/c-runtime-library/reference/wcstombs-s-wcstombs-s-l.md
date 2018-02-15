---
title: "wcstombs_s、_wcstombs_s_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _wcstombs_s_l
- wcstombs_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wcstombs_s
- _wcstombs_s_l
dev_langs:
- C++
helpviewer_keywords:
- wcstombs_s function
- string conversion, wide characters
- wide characters, converting
- _wcstombs_s_l function
- wcstombs_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 105f2d33-221a-4f6d-864c-23c1865c42af
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 863f6dc5b1c7a41145607e8f8ba83466324dac07
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="wcstombss-wcstombssl"></a>wcstombs_s、_wcstombs_s_l

ワイド文字のシーケンスを、対応するマルチバイト文字のシーケンスに変換します。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおりセキュリティが強化されたバージョンの [wcstombs、_wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t wcstombs_s(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t *wcstr,  
   size_t count   
);  

errno_t _wcstombs_s_l(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
);  

template <size_t size>  
errno_t wcstombs_s(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count   
); // C++ only  

template <size_t size>  
errno_t _wcstombs_s_l(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>パラメーター  

[out]*pReturnValue*  
変換された文字数。  
  
[out] *mbstr*  
結果として変換されたマルチバイト文字の文字列のバッファーのアドレス。  
  
[in] *sizeInBytes*  
バイト単位のサイズ、 *mbstr*バッファー。  
  
[in] *wcstr*  
変換するワイド文字の文字列を指します。  
  
[in]*数*  
格納されるバイトの最大数、 *mbstr*バッファー、終端の null 文字を含まないまたは[_TRUNCATE](../../c-runtime-library/truncate.md)です。  
  
[in]*ロケール*  
使用するロケール。  
  
## <a name="return-value"></a>戻り値  

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。  
  
|エラー条件|戻り値および `errno`|  
|---------------------|------------------------------|  
|*mbstr* is `NULL` and *sizeInBytes* > 0|`EINVAL`|  
|*wcstr*は `NULL`|`EINVAL`|  
|コピー先のバッファーが小さすぎて、変換された文字列を含める (しない限り、*カウント*は`_TRUNCATE`; 解説を参照してください)|`ERANGE`|  
  
これらのいずれかの条件が発生すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター例外が呼び出されます。 実行の続行が許可された場合、関数はエラー コードを返し、表に示すように `errno` を設定します。  
  
## <a name="remarks"></a>コメント  

`wcstombs_s`関数によって示されるワイド文字の文字列に変換*wcstr*が指すバッファーに格納されているマルチバイト文字に*mbstr*です。 これらの条件のいずれかが満たされるまで、各文字に対して変換が続きます。  
  
-   ワイド文字の null が検出されました。  
  
-   変換できないワイド文字が検出されました。  
  
-   格納されるバイト数、 *mbstr* equals をバッファー*カウント*です。  
  
変換後の文字列は、常に null で終わります (エラーの場合も同様)。  
  
場合*カウント*特殊な値は、 [_TRUNCATE](../../c-runtime-library/truncate.md)、し`wcstombs_s`null 終端文字用の領域を残して、コピー先のバッファーに収まるようだけでなく、文字列のと同様に変換します。 文字列が切り捨てられた場合、戻り値は`STRUNCATE`と、変換が成功したと見なされます。  
  
場合`wcstombs_s`ソース文字列を変換が正常に null 終端文字を含む、変換後の文字列のバイト単位のサイズを入れ`*pReturnValue`(提供*pReturnValue*は`NULL`)。 これが発生した場合でも、 *mbstr*引数は`NULL`し、必要なバッファー サイズを決定する方法を提供します。 場合*mbstr*は`NULL`、*カウント*は無視されます。  
  
マルチバイト文字に変換できないワイド文字が検出された場合、`wcstombs_s` は `*pReturnValue` に 0 を入れ、コピー先バッファーを空文字列に設定し、`errno` を `EILSEQ` に設定して、`EILSEQ` を返します。  
  
シーケンスを指す場合*wcstr*と*mbstr*などの動作の重複`wcstombs_s`が定義されていません。  
  
> [!IMPORTANT]
>  いることを確認*wcstr*と*mbstr*が重なり合わず、および*カウント*に変換するワイド文字の数を正確に反映します。  
  
`wcstombs_s` は、ロケールに依存するあらゆる動作に現在のロケールを使用します。`_wcstombs_s_l` は、渡されたロケールを代わりに使用することを除いて `wcstombs` と同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。  
  
C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`wcstombs_s`|\<stdlib.h>|  
  
互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  

このプログラムは、`wcstombs_s` 関数の動作を示しています。  
  
```C  
// crt_wcstombs_s.c  
// This example converts a wide character  
// string to a multibyte character string.  
#include <stdio.h>  
#include <stdlib.h>  
#include <assert.h>  
  
#define BUFFER_SIZE 100  
  
int main( void )  
{  
    size_t   i;  
    char      *pMBBuffer = (char *)malloc( BUFFER_SIZE );  
    wchar_t*pWCBuffer = L"Hello, world.";  
  
    printf( "Convert wide-character string:\n" );  
  
    // Conversion  
    wcstombs_s(&i, pMBBuffer, (size_t)BUFFER_SIZE,   
               pWCBuffer, (size_t)BUFFER_SIZE );  
  
    // Output  
    printf("   Characters converted: %u\n", i);  
    printf("    Multibyte character: %s\n\n",  
     pMBBuffer );  
  
    // Free multibyte character buffer  
    if (pMBBuffer)  
    {  
    free(pMBBuffer);  
    }  
}  
```  
  
```Output  
Convert wide-character string:  
   Characters converted: 14  
    Multibyte character: Hello, world.  
```  
  
## <a name="see-also"></a>参照  

[データ変換](../../c-runtime-library/data-conversion.md)   
[ロケール](../../c-runtime-library/locale.md)   
[_mbclen、mblen、_mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
[mbstowcs、_mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
[mbtowc、_mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
[wctomb_s、_wctomb_s_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)   
[WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)