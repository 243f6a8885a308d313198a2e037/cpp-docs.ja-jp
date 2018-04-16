---
title: "/Zc (準拠) |Microsoft ドキュメント"
ms.custom: 
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- /zc
dev_langs:
- C++
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dda62dc6644fd49cf9213b176a4efe563474f740
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2018
---
# <a name="zc-conformance"></a>/Zc (準拠)

使用することができます、 **/Zc**コンパイラ オプションを標準または Microsoft 固有のコンパイラの動作を指定します。

## <a name="syntax"></a>構文

> **/Zc:**_option_{,_option_}

## <a name="remarks"></a>コメント

Visual Studio には、C または C++ 規格と互換性がない拡張機能が実装されているが、ときに行うこともできます、`/Zc`準拠オプションまたは Microsoft 固有の標準準拠の動作を指定します。 いくつかのオプションでは、Microsoft 固有の動作は既存のコードを大規模な重大な変更を防ぐために、既定値です。 それ以外の場合に、既定値は、セキュリティ、パフォーマンス、または互換性の機能強化が重大な変更のコストを上回る場合、標準の動作ではします。 準拠の各オプションの既定の設定は、新しいバージョンの Visual Studio で変更できます。 準拠の各オプションの詳細については、特定のオプションのトピックを参照してください。 [寛容/-](permissive-standards-conformance.md)コンパイラ オプションは、の準拠設定に既定で設定されていない準拠オプションを暗黙的に設定します。

これらは、`/Zc`コンパイラ オプション。

|オプション|動作|
|---|---|
|[alignedNew\[-\]](zc-alignednew.md)|C++ 17 オーバーア ラインされている動的割り当てを有効にする (既定で有効にで c++ 17)。|
|[auto\[-\]](zc-auto-deduce-variable-type.md)|新しい標準 C++ の解釈を強制`auto`(で既定で)。|
|[externConstexpr\[-\]](zc-externconstexpr.md)|外部リンケージを有効にする`constexpr`変数 (既定でオフ)。|
|[forScope\[-\]](zc-forscope-force-conformance-in-for-loop-scope.md)|標準 C++ を適用する`for`スコープの規則 (で既定で)。|
|[implicitNoexcept\[-\]](zc-implicitnoexcept-implicit-exception-specifiers.md)|有効にする暗黙的な`noexcept`に必要な関数 (で既定で)。|
|[inline\[-\]](zc-inline-remove-unreferenced-comdat.md)|COMDAT はまたは内部リンケージのみを持つ場合に参照されない関数、またはデータを削除する (既定でオフ)。|
|[noexceptTypes\[-\]](zc-noexcepttypes.md)|C++ 17 noexcept ルールを適用する (で既定では c++ 17 またはそれ以降)。|
|[referenceBinding\[-\]](zc-referencebinding-enforce-reference-binding-rules.md)|非定数の左辺値参照に、UDT の一時的なはバインドされません (既定でオフ)。|
|[rvalueCast\[-\]](zc-rvaluecast-enforce-type-conversion-rules.md)|標準 C++ の明示的な型変換規則を強制する (既定でオフ)。|
|[sizedDealloc\[-\]](zc-sizeddealloc-enable-global-sized-dealloc-functions.md)|C++ 14 グローバル サイズの割り当て解除機能を有効にする (で既定で)。|
|[strictStrings\[-\]](zc-strictstrings-disable-string-literal-type-conversion.md)|文字列リテラルを無効にする`char*`または`wchar_t*`変換 (既定でオフ)。|
|[ternary\[-\]](zc-ternary.md)|オペランドの型の条件演算子のルールを適用する (既定でオフ)。|
|[threadSafeInit\[-\]](zc-threadsafeinit-thread-safe-local-static-initialization.md)|スレッド セーフであるローカルの静的な初期化を有効にする (で既定で)。|
|[throwingNew\[-\]](zc-throwingnew-assume-operator-new-throws.md)|想定`operator new`でエラーがスローされます (既定でオフ)。|
|[trigraphs\[-\]](zc-trigraphs-trigraphs-substitution.md)|トライグラフ (廃止、オフ既定) を有効にします。|
|[twoPhase-](zc-twophase.md)|解析の動作 (既定では準拠している) 非準拠のテンプレートを使用します。|
|[wchar_t\[-\]](zc-wchar-t-wchar-t-is-native-type.md)|`wchar_t` ネイティブ型を typedef ではありません (で既定で)。|

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

## <a name="see-also"></a>参照

[コンパイラ オプション](compiler-options.md)  
[コンパイラ オプションの設定](setting-compiler-options.md)
