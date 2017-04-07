---
title: "クラスの関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSingleDocTemplate
- AFXWIN/CSingleDocTemplate
- AFXWIN/CSingleDocTemplate::CSingleDocTemplate
dev_langs:
- C++
helpviewer_keywords:
- templates, SDI
- document templates, single
- single document interface (SDI), applications
- CSingleDocTemplate class
ms.assetid: 4f3a8212-81ee-48a0-ad22-e0ed7c36a391
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
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 78e288dd958e73495a8d513d7fe3427ccc956a61
ms.lasthandoff: 02/24/2017

---
# <a name="csingledoctemplate-class"></a>関数のクラス
SDI (シングル ドキュメント インターフェイス) を実装するドキュメント テンプレートを定義します。  
  
## <a name="syntax"></a>構文  
  
```  
class CSingleDocTemplate : public CDocTemplate  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSingleDocTemplate::CSingleDocTemplate](#csingledoctemplate)|`CSingleDocTemplate` オブジェクトを構築します。|  
  
## <a name="remarks"></a>コメント  
 SDI アプリケーションでは、メイン フレーム ウィンドウを使ってドキュメントを表示するには1 つのドキュメントは、一度に開くことができます。  
  
 ドキュメント テンプレートには、3 種類のクラス間のリレーションシップを定義します。  
  
-   派生するドキュメント クラス**CDocument**します。  
  
-   ビュー クラス上に示したドキュメント クラスからのデータが表示されます。 このクラスから派生できます`CView`、 `CScrollView`、 `CFormView`、または`CEditView`です。 (使用することも`CEditView`直接)。  
  
-   ビューを含むフレーム ウィンドウ クラスです。 SDI のドキュメント テンプレートからこのクラスを派生できます`CFrameWnd`フレーム ウィンドウのかどうかは、メインの動作をカスタマイズする必要はありません。 使用すると、`CFrameWnd`独自のクラスを派生させることなく直接します。  
  
 SDI アプリケーションでサポートの種類のドキュメントを&1; つだけがあるため`CSingleDocTemplate`オブジェクトです。 1 つのドキュメントは、一度に開くことができます。  
  
 すべてのメンバーの関数を呼び出すことがなくても`CSingleDocTemplate`コンス トラクターを除きます。 Framework ハンドル`CSingleDocTemplate`オブジェクトを内部的にします。  
  
 使用する方法について`CSingleDocTemplate`を参照してください[ドキュメント テンプレートとドキュメント/ビューの作成手順](../../mfc/document-templates-and-the-document-view-creation-process.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CSingleDocTemplate`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="csingledoctemplate"></a>CSingleDocTemplate::CSingleDocTemplate  
 `CSingleDocTemplate` オブジェクトを構築します。  
  
```  
CSingleDocTemplate(
    UINT nIDResource,  
    CRuntimeClass* pDocClass,  
    CRuntimeClass* pFrameClass,  
    CRuntimeClass* pViewClass);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDResource`  
 ドキュメントの種類に使用されているリソースの ID を指定します。 これには、メニューのアイコン、アクセラレータ テーブル、および文字列リソースが含まれます。  
  
 文字列リソースは、"\n"文字で区切られた最大&7; つの部分文字列で構成されます (部分文字列が含まれていない場合は、プレース ホルダーとして"\n"文字が必要。 ただし、末尾の"\n"文字は必要ありません) です。これらの部分文字列では、ドキュメントの種類について説明します。 部分文字列の詳細については、次を参照してください。 [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring)します。 アプリケーションのリソース ファイルでは、この文字列リソースが見つかります。 例:  
  
 `// MYCALC.RC`  
  
 `STRINGTABLE PRELOAD DISCARDABLE`  
  
 `BEGIN`  
  
 `IDR_MAINFRAME "MyCalc Windows Application\nSheet\nWorksheet\n Worksheets (*.myc)\n.myc\nMyCalcSheet\n MyCalc Worksheet"`  
  
 `END`  
  
 ストリング エディターを使用してこの文字列を編集することができます。文字列全体は、7 つの別のエントリとしてではなく文字列エディターで、1 つのエントリとして表示されます。  
  
 これらのリソースの種類の詳細については、次を参照してください。、[ストリング エディター](../../windows/string-editor.md)します。  
  
 `pDocClass`  
 指す、`CRuntimeClass`ドキュメント クラスのオブジェクト。 このクラスは、 **CDocument**-には、ドキュメントを表すために定義するクラスを派生します。  
  
 `pFrameClass`  
 指す、`CRuntimeClass`フレーム ウィンドウ クラスのオブジェクト。 このクラスを指定できます、`CFrameWnd`の派生クラス、または実行できます`CFrameWnd`自体のメイン フレーム ウィンドウの既定の動作をする場合。  
  
 `pViewClass`  
 指す、`CRuntimeClass`ビュー クラスのオブジェクト。 このクラスは、 `CView`-には、ドキュメントを表示するように定義するクラスを派生します。  
  
### <a name="remarks"></a>コメント  
 動的に割り当てる、`CSingleDocTemplate`オブジェクトに渡すと`CWinApp::AddDocTemplate`から、`InitInstance`アプリケーション クラスのメンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocViewSDI&#13;](../../mfc/codesnippet/cpp/csingledoctemplate-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocViewSDI&#14;](../../mfc/codesnippet/cpp/csingledoctemplate-class_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル DOCKTOOL](../../visual-cpp-samples.md)   
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)   
 [CDocument クラス](../../mfc/reference/cdocument-class.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)   
 [CMultiDocTemplate クラス](../../mfc/reference/cmultidoctemplate-class.md)   
 [CView クラス](../../mfc/reference/cview-class.md)   
 [CWinApp クラス](../../mfc/reference/cwinapp-class.md)

