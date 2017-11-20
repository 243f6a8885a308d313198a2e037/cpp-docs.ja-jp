---
title: "ITopologyNode 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ITopologyNode
- CONCRTRM/concurrency::ITopologyNode
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetExecutionResourceCount
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetFirstExecutionResource
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetId
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNext
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNumaNode
dev_langs: C++
helpviewer_keywords: ITopologyNode structure
ms.assetid: 92e7e032-04f6-4c7c-be36-8f9a35fc4734
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1b2c53761a47162e3dae17a1447612d2e16fe16c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="itopologynode-structure"></a>ITopologyNode 構造体
リソース マネージャーで定義されるトポロジ ノードへのインターフェイスです。 ノードには 1 つ以上の実行リソースが含まれます。  
  
## <a name="syntax"></a>構文  
  
```
struct ITopologyNode;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Itopologynode::getexecutionresourcecount](#getexecutionresourcecount)|このノードでグループ化の実行リソースの数を返します。|  
|[Itopologynode::getfirstexecutionresource](#getfirstexecutionresource)|列挙の順番にこのノードの下にグループ化の最初の実行リソースを返します。|  
|[Itopologynode::getid](#getid)|このノードのリソース マネージャーの一意の識別子を返します。|  
|[Itopologynode::getnext](#getnext)|列挙の順番に次のトポロジのノードにインターフェイスを返します。|  
|[Itopologynode::getnumanode](#getnumanode)|Windows が割り当てた、このリソース マネージャー ノードが属する、NUMA ノードの数を返します。|  
  
## <a name="remarks"></a>コメント  
 このインターフェイスは、通常使用率が低いリソース マネージャーで見られるように、システムのトポロジのすべての要素。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ITopologyNode`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="getexecutionresourcecount"></a>Itopologynode::getexecutionresourcecount メソッド  
 このノードでグループ化の実行リソースの数を返します。  
  
```
virtual unsigned int GetExecutionResourceCount() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 実行のリソースの数は、このノードの下にグループ化。  
  
##  <a name="getfirstexecutionresource"></a>Itopologynode::getfirstexecutionresource メソッド  
 列挙の順番にこのノードの下にグループ化の最初の実行リソースを返します。  
  
```
virtual ITopologyExecutionResource *GetFirstExecutionResource() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 列挙の順番にこのノードの下の最初の実行リソースがグループ化されます。  
  
##  <a name="getid"></a>Itopologynode::getid メソッド  
 このノードのリソース マネージャーの一意の識別子を返します。  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 このノードのリソース マネージャーの一意の識別子。  
  
### <a name="remarks"></a>コメント  
 同時実行ランタイムでは、プロセッサのノードのグループでは、システム上のハードウェア スレッドを表します。 通常、ノードは、システムのハードウェア トポロジから派生します。 たとえば、特定のソケットまたは特定の NUMA ノード上のすべてのプロセッサが同一プロセッサ ノードに属している可能性があります。 リソース マネージャーは、以降でこれらのノードに一意の識別子を割り当てます`0`含む`nodeCount - 1`ここで、`nodeCount`システム上のノードのプロセッサの合計数を表します。  
  
 ノードの数は、関数から取得できる[GetProcessorNodeCount](concurrency-namespace-functions.md)です。  
  
##  <a name="getnext"></a>Itopologynode::getnext メソッド  
 列挙の順番に次のトポロジのノードにインターフェイスを返します。  
  
```
virtual ITopologyNode *GetNext() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 列挙の順番に次のノードへのインターフェイス。 このメソッドが値を返す場合はノードが存在しない複数システム トポロジの列挙の順番に、`NULL`です。  
  
##  <a name="getnumanode"></a>Itopologynode::getnumanode メソッド  
 Windows が割り当てた、このリソース マネージャー ノードが属する、NUMA ノードの数を返します。  
  
```
virtual unsigned long GetNumaNode() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 Windows が割り当てた、このリソース マネージャー ノードが属する、NUMA ノードの数。  
  
### <a name="remarks"></a>コメント  
 このノードに属する仮想プロセッサ ルートで実行中のスレッド プロキシは、このメソッドが返す NUMA ノードに、少なくとも NUMA ノードのレベルで関係があります。  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)
