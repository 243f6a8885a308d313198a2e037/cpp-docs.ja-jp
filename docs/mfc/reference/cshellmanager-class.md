---
title: "CShellManager クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CShellManager
- AFXSHELLMANAGER/CShellManager
- AFXSHELLMANAGER/CShellManager::CShellManager
- AFXSHELLMANAGER/CShellManager::BrowseForFolder
- AFXSHELLMANAGER/CShellManager::ConcatenateItem
- AFXSHELLMANAGER/CShellManager::CopyItem
- AFXSHELLMANAGER/CShellManager::CreateItem
- AFXSHELLMANAGER/CShellManager::FreeItem
- AFXSHELLMANAGER/CShellManager::GetItemCount
- AFXSHELLMANAGER/CShellManager::GetItemSize
- AFXSHELLMANAGER/CShellManager::GetNextItem
- AFXSHELLMANAGER/CShellManager::GetParentItem
- AFXSHELLMANAGER/CShellManager::ItemFromPath
dev_langs:
- C++
helpviewer_keywords:
- CShellManager [MFC], CShellManager
- CShellManager [MFC], BrowseForFolder
- CShellManager [MFC], ConcatenateItem
- CShellManager [MFC], CopyItem
- CShellManager [MFC], CreateItem
- CShellManager [MFC], FreeItem
- CShellManager [MFC], GetItemCount
- CShellManager [MFC], GetItemSize
- CShellManager [MFC], GetNextItem
- CShellManager [MFC], GetParentItem
- CShellManager [MFC], ItemFromPath
ms.assetid: f15c4c1a-6fae-487d-9913-9b7369b33da0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3e1e3fcff06b2937df8218ce1ab32b91ddf22a7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cshellmanager-class"></a>CShellManager クラス
ID リストへのポインター (PIDL) を操作するためのさまざまなメソッドを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CShellManager : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CShellManager::CShellManager](#cshellmanager)|`CShellManager` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CShellManager::BrowseForFolder](#browseforfolder)|ユーザーがシェル フォルダーを選択できるダイアログ ボックスが表示されます。|  
|[CShellManager::ConcatenateItem](#concatenateitem)|2 つの Pidl を連結します。|  
|[CShellManager::CopyItem](#copyitem)|新しい PIDL を作成し、指定した PIDL をコピーします。|  
|[CShellManager::CreateItem](#createitem)|指定したサイズの新しい PIDL を作成します。|  
|[CShellManager::FreeItem](#freeitem)|指定した PIDL を削除します。|  
|[CShellManager::GetItemCount](#getitemcount)|指定した PIDL で項目の数を返します。|  
|[CShellManager::GetItemSize](#getitemsize)|指定した PIDL のサイズを返します。|  
|[CShellManager::GetNextItem](#getnextitem)|PIDL から次の項目を返します。|  
|[CShellManager::GetParentItem](#getparentitem)|指定された項目の親項目を取得します。|  
|[CShellManager::ItemFromPath](#itemfrompath)|指定されたパスで識別される項目の PIDL を取得します。|  
  
## <a name="remarks"></a>コメント  
 メソッド、`CShellManager`クラス Pidl をすべて処理します。 PIDL は、シェル オブジェクトの一意の識別子です。  
  
 作成しないようにする、`CShellManager`手動でのオブジェクトします。 アプリケーションのためにフレームワークによって自動的に作成されます。 ただし、呼び出す必要があります[CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager)アプリケーションの初期化プロセス中にします。 アプリケーションのシェル マネージャーへのポインターを取得する[CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CShellManager](../../mfc/reference/cshellmanager-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxshellmanager.h  
  
##  <a name="browseforfolder"></a>CShellManager::BrowseForFolder  
 ユーザーがシェル フォルダーを選択できるダイアログ ボックスが表示されます。  
  
```  
BOOL BrowseForFolder(
    CString& strOutFolder,  
    CWnd* pWndParent = NULL,  
    LPCTSTR lplszInitialFolder = NULL,  
    LPCTSTR lpszTitle = NULL,  
    UINT ulFlags = BIF_RETURNONLYFSDIRS,  
    LPINT piFolderImage = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `strOutFolder`  
 選択したフォルダーのパスを格納するメソッドによって使用される文字列。  
  
 [入力] `pWndParent`  
 親ウィンドウへのポインター。  
  
 [入力] `lplszInitialFolder`  
 ダイアログ ボックスが表示されたら、既定で選択されているフォルダーを含む文字列です。  
  
 [入力] `lpszTitle`  
 ダイアログ ボックスのタイトル。  
  
 [入力] `ulFlags`  
 ダイアログ ボックスのオプションを指定するフラグ。 参照してください[BROWSEINFO](http://msdn.microsoft.com/library/windows/desktop/bb773205)詳細についてはします。  
  
 [出力] `piFolderImage`  
 メソッドが、選択したフォルダーのイメージのインデックスを書き込む整数値へのポインター。  
  
### <a name="return-value"></a>戻り値  
 ユーザーがダイアログ ボックスからフォルダーを選択した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出すときに、アプリケーションを作成し、ユーザーがフォルダーを選択できるダイアログ ボックスが表示されます。 メソッドは、フォルダーのパスを記述、`strOutFolder`パラメーター。  
  
### <a name="example"></a>例  
 次の例への参照を取得する方法を示します、`CShellManager`オブジェクトを使用して、`CWinAppEx::GetShellManager`メソッドを使用する方法、`BrowseForFolder`メソッドです。 このコード スニペットの一部である、[エクスプ ローラー サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_Explorer#6](../../mfc/reference/codesnippet/cpp/cshellmanager-class_1.cpp)]  
  
##  <a name="concatenateitem"></a>CShellManager::ConcatenateItem  
 2 つの Pidl を含む新しいリストを作成します。  
  
```  
LPITEMIDLIST ConcatenateItem(
    LPCITEMIDLIST pidl1,  
    LPCITEMIDLIST pidl2);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pidl1`  
 最初の項目。  
  
 [入力] `pidl2`  
 2 番目の項目。  
  
### <a name="return-value"></a>戻り値  
 それ以外の場合、関数が成功した場合は、新しい項目リストへのポインター`NULL`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、新しい作成[ITEMIDLIST](http://msdn.microsoft.com/library/windows/desktop/bb773321)両方を格納するのに十分な大きさ`pidl1`と`pidl2`です。 コピーし、`pidl1`と`pidl2`新しいリストにします。  
  
##  <a name="copyitem"></a>CShellManager::CopyItem  
 項目のリストをコピーします。  
  
```  
LPITEMIDLIST CopyItem(LPCITEMIDLIST pidlSource);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pidlSource`  
 元の項目のリスト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、新しく作成されたアイテム リストへのポインターそれ以外の場合`NULL`です。  
  
### <a name="remarks"></a>コメント  
 新しく作成されたアイテムのリストには、元の項目リストと同じサイズがあります。  
  
##  <a name="createitem"></a>CShellManager::CreateItem  
 新しい PIDL を作成します。  
  
```  
LPITEMIDLIST CreateItem(UINT cbSize);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `cbSize`  
 項目リストのサイズ。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、作成されたアイテム リストへのポインターそれ以外の場合`NULL`です。  
  
##  <a name="cshellmanager"></a>CShellManager::CShellManager  
 `CShellManager` オブジェクトを構築します。  
  
```  
CShellManager();
```  
  
### <a name="remarks"></a>コメント  
 ほとんどの場合は作成する必要はありません、`CShellManager`直接です。 既定では、フレームワークの機能の 1 つを作成します。 ポインターを取得する、 `CShellManager`、呼び出す[CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager)です。 作成する場合、 `CShellManager` 、手動でメソッドを使用して初期化する必要があります[CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager)です。  
  
##  <a name="freeitem"></a>CShellManager::FreeItem  
 項目のリストを削除します。  
  
```  
void FreeItem(LPITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pidl`  
 削除する項目一覧。  
  
##  <a name="getitemcount"></a>CShellManager::GetItemCount  
 項目リストの項目の数を返します。  
  
```  
UINT GetItemCount(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pidl`  
 項目のリストへのポインター。  
  
### <a name="return-value"></a>戻り値  
 項目の一覧で項目の数。  
  
##  <a name="getitemsize"></a>CShellManager::GetItemSize  
 項目リストのサイズを返します。  
  
```  
UINT GetItemSize(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pidl`  
 項目のリストへのポインター。  
  
### <a name="return-value"></a>戻り値  
 項目リストのサイズ。  
  
##  <a name="getnextitem"></a>CShellManager::GetNextItem  
 項目識別子の一覧 (PIDL) ポインターから次の項目を取得します。  
  
```  
LPITEMIDLIST GetNextItem(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pidl`  
 反復処理する項目の一覧。  
  
### <a name="return-value"></a>戻り値  
 一覧の次の項目へのポインター。  
  
### <a name="remarks"></a>コメント  
 これ以上項目をかどうかは、一覧にある、このメソッドが戻る`NULL`です。  
  
##  <a name="getparentitem"></a>CShellManager::GetParentItem  
 項目識別子の一覧 (PIDL) へのポインターの親を取得します。  
  
```  
int GetParentItem(
    LPCITEMIDLIST lpidl,  
    LPITEMIDLIST& lpidlParent);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpidl`  
 親を取得する PIDL です。  
  
 [出力] `lpidlParent`  
 メソッドが、結果を格納する PIDL への参照。  
  
### <a name="return-value"></a>戻り値  
 親 PIDL のレベルです。  
  
### <a name="remarks"></a>コメント  
 デスクトップ相対パス PIDL のレベルです。 デスクトップの PIDL は、レベル 0 を持つと見なされます。  
  
##  <a name="itemfrompath"></a>CShellManager::ItemFromPath  
 文字列のパスで識別される項目から項目識別子の一覧 (PIDL) をポインターを取得します。  
  
```  
HRESULT ItemFromPath(
    LPCTSTR lpszPath,  
    LPITEMIDLIST& pidl);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszPath`  
 項目のパスを指定する文字列。  
  
 [出力] `pidl`  
 PIDL への参照。 メソッドでは、この PIDL を使用して、その戻り値へのポインターを格納します。  
  
### <a name="return-value"></a>戻り値  
 返します`NOERROR`成功した場合、OLE 定義のエラー値。  
  
## <a name="see-also"></a>参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)
