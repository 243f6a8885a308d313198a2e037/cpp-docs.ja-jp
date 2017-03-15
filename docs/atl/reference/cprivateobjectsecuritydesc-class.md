---
title: "CPrivateObjectSecurityDesc クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CPrivateObjectSecurityDesc
- ATL::CPrivateObjectSecurityDesc
- CPrivateObjectSecurityDesc
dev_langs:
- C++
helpviewer_keywords:
- CPrivateObjectSecurityDesc class
ms.assetid: 2c4bbb13-bf99-4833-912a-197f6815bb5d
caps.latest.revision: 20
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 154a4229f8963d3081e6e0518354d17968ee0e20
ms.lasthandoff: 02/24/2017

---
# <a name="cprivateobjectsecuritydesc-class"></a>CPrivateObjectSecurityDesc クラス
このクラスは、プライベート オブジェクトのセキュリティ記述子オブジェクトを表します。  
  
## <a name="syntax"></a>構文  
  
```
class CPrivateObjectSecurityDesc : public CSecurityDesc
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc](#cprivateobjectsecuritydesc)|コンストラクターです。|  
|[CPrivateObjectSecurityDesc:: ~ CPrivateObjectSecurityDesc](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPrivateObjectSecurityDesc::ConvertToAutoInherit](#converttoautoinherit)|セキュリティ記述子とそのアクセス制御リスト (Acl) を継承可能なアクセス制御エントリ (Ace) の自動適用をサポートする形式に変換するには、このメソッドを呼び出します。|  
|[CPrivateObjectSecurityDesc::Create](#create)|割り当ておよび呼び出し元のリソース マネージャーによって作成されるプライベート オブジェクトの自己相対セキュリティ記述子を初期化するには、このメソッドを呼び出します。|  
|[CPrivateObjectSecurityDesc::Get](#get)|このメソッドでは、プライベート オブジェクトのセキュリティ記述子から情報を取得します。|  
|[CPrivateObjectSecurityDesc::Set](#set)|プライベート オブジェクトのセキュリティ記述子を変更するには、このメソッドを呼び出します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 =](#operator_eq)|代入演算子。|  
  
## <a name="remarks"></a>コメント  
 このクラスから派生[CSecurityDesc](../../atl/reference/csecuritydesc-class.md)を作成して、プライベート オブジェクトのセキュリティ記述子を管理するメソッドを提供します。  
  
 Windows のアクセス制御モデルの概要については、次を参照してください。[アクセス制御](http://msdn.microsoft.com/library/windows/desktop/aa374860)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md)  
  
 `CPrivateObjectSecurityDesc`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h  
  
##  <a name="a-nameconverttoautoinherita--cprivateobjectsecuritydescconverttoautoinherit"></a><a name="converttoautoinherit"></a>CPrivateObjectSecurityDesc::ConvertToAutoInherit  
 セキュリティ記述子とそのアクセス制御リスト (Acl) を継承可能なアクセス制御エントリ (Ace) の自動適用をサポートする形式に変換するには、このメソッドを呼び出します。  
  
```
bool ConvertToAutoInherit(  
    const CSecurityDesc* pParent,
    GUID* ObjectType,
    bool bIsDirectoryObject,
    PGENERIC_MAPPING GenericMapping) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pParent`  
 ポインター、 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md)オブジェクトの親コンテナーを参照するオブジェクト。 親コンテナーがない場合は、このパラメーターは NULL です。  
  
 `ObjectType`  
 ポインター、 **GUID**現在のオブジェクトに関連付けられているオブジェクトの種類を識別する構造体。 設定`ObjectType`オブジェクトには、GUID がない場合は NULL にします。  
  
 `bIsDirectoryObject`  
 新しいオブジェクトが他のオブジェクトを含めるかどうかを指定します。 True の値は、新しいオブジェクトがコンテナーであることを示します。 False の値は、新しいオブジェクトがコンテナーではないことを示します。  
  
 `GenericMapping`  
 ポインター、 [GENERIC_MAPPING](http://msdn.microsoft.com/library/windows/desktop/aa446633)をオブジェクトに特定の権限に各ジェネリック右からマッピングを指定します。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドが随意アクセス制御の Ace が (DACL) を一覧表示するかどうかを決定しようと現在のセキュリティ記述子のシステム アクセス制御リスト (SACL) は、親のセキュリティ記述子から継承されました。 呼び出す、 [ConvertToAutoInheritPrivateObjectSecurity](http://msdn.microsoft.com/library/windows/desktop/aa376403)関数です。  
  
##  <a name="a-namecprivateobjectsecuritydesca--cprivateobjectsecuritydesccprivateobjectsecuritydesc"></a><a name="cprivateobjectsecuritydesc"></a>CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc  
 コンストラクターです。  
  
```
CPrivateObjectSecurityDesc() throw();
```  
  
### <a name="remarks"></a>コメント  
 初期化、`CPrivateObjectSecurityDesc`オブジェクトです。  
  
##  <a name="a-namedtora--cprivateobjectsecuritydesccprivateobjectsecuritydesc"></a><a name="dtor"></a>CPrivateObjectSecurityDesc:: ~ CPrivateObjectSecurityDesc  
 デストラクターです。  
  
```
~CPrivateObjectSecurityDesc() throw();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターは、割り当てられているすべてのリソースを解放し、プライベート オブジェクトのセキュリティ記述子を削除します。  
  
