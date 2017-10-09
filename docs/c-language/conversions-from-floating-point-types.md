---
title: "浮動小数点型からの変換 | Microsoft Docs"
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
- converting floating point
- floating-point conversion
ms.assetid: 96804c8e-fa3b-4742-9006-0082ed9e57f2
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 4974edd25d0fcdd8d990b60459517bb1148c74ae
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="conversions-from-floating-point-types"></a>Conversions from Floating-Point Types (浮動小数点型からの変換)
**double** か `long double` に変換された **float** 値、または `long double` に変換される **double** は、値が変更されません。 **float** 値に変換された **double** 値は、可能であれば正確に表されます。 値を正確に表すことができない場合、精度が失われる可能性があります。 結果が範囲外の場合、動作は未定義です。 浮動小数点型の範囲については、「[浮動小数点定数の制限](../c-language/limits-on-floating-point-constants.md)」を参照してください。  
  
 浮動小数点値は、まず **long** に変換して整数値に変換され、**long** 値から特定の整数値に変換されます。 浮動小数点値の小数部分は、**long** への変換時に破棄されます。 結果が大きすぎて **long** に収まらない場合、変換の結果は未定義になります。  
  
 **Microsoft 固有の仕様**  
  
 **double** または `long double` の浮動小数点数を小さい浮動小数点数に変換して、アンダーフローが発生すると、浮動小数点変数の値はゼロに向かって切り捨てられます。 オーバーフローは実行時エラーを発生させます。 Microsoft C コンパイラは `long double` を **double** 型にマップすることに注意してください。  
  
 **END Microsoft 固有の仕様**  
  
 次の表は、浮動小数点型から変換をまとめたものです。  
  
### <a name="conversions-from-floating-point-types"></a>Conversions from Floating-Point Types (浮動小数点型からの変換)  
  
|変換前|目的|メソッド|  
|----------|--------|------------|  
|**float**|`char`|**long** への変換、**long** から `char` への変換|  
|**float**|**short**|**long** への変換、**long** から **short** への変換|  
|**float**|**long**|小数点で切り捨てます。 結果が **long** で表すには大きすぎる場合、結果は未定義になります。|  
|**float**|**unsigned short**|**long** への変換、**long** から `unsigned` **short** への変換|  
|**float**|`unsigned long`|**long** への変換、**long** から `unsigned` **long** への変換|  
|**float**|**double**|内部表現を変更します|  
|**float**|`long double`|内部表現を変更します|  
|**double**|`char`|**float** への変換、**float** から `char` への変換|  
|**double**|**short**|**float** への変換、**float** から **short** への変換|  
|**double**|**long**|小数点で切り捨てます。 結果が **long** で表すには大きすぎる場合、結果は未定義になります。|  
|**double**|**unsigned short**|**long** への変換、**long** から **unsigned short** への変換|  
|**double**|`unsigned long`|**long** への変換、**long** から `unsigned` **long** への変換|  
|**double**|**float**|**float** として表します。 **double** 値を **float** 型で正確に表すことができない場合、有効桁数が失われます。 値が **float** で表すには大きすぎる場合、結果は未定義になります。|  
|`long double`|`char`|**float** への変換、**float** から `char` への変換|  
|`long double`|**short**|**float** への変換、**float** から **short** への変換|  
|`long double`|**long**|小数点で切り捨てます。 結果が **long** で表すには大きすぎる場合、結果は未定義になります。|  
|`long double`|**unsigned short**|**long** への変換、**long** から `unsigned` **short** への変換|  
|`long double`|`unsigned long`|**long** への変換、**long** から `unsigned` **long** への変換|  
|`long double`|**float**|**float** として表します。 **double** 値を **float** 型で正確に表すことができない場合、有効桁数が失われます。 値が **float** で表すには大きすぎる場合、結果は未定義になります。|  
|`long double`|**double**|**long double** 値は **double** として扱われます。|  
  
 **float**、**double**、または `long double` 値から `unsigned long` への変換は、変換される値が **long** の正の最大値よりも大きい場合は正確ではありません。  
  
## <a name="see-also"></a>関連項目  
 [代入の変換](../c-language/assignment-conversions.md)
