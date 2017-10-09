---
title: "IAxWinHostWindowLic インターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAxWinHostWindowLic
- No header/ATL::IAxWinHostWindowLic
- No header/ATL::CreateControlLic
- No header/ATL::CreateControlLicEx
dev_langs:
- C++
helpviewer_keywords:
- IAxWinHostWindowLic interface
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: 6d0e8c0a8ec941c7a7980b81fcd95df08298ea28
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="iaxwinhostwindowlic-interface"></a>IAxWinHostWindowLic インターフェイス
このインターフェイスは、ライセンスされたコントロールとそのホスト オブジェクトを操作するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
interface IAxWinHostWindowLic : IAxWinHostWindow
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[CreateControlLic](#createcontrollic)|ライセンスされたコントロールを作成し、そのホスト オブジェクトを結び付けます。|  
|[CreateControlLicEx](#createcontrollicex)|ライセンスされたコントロールを作成、ホスト オブジェクトをアタッチおよび必要に応じて、イベント ハンドラーを設定します。|  
  
## <a name="remarks"></a>コメント  
 `IAxWinHostWindowLic`継承[IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md)し、ライセンスされたコントロールの作成をサポートするメソッドを追加します。  
  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)のこのインターフェイスのメンバーを使用するサンプルです。  
  
## <a name="requirements"></a>要件  
 このインターフェイスの定義は、次のように idl ファイルまたは C++ として使用できます。  
  
|定義の型|ファイル|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|ATLIFace.h (ATLBase.h にも含まれます)|  
  
##  <a name="createcontrollic"></a>IAxWinHostWindowLic::CreateControlLic  
 ライセンスされたコントロールを作成、初期化して、およびで識別されるウィンドウでホスト`hWnd`です。  
  
```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```  
  
### <a name="parameters"></a>パラメーター  
 `bstrLic`  
 [in]コントロールのライセンス キーを含む BSTR です。  
  
### <a name="remarks"></a>コメント  
 参照してください[については](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol)残りのパラメーターと戻り値の詳細についてはします。  
  
 このメソッドの呼び出しは呼び出すことと同じ[呼び出し](#createcontrollicex)  
  
### <a name="example"></a>例  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)を使用するサンプルの`IAxWinHostWindowLic::CreateControlLic`します。  
  
##  <a name="createcontrollicex"></a>呼び出し  
 ライセンスされた ActiveX コントロールを作成、初期化、および指定したウィンドウでホスト[については](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol)します。  
  
```
STDMETHOD(CreateControlLicEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise,
    BSTR bstrLic);
```  
  
### <a name="parameters"></a>パラメーター  
 `bstrLic`  
 [in]コントロールのライセンス キーを含む BSTR です。  
  
### <a name="remarks"></a>コメント  
 参照してください[詳細](../../atl/reference/iaxwinhostwindow-interface.md#createcontrolex)残りのパラメーターと戻り値の詳細についてはします。  
  
### <a name="example"></a>例  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)を使用するサンプルの`IAxWinHostWindowLic::CreateControlLicEx`します。