##  <a name="a-namecreatea--cprivateobjectsecuritydesccreate"></a><a name="create"></a>CPrivateObjectSecurityDesc::Create  
 割り当ておよび呼び出し元のリソース マネージャーによって作成されるプライベート オブジェクトの自己相対セキュリティ記述子を初期化するには、このメソッドを呼び出します。  
  
```
bool Create(  
    const CSecurityDesc* pParent,
    const CSecurityDesc* pCreator,
    bool bIsDirectoryObject,
    const CAccessToken& Token,
    PGENERIC_MAPPING GenericMapping) throw();

bool Create(  
    const CSecurityDesc* pParent,
    const CSecurityDesc* pCreator,
    GUID* ObjectType,
    bool bIsContainerObject,
    ULONG AutoInheritFlags,
    const CAccessToken& Token,
    PGENERIC_MAPPING GenericMapping) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pParent`  
 ポインター、 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md)新しいオブジェクトを作成する親ディレクトリを参照するオブジェクト。 親ディレクトリが存在しない場合は NULL に設定します。  
  
 `pCreator`  
 オブジェクトの作成者によって提供されるセキュリティ記述子へのポインター。 オブジェクトの作成者が明示的に新しいオブジェクトのセキュリティ情報を渡さない場合は、このパラメーターを NULL に設定します。  
  
 `bIsDirectoryObject`  
 新しいオブジェクトが他のオブジェクトを含めるかどうかを指定します。 True の値は、新しいオブジェクトがコンテナーであることを示します。 False の値は、新しいオブジェクトがコンテナーではないことを示します。  
  
 `Token`  
 参照、 [CAccessToken](../../atl/reference/caccesstoken-class.md)オブジェクトの作成対象のクライアント プロセスのオブジェクト。  
  
 `GenericMapping`  
 ポインター、 [GENERIC_MAPPING](http://msdn.microsoft.com/library/windows/desktop/aa446633)をオブジェクトに特定の権限に各ジェネリック右からマッピングを指定します。  
  
 `ObjectType`  
 ポインター、 **GUID**現在のオブジェクトに関連付けられているオブジェクトの種類を識別する構造体。 設定`ObjectType`オブジェクトには、GUID がない場合は NULL にします。  
  
 *bIsContainerObject*  
 新しいオブジェクトが他のオブジェクトを含めるかどうかを指定します。 True の値は、新しいオブジェクトがコンテナーであることを示します。 False の値は、新しいオブジェクトがコンテナーではないことを示します。  
  
 `AutoInheritFlags`  
 アクセス制御エントリ (Ace) を継承する方法を制御するビット フラグのセット`pParent`します。 参照してください[CreatePrivateObjectSecurityEx](http://msdn.microsoft.com/library/windows/desktop/aa446581)詳細です。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出す[CreatePrivateObjectSercurity](http://msdn.microsoft.com/library/windows/desktop/aa376405)または[CreatePrivateObjectSecurityEx](http://msdn.microsoft.com/library/windows/desktop/aa446581)します。  
  
 2 番目のメソッド、または許可する新しいオブジェクトのオブジェクトの種類の GUID を指定する Ace の継承の制御のみ以降 Windows 2000 を実行するシステムで利用できます。  
  
> [!NOTE]
>  自己相対セキュリティ記述子は、連続するメモリ ブロックにすべてのセキュリティ情報を格納するセキュリティ記述子です。  
  
##  <a name="a-namegeta--cprivateobjectsecuritydescget"></a><a name="get"></a>CPrivateObjectSecurityDesc::Get  
 このメソッドでは、プライベート オブジェクトのセキュリティ記述子から情報を取得します。  
  
```
bool Get(  
    SECURITY_INFORMATION si,
    CSecurityDesc* pResult) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `si`  
 取得するセキュリティ記述子の部分を指定するビット フラグのセット。 この値は、組み合わせて使用できますが、 [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573)ビット フラグです。  
  
 `pResult`  
 ポインター、 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md)を指定したセキュリティ記述子から、必要な情報のコピーを受け取るオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 セキュリティ記述子には、構造と関連データがセキュリティ保護可能なオブジェクトのセキュリティ情報が含まれています。  
  
##  <a name="a-nameoperatoreqa--cprivateobjectsecuritydescoperator-"></a><a name="operator_eq"></a>CPrivateObjectSecurityDesc::operator =  
 代入演算子。  
  
```
CPrivateObjectSecurityDesc& operator= (const CPrivateObjectSecurityDesc& rhs) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `rhs`  
 `CPrivateObjectSecurityDesc`現在のオブジェクトに割り当てるオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 取得、更新された`CPrivateObjectSecurityDesc`オブジェクトです。  
  
##  <a name="a-nameseta--cprivateobjectsecuritydescset"></a><a name="set"></a>CPrivateObjectSecurityDesc::Set  
 プライベート オブジェクトのセキュリティ記述子を変更するには、このメソッドを呼び出します。  
  
```
bool Set(  
    SECURITY_INFORMATION si,
    const CSecurityDesc& Modification,
    PGENERIC_MAPPING GenericMapping,
    const CAccessToken& Token) throw();

bool Set(  
    SECURITY_INFORMATION si,
    const CSecurityDesc& Modification,
    ULONG AutoInheritFlags,
    PGENERIC_MAPPING GenericMapping,
    const CAccessToken& Token) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `si`  
 設定するセキュリティ記述子の部分を指定するビット フラグのセット。 この値は、組み合わせて使用できますが、 [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573)ビット フラグです。  
  
 *変更*  
 ポインター、 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md)オブジェクトです。 このセキュリティ記述子の一部が示される、`si`パラメーターは、オブジェクトのセキュリティ記述子に適用されます。  
  
 `GenericMapping`  
 ポインター、 [GENERIC_MAPPING](http://msdn.microsoft.com/library/windows/desktop/aa446633)をオブジェクトに特定の権限に各ジェネリック右からマッピングを指定します。  
  
 `Token`  
 参照、 [CAccessToken](../../atl/reference/caccesstoken-class.md)オブジェクトの作成対象のクライアント プロセスのオブジェクト。  
  
 `AutoInheritFlags`  
 アクセス制御エントリ (Ace) を継承する方法を制御するビット フラグのセット`pParent`します。 参照してください[CreatePrivateObjectSecurityEx](http://msdn.microsoft.com/library/windows/desktop/aa446581)詳細です。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は true を返します。失敗した場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 2 番目のメソッド、または許可するオブジェクトのオブジェクトの種類の GUID を指定する Ace の継承の制御のみ以降 Windows 2000 を実行するシステムで利用できます。  
  
## <a name="see-also"></a>関連項目  
 [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [セキュリティに関するグローバル関数](../../atl/reference/security-global-functions.md)   
 [CSecurityDesc クラス](../../atl/reference/csecuritydesc-class.md)

