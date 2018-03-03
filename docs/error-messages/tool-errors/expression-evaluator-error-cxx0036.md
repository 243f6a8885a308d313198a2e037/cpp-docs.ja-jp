---
title: "式エバリュエーター エラー CXX0036 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- CXX0036
dev_langs:
- C++
helpviewer_keywords:
- CXX0036
- CAN0036
ms.assetid: 383404be-df5b-4eec-b113-df21bb5d269d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fdf6ddf412786a53ec8da995c2824274da2da3b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0036"></a>式エバリュエーター エラー CXX0036
コンテキストが正しくありません {...} specification  
  
 このメッセージは、コンテキスト演算子の使用でエラーがいくつかのいずれかで生成されることができます (**{}**)。  
  
-   コンテキスト演算子の構文 (**{}**) が間違って指定されました。  
  
     コンテキスト演算子の構文です。  
  
     {*関数*、*モジュール*、*dll*}*式*  
  
     これが指定のコンテキスト*式*です。 コンテキスト演算子は、型キャストと同じ優先順位と使用状況がします。  
  
     末尾のコンマは省略できます。 いずれかの*関数*、*モジュール*、または*dll*リテラルのコンマが含まれる名前全体をかっこで囲む必要があります。  
  
-   関数名は、綴りが間違っている、または、指定されたモジュールまたはダイナミック リンク ライブラリに存在しません。  
  
     C は大文字小文字を区別の言語であるため*関数*ソースで定義されている正確なケースで指定する必要があります。  
  
-   モジュールまたは DLL が見つかりませんでした。  
  
     指定されたモジュールまたは DLL の完全なパス名を確認してください。  
  
 このエラーは、can0036 と同じものと同じです。