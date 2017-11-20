---
title: "importlib |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.importlib
dev_langs: C++
helpviewer_keywords: importlib attribute
ms.assetid: f129e459-b8d3-4aca-a0bc-ee53e18b62ed
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 27c74785f56d7cb339eff25a645191ece1e14b32
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="importlib"></a>importlib
既に他のタイプ ライブラリでコンパイル済みの型を、作成中のタイプ ライブラリで使用できるようにします。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ importlib(  
   "tlb_file"  
) ];  
```  
  
#### <a name="parameters"></a>パラメーター  
 *tlb_file*  
 現在のプロジェクトのタイプ ライブラリにインポートする .tlb ファイルの名前 (引用符で囲む)。  
  
## <a name="remarks"></a>コメント  
 **Importlib** C++ 属性により、`importlib`ステートメントが生成された .idl ファイルのライブラリ ブロックに配置されます。 **Importlib**属性と同じ機能を持つ、 [importlib](http://msdn.microsoft.com/library/windows/desktop/aa367050) MIDL 属性。  
  
## <a name="example"></a>例  
 次のコードを使用する方法の例を示します**importlib**:  
  
```  
// cpp_attr_ref_importlib.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[importlib("importlib.tlb")];  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|任意の場所|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ属性](../windows/compiler-attributes.md)   
 [スタンドアロン属性](../windows/stand-alone-attributes.md)   
 [インポート](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [含まれます](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)