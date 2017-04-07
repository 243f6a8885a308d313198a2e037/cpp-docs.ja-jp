---
title: "CAtlFile クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlFile
- ATLFILE/ATL::CAtlFile
- ATLFILE/ATL::CAtlFile::CAtlFile
- ATLFILE/ATL::CAtlFile::Create
- ATLFILE/ATL::CAtlFile::Flush
- ATLFILE/ATL::CAtlFile::GetOverlappedResult
- ATLFILE/ATL::CAtlFile::GetPosition
- ATLFILE/ATL::CAtlFile::GetSize
- ATLFILE/ATL::CAtlFile::LockRange
- ATLFILE/ATL::CAtlFile::Read
- ATLFILE/ATL::CAtlFile::Seek
- ATLFILE/ATL::CAtlFile::SetSize
- ATLFILE/ATL::CAtlFile::UnlockRange
- ATLFILE/ATL::CAtlFile::Write
- ATLFILE/ATL::CAtlFile::m_pTM
dev_langs:
- C++
helpviewer_keywords:
- CAtlFile class
ms.assetid: 93ed160b-af2a-448c-9cbe-e5fa46c199bb
caps.latest.revision: 23
author: mikeblome
ms.author: mblome
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5ba8aa0bc5544d8d541fecb87e2eb0108c2c5ebd
ms.lasthandoff: 02/24/2017

