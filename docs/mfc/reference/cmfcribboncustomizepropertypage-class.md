---
title: "CMFCRibbonCustomizePropertyPage クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::AddCustomCategory
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::OnOK
dev_langs: C++
helpviewer_keywords:
- CMFCRibbonCustomizePropertyPage [MFC], CMFCRibbonCustomizePropertyPage
- CMFCRibbonCustomizePropertyPage [MFC], AddCustomCategory
- CMFCRibbonCustomizePropertyPage [MFC], OnOK
ms.assetid: ea32a99a-dfbe-401e-8975-aa191552532f
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2ad58cb0b062e25a52742eec5491489d3744a9ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcribboncustomizepropertypage-class"></a>CMFCRibbonCustomizePropertyPage クラス
カスタム ページを実装して、**カスタマイズ**リボン ベースのアプリケーション ダイアログ ボックス。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonCustomizePropertyPage: public CMFCPropertyPage  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage](#cmfcribboncustomizepropertypage)|`CMFCRibbonCustomizePropertyPage` オブジェクトを構築します。|  
|`CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCRibbonCustomizePropertyPage::AddCustomCategory](#addcustomcategory)|カスタム カテゴリを追加、**コマンド**コンボ ボックス。|  
|`CMFCRibbonCustomizePropertyPage::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|`CMFCRibbonCustomizePropertyPage::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCRibbonCustomizePropertyPage::OnOK](#onok)|ユーザーがクリックすると、システムによって呼び出されます**OK**上、**カスタマイズ** ダイアログ ボックス。|  
  
## <a name="remarks"></a>コメント  
 カスタム コマンドを追加する場合、**カスタマイズ**ダイアログ ボックスで、AFX_WM_ON_RIBBON_CUSTOMIZE メッセージを処理する必要があります。 メッセージ ハンドラーでインスタンス化、`CMFCRibbonCustomizePropertyPage`スタック上のオブジェクト。 カスタムのコマンドの一覧を作成し、呼び出す`AddCustomCategory`に新しいページを追加する、**カスタマイズ** ダイアログ ボックス。  
  
## <a name="example"></a>例  
 次の例で作成する方法、`CMFCRibbonCustomizePropertyPage`オブジェクトと、カスタム カテゴリを追加します。  
  
 [!code-cpp[NVC_MFC_RibbonApp#22](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizepropertypage-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)  
  
 [CMFCRibbonCustomizePropertyPage](../../mfc/reference/cmfcribboncustomizepropertypage-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxribboncustomizedialog.h  
  
##  <a name="addcustomcategory"></a>CMFCRibbonCustomizePropertyPage::AddCustomCategory  
 カスタム カテゴリを追加、**コマンド**コンボ ボックス。  
  
```  
void AddCustomCategory(
    LPCTSTR lpszName,  
    const CList<UINT, UINT>& lstIDS);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `lpszName`|カスタムのカテゴリの名前を指定します。|  
|[入力] `lstIDS`|カスタムのカテゴリに表示されるリボン コマンド Id が含まれています。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは、という名前のカテゴリを追加`lpszName`を**コマンド**コンボ ボックス。 コマンドがで指定されたユーザーは、カテゴリを選択するときに`lstIDS`コマンドの一覧に表示されます。  
  
##  <a name="cmfcribboncustomizepropertypage"></a>CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage  
 `CMFCRibbonCustomizePropertyPage` オブジェクトを構築します。  
  
```  
CMFCRibbonCustomizePropertyPage(CMFCRibbonBar* pRibbonBar = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pRibbonBar`  
 対象のリボン コントロールへのポインターをカスタマイズするオプションです。  
  
##  <a name="onok"></a>CMFCRibbonCustomizePropertyPage::OnOK  
 ユーザーがクリックしたときに、システムによって Calleld **ok**上、**カスタマイズ** ダイアログ ボックス。  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>コメント  
 既定の実装で選択したオプションの適用、**カスタマイズ**クイック アクセス ツールバーに ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)
