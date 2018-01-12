---
title: "_ _interface |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: __interface_cpp
dev_langs: C++
helpviewer_keywords: __interface keyword [C++]
ms.assetid: ca5d400b-d6d8-4ba2-89af-73f67e5ec056
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6fc53310c492c424c3d97aecec965ba03553dd8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="interface"></a>__interface
**Microsoft 固有の仕様**  
  
 Visual C++ インターフェイスは次のように定義できます。  
  
-   0 個以上の基底インターフェイスから継承できます。  
  
-   基底クラスから継承することはできません。  
  
-   パブリックな純粋仮想メソッドのみを含めることができます。  
  
-   コンストラクター、デストラクター、または演算子を含めることはできません。  
  
-   静的メソッドを含めることはできません。  
  
-   データ メンバーを含めることはできません。プロパティは使用できます。  
  
## <a name="syntax"></a>構文  
  
```  
  
modifier  
 __interface interface-name {interface-definition};  
```  
  
## <a name="remarks"></a>コメント  
 C++[クラス](../cpp/class-cpp.md)または[構造体](../cpp/struct-cpp.md)これらの規則に、実装する可能性がありますが、`__interface`はこれらを強制します。  
  
 次にインターフェイスの定義例を示します。  
  
```  
__interface IMyInterface {  
   HRESULT CommitX();  
   HRESULT get_X(BSTR* pbstrName);  
};  
```  
  
 詳細については、マネージ インターフェイスは、次を参照してください。[インターフェイス クラス](../windows/interface-class-cpp-component-extensions.md)です。  
  
 `CommitX` 関数と `get_X` 関数が純粋仮想関数であることを明示的に示す必要がないことに注意してください。 最初の関数の同等の宣言は次のとおりです。  
  
```  
virtual HRESULT CommitX() = 0;  
```  
  
 `__interface`意味、 [novtable](../cpp/novtable.md) `__declspec`修飾子です。  
  
## <a name="example"></a>例  
 次の例では、インターフェイスで宣言されたプロパティを使用する方法を示します。  
  
```  
// deriv_interface.cpp  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
#include <string.h>  
#include <comdef.h>  
#include <stdio.h>  
  
[module(name="test")];  
  
[ object, uuid("00000000-0000-0000-0000-000000000001"), library_block ]  
__interface IFace {  
   [ id(0) ] int int_data;  
   [ id(5) ] BSTR bstr_data;  
};  
  
[ coclass, uuid("00000000-0000-0000-0000-000000000002") ]  
class MyClass : public IFace {  
private:  
    int m_i;  
    BSTR m_bstr;   
  
public:  
    MyClass()  
    {  
        m_i = 0;  
        m_bstr = 0;  
    }  
  
    ~MyClass()  
    {  
        if (m_bstr)   
            ::SysFreeString(m_bstr);  
    }  
  
    int get_int_data()  
    {  
        return m_i;  
    }  
  
    void put_int_data(int _i)   
    {  
        m_i = _i;  
    }  
  
    BSTR get_bstr_data()  
    {   
        BSTR bstr = ::SysAllocString(m_bstr);  
        return bstr;   
    }  
  
    void put_bstr_data(BSTR bstr)   
    {   
        if (m_bstr)   
            ::SysFreeString(m_bstr);  
        m_bstr = ::SysAllocString(bstr);  
    }  
};  
  
int main()  
{  
    _bstr_t bstr("Testing");  
    CoInitialize(NULL);  
    CComObject<MyClass>* p;  
    CComObject<MyClass>::CreateInstance(&p);  
    p->int_data = 100;  
    printf_s("p->int_data = %d\n", p->int_data);                
    p->bstr_data = bstr;  
    printf_s("bstr_data = %S\n", p->bstr_data);  
}  
```  
  
```Output  
p->int_data = 100  
bstr_data = Testing  
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [キーワード](../cpp/keywords-cpp.md)   
 [インターフェイス属性](../windows/interface-attributes.md)