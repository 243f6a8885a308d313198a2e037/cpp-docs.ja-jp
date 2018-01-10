---
title: "リンカー入力としての .netmodule ファイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MSIL linking
- linking [C++], modules
- .netmodules
- modules, Visual C++
ms.assetid: a4bcbe8a-4255-451d-853b-f88cfd82f4e1
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: adafad3532b17573278e7afd82bc33f2c3c50b67
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="netmodule-files-as-linker-input"></a>リンカー入力としての .netmodule ファイル
link.exe では、入力として MSIL .obj と .netmodule を今すぐ受け取ります。 リンカーによって生成される出力ファイルは、アセンブリまたは依存せずに、実行時の .obj または .netmodule をリンカー入力した .netmodule になります。  
  
 .netmodule がコンパイラによって作成された、Visual C で[/LN (MSIL モジュールの作成)](../../build/reference/ln-create-msil-module.md)またはのリンカーによって[/NOASSEMBLY (MSIL モジュールの作成)](../../build/reference/noassembly-create-a-msil-module.md)です。 .obj は常に、Visual C のコンパイル時に作成されます。 他の Visual Studio コンパイラを使用して、 **/target:module**コンパイラ オプション。  
  
 ほとんどの場合、リンカーに渡す .obj ファイル、.netmodule を作成した Visual C コンパイラから、.netmodule がで作成された場合を除きする必要があります[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)です。 リンカーへの入力が、Visual C コンパイラを使用して、によって作成される純粋 MSIL にする必要がありますとして使用される MSIL .netmodule **/clr:safe**です。 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で使用されていません。 .NET の Visual Studio コンパイラでは、既定では純粋 MSIL モジュールを生成します。  
  
 コマンドラインからリンカーを呼び出す方法については、次を参照してください[リンカーのコマンドライン構文](../../build/reference/linker-command-line-syntax.md)、[コマンドラインでビルドの c/c++ コード](../../build/building-on-the-command-line.md)、および[パスと環境変数の設定。コマンド ライン ビルド](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)です。  
  
 Visual C コンパイラでコンパイルされたリンカーに .netmodule または .dll ファイルを渡す**/clr**または**/clr: 純粋な**リンカー エラーが発生することができます。 詳細については、次を参照してください。 [.netmodule 入力ファイルの形式を選択する](../../build/reference/choosing-the-format-of-netmodule-input-files.md)です。  
  
 リンカーは、ネイティブ .obj ファイルだけでなくでコンパイルされた MSIL .obj ファイルを受け入れる**/clr**、 **/clr: 純粋な**、または**/clr:safe**です。 同じビルドで混合の .obj を渡すと、結果として得られる出力ファイルの検証は、既定では、入力モジュールの検証可能性の最も低いレベルに等しくなります。 たとえば、安全で純粋な .obj をリンカーに渡す場合、出力ファイルは純粋なのようになります。 [/CLRIMAGETYPE (を指定する型の CLR イメージ)](../../build/reference/clrimagetype-specify-type-of-clr-image.md)を指定できますの下位レベルの検証可能性、必要なものである場合。  
  
 2 つ以上のアセンブリで構成されるアプリケーションが現在ある 1 つのアセンブリに含まれているアプリケーションで、使用する場合は、、アセンブリを再コンパイルを .obj または 1 つのアセンブリを生成するために .netmodule をリンクする必要があります。  
  
 エントリ ポイントを使用して、指定する必要があります[/ENTRY (エントリ ポイント シンボル)](../../build/reference/entry-entry-point-symbol.md)実行可能イメージを作成するときにします。  
  
 MSIL .obj または .netmodule ファイルを使用してリンクする場合を使用して[/LTCG (リンク時コード生成)](../../build/reference/ltcg-link-time-code-generation.md)、それ以外の場合、リンカーには、MSIL .obj または .netmodule が検出されると、再起動が/LTCG をリンクします。  
  
 MSIL .obj または .netmodule ファイルは、cl.exe に渡すこともできます。  
  
 入力の MSIL .obj または .netmodule ファイルには、リソースが埋め込まれていることはできません。 リソースが (モジュールまたはアセンブリ) の出力ファイルに埋め込まれた[/ASSEMBLYRESOURCE (マネージ リソースを埋め込む)](../../build/reference/assemblyresource-embed-a-managed-resource.md)リンカー オプション、または、 **/resource**他の Visual Studio コンパイラでコンパイラ オプション。  
  
 MSIL リンクするを実行するも指定しない場合および[/LTCG (リンク時コード生成)](../../build/reference/ltcg-link-time-code-generation.md)リンクが再起動することを通知する情報メッセージが表示されます。 このメッセージは、MSIL リンクでリンカーのパフォーマンスの向上をさせるのには、無視することができます、明示的に指定**/LTCG**です。  
  
## <a name="example"></a>例  
 C++ コードでは、対応する、試してみてくださいの catch ブロックをシステム以外の例外が呼び出されます。 ただし、既定では、CLR システム以外の例外をラップで<xref:System.Runtime.CompilerServices.RuntimeWrappedException>です。 Visual C からアセンブリを作成し、たいときに呼び出される、対応する try 句から try ブロックは例外をスロー以外のシステムを追加する必要がありますの C++ コードの catch ブロックの Visual C 以外のモジュールと、  
  
 非 C++ モジュールのソース コードを [assembly:System::Runtime::CompilerServices::RuntimeCompatibility(WrapNonExceptionThrows=false)] 属性です。  
  
```  
// MSIL_linking.cpp  
// compile with: /c /clr  
value struct V {};  
  
ref struct MCPP {  
   static void Test() {  
      try {  
         throw (gcnew V);  
      }  
      catch (V ^) {  
         System::Console::WriteLine("caught non System exception in C++ source code file");  
      }  
   }  
};  
  
/*  
int main() {  
   MCPP::Test();  
}  
*/  
```  
  
## <a name="example"></a>例  
 WrapNonExceptionThrows 属性のブール値を変更すると、システム以外の例外をキャッチする Visual C コードの機能を変更します。  
  
```  
// MSIL_linking_2.cs  
// compile with: /target:module /addmodule:MSIL_linking.obj  
// post-build command: link /LTCG MSIL_linking.obj MSIL_linking_2.netmodule /entry:MLinkTest.Main /out:MSIL_linking_2.exe /subsystem:console  
using System.Runtime.CompilerServices;  
  
// enable non System exceptions  
[assembly:RuntimeCompatibility(WrapNonExceptionThrows=false)]  
  
class MLinkTest {  
   public static void Main() {  
      try {  
         MCPP.Test();  
      }  
      catch (RuntimeWrappedException) {  
         System.Console.WriteLine("caught a wrapped exception in C#");  
      }  
   }  
}  
```  
  
```Output  
caught non System exception in C++ source code file  
```  
  
## <a name="see-also"></a>参照  
 [LINK の入力ファイル](../../build/reference/link-input-files.md)   
 [リンカー オプション](../../build/reference/linker-options.md)