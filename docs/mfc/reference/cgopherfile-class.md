---
title: CGopherFile クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CGopherFile
- AFXINET/CGopherFile
- AFXINET/CGopherFile::CGopherFile
dev_langs:
- C++
helpviewer_keywords:
- CGopherFile [MFC], CGopherFile
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c6c4f87ffb1538e581320e9d6f36e8d4fbc6fc12
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335683"
---
# <a name="cgopherfile-class"></a>CGopherFile クラス
gopher サーバー上のファイルを検索し、読み込む機能が用意されています。  
  
> [!NOTE]
>  クラスは、 `CGopherConnection`、 `CGopherFile`、 `CGopherFileFind`、`CGopherLocator`と Windows XP のプラットフォームで機能しませんが、引き続き以前のプラットフォームで動作するため、そのメンバーが使用されなくなりました。  
  
## <a name="syntax"></a>構文  
  
```  
class CGopherFile : public CInternetFile  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CGopherFile::CGopherFile](#cgopherfile)|`CGopherFile` オブジェクトを構築します。|  
  
## <a name="remarks"></a>Remarks  
 Gopher サービスには、ユーザーがこのサービスは、主に情報を検索するためのメニュー方式のインターフェイスとして機能するため、gopher ファイルにデータを書き込むことはできません。 `CGopherFile`メンバー関数`Write`、 `WriteString`、および`Flush`に実装されていない`CGopherFile`します。 これらの関数を呼び出すことで、`CGopherFile`オブジェクトを返します、 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)します。  
  
 方法の詳細については、`CGopherFile`クラスでは、その他の MFC インターネット機能は、記事をご覧ください。[インターネットが WinInet を使用したプログラミング](../../mfc/win32-internet-extensions-wininet.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CGopherFile`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxinet.h  
  
##  <a name="cgopherfile"></a>  CGopherFile::CGopherFile  
 このメンバー関数が構築すると呼ばれる、`CGopherFile`オブジェクト。  
  
```  
CGopherFile(
    HINTERNET hFile,  
    CGopherLocator& refLocator,  
    CGopherConnection* pConnection);

 
CGopherFile(
    HINTERNET hFile,  
    HINTERNET hSession,  
    LPCTSTR pstrLocator,  
    DWORD dwLocLen,  
    DWORD_PTR dwContext);
```  
  
### <a name="parameters"></a>パラメーター  
 *hFile*  
 HINTERNET ファイルへのハンドル。  
  
 *refLocator*  
 参照を[CGopherLocator](../../mfc/reference/cgopherlocator-class.md)オブジェクト。  
  
 *pConnection*  
 ポインターを[CGopherConnection](../../mfc/reference/cgopherconnection-class.md)オブジェクト。  
  
 *hSession*  
 現在のインターネット セッションへのハンドル。  
  
 *pstrLocator*  
 Gopher サーバーを検索に使用する文字列へのポインター。 参照してください[Gopher セッション](cgopherlocator-class.md)gopher ロケーターの詳細についてはします。  
  
 *dwLocLen*  
 内のバイト数を含む DWORD *pstrLocator*します。  
  
 *独自*  
 開いているファイルのコンテキスト識別子へのポインター。  
  
### <a name="remarks"></a>Remarks  
 必要があります、 `CGopherFile` gopher インターネット セッション中に、ファイルから読み取るオブジェクト。  
  
 作成することはありません、`CGopherFile`オブジェクトに直接します。 代わりに、 [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile)を gopher サーバー上のファイルを開きます。  
  
## <a name="see-also"></a>関連項目  
 [CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)   
 [CGopherLocator クラス](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFileFind クラス](../../mfc/reference/cgopherfilefind-class.md)   
 [CGopherConnection クラス](../../mfc/reference/cgopherconnection-class.md)
