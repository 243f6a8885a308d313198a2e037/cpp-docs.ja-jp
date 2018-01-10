---
title: "-Zc: strictStrings (文字列リテラルの型変換の無効化) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /Zc:strictStrings
- strictStrings
dev_langs: C++
helpviewer_keywords:
- /Zc:strictStrings
- -Zc compiler options (C++)
- strictStrings
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: b7eb3f3b-82c1-48a2-8e63-66bad7397b46
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f316c5fc9209f968219d770a15e6576880b69954
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="zcstrictstrings-disable-string-literal-type-conversion"></a>/Zc:strictStrings (文字列リテラル型の変換の無効化)
指定された場合、コンパイラは、文字列リテラルを使用して初期化されたポインターに対して `const` 修飾による標準への厳密な準拠を要求します。  
  
## <a name="syntax"></a>構文  
  
```  
/Zc:strictStrings[-]  
```  
  
## <a name="remarks"></a>コメント  
 場合**/Zc:strictStrings**が指定されている、コンパイラは C++ の標準`const`型としての文字列リテラルの制限 'の配列`const char`' または 'の配列`const wchar_t`' 宣言によって、します。 文字列リテラルは変更不可であり、文字列リテラルの内容を変更しようとすると、実行時にアクセス違反エラーが発生します。 文字列ポインターは `const` として宣言して文字列リテラルで初期化するか、明示的な `const_cast` を使用して非 `const` ポインターを初期化する必要があります。 既定では、場合**/Zc:strictStrings-**を指定すると、コンパイラは C++ の標準を強制していない`const`文字列リテラルを使用して初期化された文字列ポインターを修飾します。  
  
 使用して、 **/Zc:strictStrings**不適切なコードのコンパイルを回避するにはオプションです。 この例では、単純な宣言エラーが実行時のクラッシュを招くことを示しています。  
  
```cpp  
// strictStrings_off.cpp  
// compile by using: cl /W4 strictStrings_off.cpp  
int main() {  
   wchar_t* str = L"hello";  
   str[2] = L'a'; // run-time error: access violation  
}  
```  
  
 ときに**/Zc:strictStrings**は有効な場合、同じコードによってエラーが報告の宣言で`str`です。  
  
```cpp  
// strictStrings_on.cpp  
// compile by using: cl /Zc:strictStrings /W4 strictStrings_on.cpp  
int main() {  
   wchar_t* str = L"hello"; // error: Conversion from string literal   
   // loses const qualifier  
   str[2] = L'a';   
}  
```  
  
 `auto` を使用して文字列ポインターを宣言すると、正しい `const` ポインター型宣言がコンパイラによって作成されます。 `const` ポインターの内容を変更しようとすると、コンパイラによってエラーとして報告されます。  
  
> [!NOTE]
>  C++ 標準ライブラリ[!INCLUDE[cpp_dev12_long](../../build/reference/includes/cpp_dev12_long_md.md)]はサポートしていません、 **/Zc:strictStrings**デバッグ コンパイラ オプションを構築します。 いくつかを表示する場合は[C2665](../../error-messages/compiler-errors-2/compiler-error-c2665.md)ビルドでエラー出力、原因が考えられます。  
  
 Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  選択、 **C/C++**フォルダーです。  
  
3.  選択、**コマンドライン**プロパティ ページ。  
  
4.  変更、**追加オプション**含めるプロパティを`/Zc:strictStrings`を選択し**OK**です。  
  
## <a name="see-also"></a>参照  
 [/Zc (準拠)](../../build/reference/zc-conformance.md)