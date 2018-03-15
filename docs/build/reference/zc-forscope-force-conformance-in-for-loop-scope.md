---
title: "/Zc:forScope (for の強制準拠ループ スコープ) |Microsoft ドキュメント"
ms.custom: 
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.ForceConformanceInForLoopScope
- VC.Project.VCCLWCECompilerTool.ForceConformanceInForLoopScope
- /zc:forScope
dev_langs:
- C++
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: 3031f02d-3b14-4ad0-869e-22b0110c3aed
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 47cdc45b63e5e5c7b48627b13040e95fc64c8a2d
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2018
---
# <a name="zcforscope-force-conformance-in-for-loop-scope"></a>/Zc:forScope (for ループのスコープの強制準拠)

Microsoft の拡張機能 ( [/Ze](../../cpp/for-statement-cpp.md) ) の[for](../../build/reference/za-ze-disable-language-extensions.md)ループの標準 C++ 動作を実装するために使用します。

## <a name="syntax"></a>構文

> **/Zc:forScope**[**-**]

## <a name="remarks"></a>コメント

標準動作とは、 **for** ループの初期化子が **for** ループの後にスコープ外に出るようにすることです。 **/Zc:forScope-** と [/Ze](../../build/reference/za-ze-disable-language-extensions.md)では、 **for** ループの初期化子は、ローカル スコープが終わるまでスコープ内にとどまります。

**/Zc:forScope**オプションは既定でオンです。 **/Zc:forScope**ときに影響しません、[寛容/-](permissive-standards-conformance.md)オプションを指定します。

**/Zc:forScope-** オプションは使用されなくなりました。今後のバージョンからは削除されます。 **/Zc:forScope-** を使うと、廃止予定の警告 D9035 が表示されます。

次のコードは **/Ze** ではコンパイルされますが、 **/Za**ではコンパイルされません。

```cpp
// zc_forScope.cpp
// compile by using: cl /Zc:forScope- /Za zc_forScope.cpp
// C2065, D9035 expected  
int main() {
    // Compile by using cl /Zc:forScope- zc_forScope.cpp
    // to compile this non-standard code as-is.
    // Uncomment the following line to resolve C2065 for /Za.
    // int i;
    for (int i = 0; i < 1; i++)
        ;
    i = 20;   // i has already gone out of scope under /Za
}
```

**/Zc:forScope-**を使う場合、以前のスコープで行った宣言によって変数がスコープ内にあるときに、警告 C4288 (既定ではオフ) が表示されます。 これを示すために、サンプル コードから `//` の文字を削除して `int i`を宣言します。

**/Zc:forScope** の実行時の動作は、 [conform](../../preprocessor/conform.md) プラグマを使って変更できます。

既存の .pch ファイルがあるプロジェクトで **/Zc:forScope-** を使う場合、警告が表示され、 **/Zc:forScope-** は無視され、既存の .pch ファイルを使ってコンパイルが継続されます。 新しい .pch ファイルを生成する場合は、使用[/Yc (プリコンパイル済みヘッダー ファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)です。

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **C/C++** > **言語**プロパティ ページ。

1. **[for ループ スコープの強制準拠]** プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForceConformanceInForLoopScope%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](../../build/reference/zc-conformance.md)<br/>
[/Za、/Ze (言語拡張機能の無効化)](../../build/reference/za-ze-disable-language-extensions.md)<br/>
