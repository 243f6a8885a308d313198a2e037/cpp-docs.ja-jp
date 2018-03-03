---
title: "明示的なオーバーライド (C++ コンポーネント拡張) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- overriding, override [C++]
ms.assetid: 4ec3eaf5-163b-4df8-8f16-7a2ec04c3d0f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 346dd73952934d514b2741c41d5a27816b7152ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="explicit-overrides--c-component-extensions"></a>明示的なオーバーライド (C++ Component Extensions)
このトピックでは、基底クラスまたはインターフェイスのメンバーを明示的にオーバーライドする方法について説明します。 (明示的な) 名前付きオーバーライドを別の名前を持つ派生メソッドでメソッドをオーバーライドする場合にのみ使用する必要があります。  
  
## <a name="all-runtimes"></a>すべてのランタイム  
 **構文**  
  
```  
  
      overriding-function-declarator = type::function [,type::function] { overriding-function-definition }  
overriding-function-declarator = function { overriding-function-definition }  
```  
  
 **パラメーター**  
  
 *オーバーライドする関数の宣言子*  
 オーバーライド関数の戻り値の型、名、および引数リスト。  オーバーライドされる関数と同じ名前に設定をオーバーライドする関数がないことに注意してください。  
  
 *type*  
 基本データ型をオーバーライドする関数が含まれています。  
  
 *function*  
 オーバーライドする 1 つまたは複数の関数名のコンマ区切りの一覧。  
  
 *オーバーライドする関数定義*  
 オーバーライド関数を定義する関数本体のステートメント。  
  
 **解説**  
  
 明示的な使用には、メソッドのシグネチャのエイリアスを作成する、またはメソッド witht 同じシグネチャの別の実装を提供するがオーバーライドされます。  
  
 継承された型および継承された型のメンバーの動作を変更する方法については、次を参照してください。[オーバーライド指定子を](../windows/override-specifiers-cpp-component-extensions.md)です。  
  
## <a name="windows-runtime"></a>Windows ランタイム  
  
### <a name="requirements"></a>必要条件  
 コンパイラ オプション: **/ZW**  
  
## <a name="common-language-runtime"></a>共通言語ランタイム 
 **解説**  
  
 ネイティブ コードで明示的なに関する情報が上書きまたはコードでコンパイルされた**/clr:oldSyntax**を参照してください[明示的なオーバーライド](../cpp/explicit-overrides-cpp.md)です。  
  
### <a name="requirements"></a>必要条件  
 コンパイラ オプション: **/clr**  
  
### <a name="examples"></a>使用例  
 **例**  
  
 次のコード例は、基本インターフェイスでの単純な明示的なオーバーライドとメンバーの実装を示しています明示的なオーバーライドを使用していないを提供します。  
  
```  
// explicit_override_1.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X : public I1 {  
public:  
   virtual void f() {  
      System::Console::WriteLine("X::f override of I1::f");  
   }  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   MyI -> f();  
}  
```  
  
 **出力**  
  
```Output  
X::f override of I1::f  
```  
  
 **例**  
  
 次のコード例では、すべてのインターフェイス メンバー一般的なシグネチャを持つが明示的なオーバーライド構文を使用して実装する方法を示します。  
  
```  
  
// explicit_override_2.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
interface struct I2 {  
   virtual void f();  
};  
  
ref struct X : public I1, I2 {  
   virtual void f() = I1::f, I2::f {  
      System::Console::WriteLine("X::f override of I1::f and I2::f");  
   }  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   I2 ^ MyI2 = gcnew X;  
   MyI -> f();  
   MyI2 -> f();  
}  
```  
  
 **出力**  
  
```Output  
X::f override of I1::f and I2::f  
X::f override of I1::f and I2::f  
```  
  
 **例**  
  
 次のコード例では、関数のオーバーライドでは、実装する関数とは異なる名前を持つことができる方法を示します。  
  
```  
// explicit_override_3.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X : public I1 {  
public:  
   virtual void g() = I1::f {  
      System::Console::WriteLine("X::g");  
   }  
};  
  
int main() {  
   I1 ^ a = gcnew X;  
   a->f();  
}  
```  
  
 **出力**  
  
```Output  
X::g  
```  
  
 **例**  
  
 次のコード例は、タイプ セーフのコレクションを実装する明示的なインターフェイス実装を示しています。  
  
```  
// explicit_override_4.cpp  
// compile with: /clr /LD  
using namespace System;  
ref class R : ICloneable {  
   int X;  
  
   virtual Object^ C() sealed = ICloneable::Clone {  
      return this->Clone();  
   }  
  
public:  
   R() : X(0) {}  
   R(int x) : X(x) {}  
  
   virtual R^ Clone() {  
      R^ r = gcnew R;  
      r->X = this->X;  
      return r;  
   }  
};  
```  
  
## <a name="see-also"></a>参照  
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)