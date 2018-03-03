---
title: "インポート ライブラリとエクスポート ファイルを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- circular exports
- import libraries, using
- export files
ms.assetid: 2634256a-8aa5-4495-8c9e-6cde10e4ed76
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 37d77fdc4df7d2e7239b8bba652d8cf8f4bbc997
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="using-an-import-library-and-export-file"></a>インポート ライブラリとエクスポート ファイルの使用
プログラム (実行可能ファイルまたは DLL) にエクスポート、インポートする別のプログラムまたはプログラムの 3 つ以上の両方をエクスポートおよびインポートから他の場合は、これらのプログラムをリンクするコマンドが循環エクスポートを対応する必要があります。  
  
 循環エクスポートを行わない場合は、別のプログラムからエクスポートを使用するプログラムをリンクしたときにエクスポート側のプログラム用インポート ライブラリを指定する必要があります。 そのエクスポート側のプログラムをリンクする場合は、エクスポート側のプログラム用インポート ライブラリが作成されます。 そのため、インポート側のプログラムの前に、エクスポート側のプログラムをリンクする必要があります。 たとえば、TWO.dll ONE.dll からインポートすると、必要がありますまず ONE.dll をリンクし、インポート ライブラリ ONE.lib を取得します。 次に、TWO.dll をリンクするときに、ONE.lib を指定します。 リンカー TWO.dll を作成すると、そのインポート ライブラリ、TWO.lib も作成します。 TWO.dll からインポートするプログラムをリンクするときに、TWO.lib を使用します。  
  
 ただし、循環エクスポートの状況で、すべての他のプログラムからのインポート ライブラリを使用して相互に依存するプログラムをリンクすることはできません。 TWO.dll にもエクスポート ONE.dll、TWO.dll 用インポート ライブラリが存在しないまだ ONE.dll がリンクされている場合は、前述の例です。 循環エクスポートが存在する場合は、インポート ライブラリを作成し、プログラムのいずれかのファイルをエクスポート LIB を使用する必要があります。  
  
 作業を開始するには、LIB を実行する対象のプログラムのいずれかを選択します。 LIB コマンドですべてのオブジェクトと、プログラムのライブラリを一覧表示し、/def オプションを指定 プログラムでは、.def ファイルまたは/EXPORT の仕様を使用する場合、それらも指定します。  
  
 インポート ライブラリ (.lib) と、プログラムのエクスポート ファイル (.exp) を作成した後は、他のプログラムまたはプログラムをリンクするときに、インポート ライブラリを使用します。 リンクでは、各エクスポート プログラムをビルドするため、インポート ライブラリを作成します。 たとえば、オブジェクトとエクスポート ONE.dll の LIB を実行する場合は、ONE.lib と ONE.exp を作成します。TWO.dll; をリンクするときに、今すぐ ONE.lib を使用することができます。この手順では、インポート ライブラリ TWO.lib も作成します。  
  
 最後で開始するプログラムをリンクします。 LINK コマンドでは、オブジェクトと、プログラムでは、プログラム、およびインポート ライブラリに対して作成された LIB .exp ファイル ライブラリや、プログラムによって使用されるエクスポートのライブラリを指定します。 例を続行するには、ONE.dll のリンク コマンドには、ONE.exp と TWO.lib、だけでなく、オブジェクトおよび ONE.dll にライブラリが含まれています。 LINK コマンドでは; で .def ファイルまたは/EXPORT 仕様を指定しません。これらは不要、.exp ファイルにエクスポートの定義が含まれているためです。 .Exp ファイルを使用してリンクすると、リンクは、インポート ライブラリを作成できませんが、.exp ファイルが作成されたときに 1 つが作成されました。  
  
## <a name="see-also"></a>参照  
 [インポート ライブラリとエクスポート ファイル](../../build/reference/working-with-import-libraries-and-export-files.md)