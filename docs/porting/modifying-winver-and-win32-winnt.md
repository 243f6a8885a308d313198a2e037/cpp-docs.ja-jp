---
title: "WINVER および _WIN32_WINNT の変更 | Microsoft Docs"
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
- WINVER in an upgraded Visual C++ project
- _WIN32_WINNT in an upgraded Visual C++ project
ms.assetid: 6a1f1d66-ae0e-48a7-81c3-524d8e8f3447
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 220ecd24c6056737d0338cc584663e4664ac81b1
ms.openlocfilehash: 73c02454c535c030846c5a3dfca74818182baafb
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="modifying-winver-and-win32winnt"></a>WINVER および _WIN32_WINNT の変更
Visual C++ では、Windows 95、Windows 98、Windows ME、Windows NT、および Windows 2000 がサポート対象外になりました。 **WINVER** マクロまたは **_WIN32_WINNT** マクロをこれらのいずれかのバージョンの Windows に割り当てている場合は、そのマクロを修正する必要があります。 Visual C++ の以前のバージョンを使用して作成したプロジェクトをアップグレードすると、 **WINVER** マクロまたは **_WIN32_WINNT** マクロがサポート対象外になった Windows のバージョンに割り当てられている場合には、そのマクロに関連するコンパイル エラーが発生することがあります。  
  
## <a name="remarks"></a>コメント  
 マクロを変更するには、ヘッダー ファイル (たとえば、Windows を対象とするプロジェクトを作成するときに含まれる targetver.h) で、以下の行を追加します。  
  
```  
#define WINVER 0x0A00  
#define _WIN32_WINNT 0x0A00  
```  
  
 これは、Windows 10 オペレーティング システムを対象としています。 これらの値は、各 Windows バージョンのマクロを定義する Windows ヘッダー ファイル SDKDDKVer.h にもリストされています。 SDKDDKVer.h を含める前に、#define ステートメントを追加する必要があります。 Windows の各バージョンの値をエンコードする、SDKDDKVer.h の Windows 10 バージョンの行を次に示します。  
  
```  
//  
// _WIN32_WINNT version constants  
//  
#define _WIN32_WINNT_NT4                    0x0400 // Windows NT 4.0  
#define _WIN32_WINNT_WIN2K                  0x0500 // Windows 2000  
#define _WIN32_WINNT_WINXP                  0x0501 // Windows XP  
#define _WIN32_WINNT_WS03                   0x0502 // Windows Server 2003  
#define _WIN32_WINNT_WIN6                   0x0600 // Windows Vista  
#define _WIN32_WINNT_VISTA                  0x0600 // Windows Vista  
#define _WIN32_WINNT_WS08                   0x0600 // Windows Server 2008  
#define _WIN32_WINNT_LONGHORN               0x0600 // Windows Vista  
#define _WIN32_WINNT_WIN7                   0x0601 // Windows 7  
#define _WIN32_WINNT_WIN8                   0x0602 // Windows 8  
#define _WIN32_WINNT_WINBLUE                0x0603 // Windows 8.1  
#define _WIN32_WINNT_WINTHRESHOLD           0x0A00 // Windows 10  
#define _WIN32_WINNT_WIN10                  0x0A00 // Windows 10  
```  
  
 表示している SDKDDKVer.h のコピーに Windows のすべてのバージョンがリストされていない場合、古いバージョンの Windows SDK を使用している可能性があります。 既定では、Visual Studio 2017 の Win32 プロジェクトは Windows 10 SDK を使用します。   
  
> [!NOTE]
>  アプリケーションに内部 MFC ヘッダーを含めた場合には、値が動作する保証はありません。  
  
 **/D** コンパイラ オプションを使用して、このマクロを定義することもできます。 詳細については、「[/D (プリプロセッサの定義)](../build/reference/d-preprocessor-definitions.md)」を参照してください。  
  
 これらのマクロの意味について詳しくは、「 [Windows ヘッダーの使用](http://msdn.microsoft.com/library/windows/desktop/aa383745)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [前の製品の変更点](http://msdn.microsoft.com/en-us/91fa1713-0778-4b6b-82f7-0fe0a23ab1db)