---
# <a name="catlfile-class"></a>CAtlFile クラス
このクラスは、ファイル処理 API、Windows の thin ラッパーを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CAtlFile : public CHandle
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlFile::CAtlFile](#catlfile)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlFile::Create](#create)|作成するか、ファイルを開くには、このメソッドを呼び出します。|  
|[CAtlFile::Flush](#flush)|ファイルのバッファーをクリアして、ファイルに書き込まれるバッファー内のすべてのデータには、このメソッドを呼び出します。|  
|[CAtlFile::GetOverlappedResult](#getoverlappedresult)|ファイルの重複した操作の結果を取得するには、このメソッドを呼び出します。|  
|[CAtlFile::GetPosition](#getposition)|ファイルから現在のファイル ポインターの位置を取得するには、このメソッドを呼び出します。|  
|[CAtlFile::GetSize](#getsize)|ファイルのバイト単位のサイズを取得するには、このメソッドを呼び出します。|  
|[CAtlFile::LockRange](#lockrange)|他のプロセスがアプリケーションにアクセスすることを防ぐために、ファイル内の領域をロックするには、このメソッドを呼び出します。|  
|[CAtlFile::Read](#read)|ファイル ポインターが指す位置以降にあるファイルからデータを読み取るには、このメソッドを呼び出します。|  
|[CAtlFile::Seek](#seek)|ファイルのファイル ポインターを移動するには、このメソッドを呼び出します。|  
|[CAtlFile::SetSize](#setsize)|ファイルのサイズを設定するには、このメソッドを呼び出します。|  
|[CAtlFile::UnlockRange](#unlockrange)|ファイルの領域のロックを解除するには、このメソッドを呼び出します。|  
|[CAtlFile::Write](#write)|ファイル ポインターが指す位置以降にあるファイルにデータを書き込むには、このメソッドを呼び出します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlFile::m_pTM](#m_ptm)|ポインター`CAtlTransactionManager`オブジェクト|  
  
## <a name="remarks"></a>コメント  
 ファイル処理要件は比較的単純な Windows API が提供する以上の複数の抽象化は、MFC の依存関係を含めずに、必要な場合は、このクラスを使用します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CHandle](../../atl/reference/chandle-class.md)  
  
 `CAtlFile`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlfile.h  
  
##  <a name="catlfile"></a>CAtlFile::CAtlFile  
 コンストラクターです。  
  
```
CAtlFile() throw();
CAtlFile(CAtlTransactionManager* pTM = NULL) throw();
CAtlFile(CAtlFile& file) throw();
explicit CAtlFile(HANDLE hFile) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `file`  
 ファイル オブジェクト。  
  
 `hFile`  
 ファイル ハンドル。  
  
 `pTM`  
 CAtlTransactionManager オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 コピー コンス トラクターは、元のファイル ハンドルの所有権を譲渡`CAtlFile`オブジェクトを新しく構築されたオブジェクトにします。  
  
##  <a name="create"></a>CAtlFile::Create  
 作成するか、ファイルを開くには、このメソッドを呼び出します。  
  
```
HRESULT Create(
    LPCTSTR szFilename,
    DWORD dwDesiredAccess,
    DWORD dwShareMode,
    DWORD dwCreationDisposition,
    DWORD dwFlagsAndAttributes = FILE_ATTRIBUTE_NORMAL,
    LPSECURITY_ATTRIBUTES lpsa = NULL,
    HANDLE hTemplateFile = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *szFilename*  
 ファイル名。  
  
 `dwDesiredAccess`  
 必要なアクセスします。 参照してください`dwDesiredAccess`で[CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `dwShareMode`  
 共有モードです。 参照してください`dwShareMode`で**CreateFile**します。  
  
 `dwCreationDisposition`  
 作成処理します。 参照してください`dwCreationDisposition`で**CreateFile**します。  
  
 `dwFlagsAndAttributes`  
 フラグと属性。 参照してください`dwFlagsAndAttributes`で**CreateFile**します。  
  
 `lpsa`  
 セキュリティ属性。 参照してください*lpSecurityAttributes*で**CreateFile**します。  
  
 `hTemplateFile`  
 テンプレート ファイルです。 参照してください`hTemplateFile`で**CreateFile**します。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 呼び出し[CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858)を作成またはファイルを開きます。  
  
##  <a name="flush"></a>CAtlFile::Flush  
 ファイルのバッファーをクリアして、ファイルに書き込まれるバッファー内のすべてのデータには、このメソッドを呼び出します。  
  
```
HRESULT Flush() throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 呼び出し[FlushFileBuffers](http://msdn.microsoft.com/library/windows/desktop/aa364439)バッファー内のデータをファイルにフラッシュします。  
  
##  <a name="getoverlappedresult"></a>CAtlFile::GetOverlappedResult  
 ファイルの重複した操作の結果を取得するには、このメソッドを呼び出します。  
  
```
HRESULT GetOverlappedResult(
    LPOVERLAPPED pOverlapped,
    DWORD& dwBytesTransferred,
    BOOL bWait) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pOverlapped`  
 Overlapped 構造体。 参照してください`lpOverlapped`で[GetOverlappedResult](http://msdn.microsoft.com/library/windows/desktop/ms683209)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 *dwBytesTransferred*  
 バイトが転送されます。 参照してください*lpNumberOfBytesTransferred*で`GetOverlappedResult`します。  
  
 `bWait`  
 待機 オプション。 「`bWait`」の「`GetOverlappedResult`」を参照してください。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 呼び出し[GetOverlappedResult](http://msdn.microsoft.com/library/windows/desktop/ms683209)ファイルの重複した操作の結果を取得します。  
  
##  <a name="getposition"></a>CAtlFile::GetPosition  
 現在のファイル ポインターの位置を取得するには、このメソッドを呼び出します。  
  
```
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nPos`  
 内のバイト位置。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 呼び出し[SetFilePointer](http://msdn.microsoft.com/library/windows/desktop/aa365541)を現在のファイル ポインターの位置を取得します。  
  
##  <a name="getsize"></a>CAtlFile::GetSize  
 ファイルのバイト単位のサイズを取得するには、このメソッドを呼び出します。  
  
```
HRESULT GetSize(ULONGLONG& nLen) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nLen`  
 ファイル内のバイト数。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 呼び出し[GetFileSize](http://msdn.microsoft.com/library/windows/desktop/aa364955)ファイルのバイト単位でサイズを取得します。  
  
##  <a name="lockrange"></a>CAtlFile::LockRange  
 他のプロセスがアプリケーションにアクセスすることを防ぐために、ファイル内の領域をロックするには、このメソッドを呼び出します。  
  
```
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nPos`  
 ロックの開始位置を示すファイル内の位置。  
  
 `nCount`  
 ロックするバイト範囲の長さ。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 呼び出し[ロック ファイル](http://msdn.microsoft.com/library/windows/desktop/aa365202)ファイルに領域をロックします。 ファイル内のバイトをロックすると、他のプロセスがそれらのバイトにアクセスできなくなります。 ファイルの&1; つ以上の領域をロックすることができますが、重なり合う領域は使用できません。 使用して、領域のロックを解除するときに[CAtlFile::UnlockRange](#unlockrange)バイトの範囲は、以前にロックされた領域と正確に一致する必要があります。 `LockRange`マージされず、隣接する領域です。2 つのロックされた領域が隣接している場合は、必要がありますロックを解除する各とは別にします。  
  
##  <a name="m_ptm"></a>CAtlFile::m_pTM  
 ポインター、`CAtlTransactionManager`オブジェクトです。  
  
```
CAtlTransactionManager* m_pTM;
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="read"></a>CAtlFile::Read  
 ファイル ポインターが指す位置以降にあるファイルからデータを読み取るには、このメソッドを呼び出します。  
  
```
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped,
    LPOVERLAPPED_COMPLETION_ROUTINE pfnCompletionRoutine) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pBuffer`  
 ファイルから読み取られたデータを受け取るバッファーへのポインター。  
  
 `nBufSize`  
 バイト単位のバッファー サイズ。  
  
 `nBytesRead`  
 読み取られたバイト数。  
  
 `pOverlapped`  
 Overlapped 構造体。 参照してください`lpOverlapped`で[ReadFile](http://msdn.microsoft.com/library/windows/desktop/aa365467)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `pfnCompletionRoutine`  
 メモリを割り当てます。 参照してください*lpCompletionRoutine*で[ReadFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365468)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 最初の&3; つのフォームを呼び出す[ReadFile](http://msdn.microsoft.com/library/windows/desktop/aa365467)、最後の[ReadFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365468)ファイルからデータを読み取れません。 使用[CAtlFile::Seek](#seek)ファイル ポインターを移動します。  
  
##  <a name="seek"></a>CAtlFile::Seek  
 ファイルのファイル ポインターを移動するには、このメソッドを呼び出します。  
  
```
HRESULT Seek(
    LONGLONG nOffset,
    DWORD dwFrom = FILE_CURRENT) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nOffset`  
 指定された開始点からのオフセット`dwFrom`します。  
  
 `dwFrom`  
 (FILE_BEGIN、FILE_CURRENT、または FILE_END) の開始位置。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 呼び出し[SetFilePointer](http://msdn.microsoft.com/library/windows/desktop/aa365541)ファイル ポインターを移動します。  
  
##  <a name="setsize"></a>CAtlFile::SetSize  
 ファイルのサイズを設定するには、このメソッドを呼び出します。  
  
```
HRESULT SetSize(ULONGLONG nNewLen) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nNewLen`  
 ファイルのバイトの新しい長さ。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 呼び出し[SetFilePointer](http://msdn.microsoft.com/library/windows/desktop/aa365541)と[SetEndOfFile](http://msdn.microsoft.com/library/windows/desktop/aa365531)ファイルのサイズを設定します。 返された場合は、ファイル ポインターは、ファイルの末尾に配置されます。  
  
##  <a name="unlockrange"></a>CAtlFile::UnlockRange  
 ファイルの領域のロックを解除するには、このメソッドを呼び出します。  
  
```
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nPos`  
 ロックの解除を開始する位置を示すファイル内の位置。  
  
 `nCount`  
 ロックを解除するバイト範囲の長さ。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 呼び出し[UnlockFile](http://msdn.microsoft.com/library/windows/desktop/aa365715)ファイルの領域のロックを解除します。  
  
##  <a name="write"></a>CAtlFile::Write  
 ファイル ポインターが指す位置以降にあるファイルにデータを書き込むには、このメソッドを呼び出します。  
  
```
HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped,
    LPOVERLAPPED_COMPLETION_ROUTINE pfnCompletionRoutine) throw();

HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();

HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pBuffer`  
 ファイルに書き込まれるデータを保持するバッファー。  
  
 `nBufSize`  
 バッファーからの転送バイト数。  
  
 `pOverlapped`  
 Overlapped 構造体。 参照してください`lpOverlapped`で[WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `pfnCompletionRoutine`  
 メモリを割り当てます。 参照してください*lpCompletionRoutine*で[WriteFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365748)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `pnBytesWritten`  
 書き込まれたバイト。  
  
### <a name="return-value"></a>戻り値  
 返します。`S_OK`に成功した場合、またはエラー`HRESULT`失敗します。  
  
### <a name="remarks"></a>コメント  
 最初の&3; つのフォームを呼び出す[WriteFile](http://msdn.microsoft.com/library/windows/desktop/aa365747)、最後の呼び出し[WriteFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365748)ファイルにデータを書き込めません。 使用[CAtlFile::Seek](#seek)ファイル ポインターを移動します。  
  
## <a name="see-also"></a>関連項目  
 [マーキーのサンプル](../../visual-cpp-samples.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CHandle クラス](../../atl/reference/chandle-class.md)

