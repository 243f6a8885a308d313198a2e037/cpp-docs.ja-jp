---
title: "コクラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.coclass
dev_langs:
- C++
helpviewer_keywords:
- coclass attribute
ms.assetid: 42da6a10-3af9-4b43-9a1d-689d00b61eb3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6bcae762c603f05ce11eae5d14eb2e182c666797
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="coclass"></a>coclass
COM インターフェイスを実装する COM オブジェクトを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
  
[coclass]  
  
```  
  
## <a name="remarks"></a>コメント  
 **コクラス**C++ 属性は、生成された .idl ファイル内のコクラス構成要素を配置します。  
  
 コクラスを定義するときに指定することも、 [uuid](../windows/uuid-cpp-attributes.md)、[バージョン](../windows/version-cpp.md)、[スレッド](../windows/threading-cpp.md)、 [vi_progid](../windows/vi-progid.md)、および[progid](../windows/progid.md)属性。 いずれかのファイルが指定されていない場合それが生成されます。  
  
 2 つのヘッダー ファイルを持つクラスが含まれている場合、**コクラス**属性を GUID を指定しない、コンパイラは両方のクラスに対して、同じ GUID を使用し、MIDL のエラーが発生します。  したがって、使用する必要があります、`uuid`属性を使用するときに**コクラス**です。  
  
 **ATL プロジェクト**  
  
 この属性は、ATL プロジェクトでは、クラスまたは構造体の定義を前に。  
  
-   コードまたはオブジェクトの自動登録をサポートするためにデータを挿入します。  
  
-   コードまたはオブジェクトの COM クラス ファクトリをサポートするためにデータを挿入します。  
  
-   コードまたは実装するデータが挿入**IUnknown**と COM で作成可能オブジェクトのオブジェクトを作成します。  
  
 具体的には、次の基本クラスは、ターゲット オブジェクトに追加されます。  
  
-   [CComCoClass クラス](../atl/reference/ccomcoclass-class.md)オブジェクトの既定のクラス ファクトリと集計モデルを提供します。  
  
-   [CComObjectRootEx クラス](../atl/reference/ccomobjectrootex-class.md)によって指定されたスレッド処理モデル クラスに基づくテンプレートを持つ、[スレッド](../windows/threading-cpp.md)属性。 場合、**スレッド**属性が指定されていない、既定のスレッド モデルがアパートメントです。  
  
-   [IProvideClassInfo2Impl](../atl/reference/iprovideclassinfo2impl-class.md)場合は、追加、 [noncreatable](../windows/noncreatable.md)ターゲット オブジェクトの属性が指定されていません。  
  
 最後に、埋め込み IDL で定義されていない任意のデュアル インターフェイスが置き換えられます、対応する[IDispatchImpl](../atl/reference/idispatchimpl-class.md)クラスです。 デュアル インターフェイスが埋め込み IDL で定義されている場合は、基底のリストに特定のインターフェイスは変更されません。  
  
 **コクラス**属性も使用可能、次の関数の場合または挿入されたコードを使用して`GetObjectCLSID`、基本クラスの静的メソッドとして`CComCoClass`:  
  
-   `UpdateRegistry`ターゲット クラスのクラス ファクトリを登録します。  
  
-   `GetObjectCLSID`、、登録に関連することもできますをターゲット クラスの CLSID を取得します。  
  
-   **GetObjectFriendlyName**既定の形式の文字列が返されます"\<*対象のクラス名*> `Object`"です。 この関数が既に存在する場合は追加されません。 この関数を自動的に生成されたものよりもわかりやすい名を返す対象クラスに追加します。  
  
-   **GetProgID**、登録に関連すると指定した文字列を返します、 [progid](../windows/progid.md)属性。  
  
-   **GetVersionIndependentProgID**と同じ機能を持つ**GetProgID**で指定された文字列を返しますが、 [vi_progid](../windows/vi-progid.md)です。  
  
 対象のクラスには、COM マップに関連する、次の変更が行われました。  
  
-   COM マップが追加され、すべてのインターフェイスのターゲット クラスの派生元のエントリとで指定されたすべてのエントリが、 [COM インターフェイス エントリ ポイント](../mfc/com-interface-entry-points.md)属性またはで必要な[集計](../windows/aggregates.md)属性。  
  
-   [OBJECT_ENTRY_AUTO](../atl/reference/object-map-macros.md#object_entry_auto)マクロは、COM マップに挿入します。
  
 クラスの .idl ファイル内に生成されるコクラスの名前は、クラスと同じ名前になります。  たとえばと次の例を参照する、MIDL によって生成されたヘッダー ファイルを使用して、クライアントで CMyClass、コクラスのクラス ID にアクセスする CLSID_CMyClass を使用します。  
  
## <a name="example"></a>例  
 次のコードを使用する方法を示しています、**コクラス**属性。  
  
```  
// cpp_attr_ref_coclass1.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[ object, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface I {  
   HRESULT func();  
};  
  
[coclass, progid("MyCoClass.coclass.1"), vi_progid("MyCoClass.coclass"),   
appobject, uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")]  
class CMyClass : public I {};  
```  
  
 次の例は、によって挿入されたコードに表示される関数の既定の実装をオーバーライドする方法を示します、**コクラス**属性。 挿入されたコードを参照する方法の詳細については、「 [/Fx](../build/reference/fx-merge-injected-code.md) 」を参照してください。 すべての基底クラスまたはインターフェイス クラスを使用することは、挿入されたコードに表示されます。   さらに、挿入されたコードで既定では、クラスが含まれている、明示的に指定するクラスをベースとして、コクラスの場合は、属性プロバイダーは、コードで指定されたフォームを使用します。  
  
```  
// cpp_attr_ref_coclass2.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlwin.h>  
#include <atltypes.h>  
#include <atlctl.h>  
#include <atlhost.h>  
#include <atlplus.h>  
  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000000")]  
__interface bb {};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000001")]  
class CMyClass : public bb {  
public:  
   // by adding the definition of UpdateRegistry to your code,   
   // the function will not be included in the injected code  
   static HRESULT WINAPI UpdateRegistry(BOOL bRegister) {  
      // you can add to the default implementation  
      CRegistryVirtualMachine rvm;  
      HRESULT hr;  
      if (FAILED(hr = rvm.AddStandardReplacements()))  
         return hr;  
      rvm.AddReplacement(_T("FriendlyName"), GetObjectFriendlyName());  
      return rvm.VMUpdateRegistry(GetOpCodes(), GetOpcodeStringVals(),  
         GetOpcodeDWORDVals(), GetOpcodeBinaryVals(), bRegister);  
   }  
};  
```  
  
## <a name="requirements"></a>必要条件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**class**、 `struct`|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [IDL 属性](../windows/idl-attributes.md)   
 [COM 属性](../windows/com-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [appobject](../windows/appobject.md)