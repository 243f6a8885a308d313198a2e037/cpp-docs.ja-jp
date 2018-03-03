---
title: "CMFCToolBarInfo クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo::m_uiColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuResID
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarInfo [MFC], m_uiColdResID
- CMFCToolBarInfo [MFC], m_uiDisabledResID
- CMFCToolBarInfo [MFC], m_uiHotResID
- CMFCToolBarInfo [MFC], m_uiLargeColdResID
- CMFCToolBarInfo [MFC], m_uiLargeDisabledResID
- CMFCToolBarInfo [MFC], m_uiLargeHotResID
- CMFCToolBarInfo [MFC], m_uiMenuDisabledResID
- CMFCToolBarInfo [MFC], m_uiMenuResID
ms.assetid: 6dc84482-eaaa-491f-aa5d-dd7a57886b46
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c47be3ddb2302124b233c39aaf8bd829cd481d79
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cmfctoolbarinfo-class"></a>CMFCToolBarInfo クラス
さまざまな状態のツール バー イメージのリソース ID を含みます。 `CMFCToolBarInfo`パラメーターとして使用されるヘルパー クラスには、 [CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex)メソッドです。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCToolBarInfo  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="data-members"></a>データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CMFCToolBarInfo::m_uiColdResID](#m_uicoldresid)|正規の (コールド) ツール バー イメージを含むツール バー ビットマップのリソース ID です。|  
|[CMFCToolBarInfo::m_uiDisabledResID](#m_uidisabledresid)|無効なツール バー イメージを含むツール バー ビットマップのリソース ID です。|  
|[CMFCToolBarInfo::m_uiHotResID](#m_uihotresid)|選択されている (ホット) ツール バー イメージを含むツール バー ビットマップのリソース ID です。|  
|[CMFCToolBarInfo::m_uiLargeColdResID](#m_uilargecoldresid)|通常、大規模なツール バー イメージを含むツール バー ビットマップのリソース ID。|  
|[CMFCToolBarInfo::m_uiLargeDisabledResID](#m_uilargedisabledresid)|含む大きな、ツールバーのビットマップのリソース ID には、ツール バー イメージが無効になります。|  
|[CMFCToolBarInfo::m_uiLargeHotResID](#m_uilargehotresid)|含む大きな、ツールバーのビットマップのリソース ID は、ツール バー イメージを選択します。|  
|[CMFCToolBarInfo::m_uiMenuDisabledResID](#m_uimenudisabledresid)|メニューの無効イメージを含むツール バー ビットマップのリソース ID です。|  
|[CMFCToolBarInfo::m_uiMenuResID](#m_uimenuresid)|メニュー イメージを含むツール バー ビットマップのリソース ID です。|  
  
## <a name="remarks"></a>コメント  
 完全ツールバーのビットマップは、固定サイズの小さいツール バー イメージ (ボタン) で構成されます。 格納されているそれぞれのリソース ID、`CMFCToolBarInfo`オブジェクトが (たとえば、選択した、無効な場合、大規模なまたはメニュー イメージ) の 1 つの状態のツール バー イメージの完全なセットを含むビットマップ。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CMFCToolBarInfo](../../mfc/reference/cmfctoolbarinfo-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxtoolbar.h  
  
##  <a name="m_uicoldresid"></a>CMFCToolBarInfo::m_uiColdResID  
 ツールバーのすべての標準ボタン イメージのリソース ID を指定します。  
  
```  
UINT m_uiColdResID;  
```  
  
##  <a name="m_uidisabledresid"></a>CMFCToolBarInfo::m_uiDisabledResID  
 ツールバーのボタン-利用不可のイメージのリソース ID を指定します。  
  
```  
UINT m_uiDisabledResID;  
```  
  
##  <a name="m_uihotresid"></a>CMFCToolBarInfo::m_uiHotResID  
 ツールバーのボタンの強調表示されたイメージをすべてのリソース ID を指定します。  
  
```  
UINT m_uiHotResID  
```  
  
##  <a name="m_uilargecoldresid"></a>CMFCToolBarInfo::m_uiLargeColdResID  
 ツールバーのすべての大きな標準ボタン イメージのリソース ID を指定します。  
  
```  
UINT m_uiLargeColdResID  
```  
  
##  <a name="m_uilargedisabledresid"></a>CMFCToolBarInfo::m_uiLargeDisabledResID  
 ツールバーのすべての大きな無効にされたボタン イメージのリソース ID を指定します。  
  
```  
UINT m_uiLargeDisabledResID;  
```  
  
##  <a name="m_uilargehotresid"></a>CMFCToolBarInfo::m_uiLargeHotResID  
 ツールバーの大規模なすべての強調表示されたイメージのリソース ID を指定します。  
  
```  
UINT m_uiLargeHotResID;  
```  
  
##  <a name="m_uimenudisabledresid"></a>CMFCToolBarInfo::m_uiMenuDisabledResID  
 ツールバーのコマンドにアクセスできないイメージのリソース ID を指定します。  
  
```  
UINT m_uiMenuDisabledResID;  
```  
  
##  <a name="m_uimenuresid"></a>CMFCToolBarInfo::m_uiMenuResID  
 ツールバーのすべての標準のメニュー項目イメージのリソース ID を指定します。  
  
```  
UINT m_uiMenuResID;  
```  
  
## <a name="see-also"></a>参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)
