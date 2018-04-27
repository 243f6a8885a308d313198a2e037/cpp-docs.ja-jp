---
title: _CrtDoForAllClientObjects | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _CrtDoForAllClientObjects
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
- _CrtDoForAllClientObjects
- CrtDoForAllClientObjects
- crtdbg/_CrdDoForAllClientObjects
dev_langs:
- C++
helpviewer_keywords:
- _CrtDoForAllClientObjects function
- CrtDoForAllClientObjects function
ms.assetid: d0fdb835-3cdc-45f1-9a21-54208e8df248
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 83c555899807c9236b803b0576bc8bf6884fd944
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="crtdoforallclientobjects"></a>_CrtDoForAllClientObjects

すべてのアプリケーションによって提供される関数を呼び出す **_CLIENT_BLOCK** (デバッグ バージョンのみ)、ヒープ内の型。

## <a name="syntax"></a>構文

```C
void _CrtDoForAllClientObjects(
   void ( * pfn )( void *, void * ),
   void *context
);
```

### <a name="parameters"></a>パラメーター

*pfn*アプリケーションによって提供される関数のコールバック関数へのポインター。 この関数の最初のパラメーターは、データを指します。 2 番目のパラメーターが呼び出しに渡されるコンテキスト ポインター **_CrtDoForAllClientObjects**です。

*コンテキスト*アプリケーションによって提供される関数に渡すアプリケーションによって提供されるコンテキストへのポインター。

## <a name="remarks"></a>コメント

**_CrtDoForAllClientObjects**関数のメモリ ブロックをヒープのリンク リストの検索、 **_CLIENT_BLOCK**型と呼び出しがある場合、この型のブロック、アプリケーションによって提供される関数。 見つかったブロックと*コンテキスト*パラメーターは、アプリケーションによって提供される関数に引数として渡されます。 デバッグ中にアプリケーションは、明示的に関数を呼び出して、デバッグ ヒープ、メモリを割り当てるし、ブロックが割り当てられることを指定することによって割り当ての特定のグループを追跡できる、 **_CLIENT_BLOCK**ブロック型です。 これらのブロックは個別に追跡し、リーク検出やメモリ状態のレポート時に異なる方法で報告できます。

場合、 **_CRTDBG_ALLOC_MEM_DF**のビット フィールド、 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)フラグが有効でない **_CrtDoForAllClientObjects**が直ちに返されます。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていないへの呼び出し **_CrtDoForAllClientObjects**プリプロセス時に削除されます。

詳細については、 **_CLIENT_BLOCK**を入力し、その他のデバッグ関数で使用する方法を参照してください。[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)です。 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。

場合*pfn*は**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)に設定されている**EINVAL**関数を返します。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_CrtDoForAllClientObjects**|\<crtdbg.h>、\<errno.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

**ライブラリ:** ユニバーサル C ランタイム ライブラリのデバッグ バージョンのみ。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
[ヒープの状態をレポートする関数](/visualstudio/debugger/crt-debug-heap-details)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
