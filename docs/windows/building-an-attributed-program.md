---
title: "属性付きプログラムを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- tlb files
- MIDL
- MIDL, linker output
- IDL files
- tlb files, building attributed programs
- .tlb files, building attributed programs
- IDL files, building
- attributes [C++], building type libraries and .idl files
- .tlb files
- .idl files, building
- type libraries, linker options for building
ms.assetid: 04997b5f-bf2c-46ec-b868-c4adebbef5f4
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a757cbbb7bb9e080a9492ecabfd0542714cf2c7a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="building-an-attributed-program"></a>属性付きプログラムの作成
Visual C 属性をソース コードに配置すると後のタイプ ライブラリおよび .idl ファイルを生成するために、Visual C コンパイラもかまいません。 次のリンカー オプション、.tlb および .idl ファイルをビルドするときに役立ちます。  
  
-   [/IDLOUT](../build/reference/idlout-name-midl-output-files.md)  
  
-   [/IGNOREIDL](../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)  
  
-   [/MIDL](../build/reference/midl-specify-midl-command-line-options.md)  
  
-   [/TLBOUT](../build/reference/tlbout-name-dot-tlb-file.md)  
  
 いくつかのプロジェクトには、複数の独立した .idl ファイルが含まれています。 これらは、2 つ以上の .tlb ファイルを生成し、必要に応じてリソース ブロックにバインドに使用されます。 このシナリオは、この Visual C では現在サポートされていません。  
  
 さらに、Visual C リンカーは、単一の MIDL ファイルにすべての属性の IDL に関連する情報を出力します。 1 つのプロジェクトから次の 2 つのタイプ ライブラリを生成する方法されません。  
  
## <a name="see-also"></a>関連項目  
 [概念](../windows/attributed-programming-concepts.md)