---
title: "C 拡張ストレージ クラス属性 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C]
- extended attributes
- extended storage-class attributes
- storage class specifiers, C storage classes
ms.assetid: 2580735c-f5bf-46ab-9468-0696893d82be
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 972a8dc27283839ce1eade0e1e9b81dc92998b15
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="c-extended-storage-class-attributes"></a>C 拡張ストレージ クラス属性
**Microsoft 固有の仕様**  
  
 このトピックの最新情報は、[__declspec (C++ リファレンス)](../cpp/declspec.md) に関するページをご覧ください。  
  
 拡張属性構文は、Microsoft 固有の C 言語拡張機能を簡略化し、標準化します。 拡張属性構文を使用するストレージ クラス属性には、thread、naked、dllimport、dllexport があります。  
  
 ストレージ クラス情報を指定するための拡張属性構文は、__declspec キーワードを使用します。これは、指定された型のインスタンスを、Microsoft 固有のストレージ クラス属性 (thread、naked、dllimport、または dllexport) で保存することを指定します。 他のストレージ クラス修飾子の例としては、static および extern キーワードがあります。 ただし、これらのキーワードは ANSI C 規格の一部であるため、拡張属性構文では扱われません。  
  
## <a name="syntax"></a>構文  
 *storage-class-specifier*:  
 `__declspec` ( *extended-decl-modifier-seq* ) /* Microsoft 固有の仕様 \*/  
  
 *extended-decl-modifier-seq*:  
 *extended-decl-modifier* opt  
  
 *extended-decl-modifier-seq extended-decl-modifier*  
  
 *extended-decl-modifier*:  
 **thread**  
  
 **naked**  
  
 **dllimport**  
  
 `dllexport`  
  
 空白は、宣言修飾子を区切ります。 *extended-decl-modifier-seq* は空にできます。この場合、__declspec は無効になります。  
  
 thread、naked、dllimport、および dllexport ストレージ クラス属性は、適用先のデータまたは関数を宣言するだけのプロパティです。関数自体の型属性は再定義しません。 thread 属性はデータだけに影響します。 naked 属性は関数だけに影響します。 dllimport 属性と dllexport 属性は関数とデータに影響します。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [宣言と型](../c-language/declarations-and-types.md)