---
title: "&lt;system_error&gt; 演算子 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- system_error/std::operator!=
- system_error/std::operator==
dev_langs:
- C++
ms.assetid: c14edefb-bd8a-4e90-88d3-c59c98e6f73c
caps.latest.revision: 11
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: ed01a5abeb54f5071968555b563849e2cd4ac1af
ms.contentlocale: ja-jp
ms.lasthandoff: 10/03/2017

---
# <a name="ltsystemerrorgt-operators"></a>&lt;system_error&gt; 演算子
||||  
|-|-|-|  
|[operator!=](#op_neq)|[operator&lt;](#op_lt)|[operator==](#op_eq_eq)|  
  
##  <a name="op_eq_eq"></a>  operator==  
 演算子の左側のオブジェクトが右側のオブジェクトと等しいかどうかを調べます。  
  
```
bool operator==(const error_code& left,
    const error_condition& right);

bool operator==(const error_condition& left,
    const error_code& right);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`left`|等しいかどうかをテストするオブジェクト。|  
|`right`|等しいかどうかをテストするオブジェクト。|  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが等しい場合は **true**、オブジェクトが等しくない場合は **false**。  
  
### <a name="remarks"></a>コメント  
 この関数は `left.category() == right.category() && left.value() == right.value()` を返します。  
  
##  <a name="op_neq"></a>  operator!=  
 演算子の左側のオブジェクトが右側のオブジェクトと等しくないかどうかを調べます。  
  
```
bool operator!=(const error_code& left,
    const error_condition& right);

bool operator!=(const error_condition& left,
    const error_code& right);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`left`|不等性をテストするオブジェクト。|  
|`right`|不等性をテストするオブジェクト。|  
  
### <a name="return-value"></a>戻り値  
 `left` で渡されるオブジェクトが `right` で渡されるオブジェクトと等しくない場合は **true**、それ以外の場合は **false**。  
  
### <a name="remarks"></a>コメント  
 この関数は `!(left == right)` を返します。  
  
##  <a name="op_lt"></a>  operator&lt;  
 オブジェクトが比較のために渡されるオブジェクトより小さいかどうかをテストします。  
  
```
template <class _Enum>  
inline bool operator<(
    _Enum left,
    typename enable_if<is_error_code_enum<_Enum>::value,
    const error_code&>::type right);

template <class _Enum>  
inline bool operator<(
    typename enable_if<is_error_code_enum<_Enum>::value,
    const error_code&>::type left, _Enum right);

template <class _Enum>  
inline bool operator<(
    _Enum left,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    const error_condition&>::type right);

template <class _Enum>  
inline bool operator<(
    typename enable_if<is_error_condition_enum<_Enum>::value,
    const error_condition&>::type left, _Enum right);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`left`|比較されるオブジェクト。|  
|`right`|比較されるオブジェクト。|  
  
### <a name="return-value"></a>戻り値  
 `left` で渡されるオブジェクトが `right` で渡されるオブジェクトより小さい場合は **true**、それ以外の場合は **false**。  
  
### <a name="remarks"></a>コメント  
 この関数はエラー順序をテストします。  
  
## <a name="see-also"></a>関連項目  
 [<system_error>](../standard-library/system-error.md)




