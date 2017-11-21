---
title: "コンス トラクターの初期化の順序の変更 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: constructors, C++
ms.assetid: 8892c38d-6bf7-4cf7-ac8f-15e052135a79
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bdcfea2339bfe7aac93192e88a6ec39ce919c596
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="changes-in-constructor-initialization-order"></a>コンストラクターの初期化処理の順序における変更
クラスのコンス トラクターの初期化の順序は、Visual C を c++ マネージ拡張から変更されました。  
  
## <a name="comparison-of-constructor-initialization-order"></a>コンス トラクターの初期化の順序の比較  
 C++ マネージ拡張では、コンス トラクターの初期化は、次の順序で発生しました。  
  
1.  基本クラスのコンス トラクターは、存在する場合は呼び出されます。  
  
2.  クラスの初期化リストが評価されます。  
  
3.  クラスのコンス トラクターのコード本体が実行されます。  
  
 この実行の順序では、ネイティブの C++ プログラミングのように同じ規則に従います。 新しい Visual C 言語では、CLR クラスの次の実行順序を示します。  
  
1.  クラスの初期化リストが評価されます。  
  
2.  基本クラスのコンス トラクターは、存在する場合は呼び出されます。  
  
3.  クラスのコンス トラクターのコード本体が実行されます。  
  
 この変更は、CLR クラスにのみ適用されます。 注意してください。Visual C でのネイティブ クラスには、以前の規則もに従います。 どちらの場合も、これらの規則は特定のクラスの階層全体のチェーン全体上方向へ連鎖します。  
  
 C++ マネージ拡張を使用して次のコード例を考えてみます。  
  
```  
__gc class A  
{  
public:  
   A() : _n(1)  
   {  
   }  
  
protected:  
   int _n;  
};  
  
__gc class B : public A  
{  
public:  
   B() : _m(_n)  
   {  
   }  
private:  
   int _m;  
};  
```  
  
 前述したコンス トラクターの初期化順序に従うと、実行時に新しいの次の順序いることを確認クラスのインスタンス`B`が構築されます。  
  
1.  基本クラスのコンス トラクター`A`が呼び出されます。 `_n`にメンバーを初期化`1`です。  
  
2.  クラスの初期化リスト`B`が評価されます。 `_m`にメンバーを初期化`1`です。  
  
3.  クラスのコード本体`B`を実行します。  
  
 新しい Visual C 構文では、同じコードについて考えてみましょう。  
  
```  
ref class A  
{  
public:  
   A() : _n(1)  
   {  
   }  
  
protected:  
   int _n;  
};  
  
ref class B : A  
{  
public:  
   B() : _m(_n)  
   {  
   }  
private:  
   int _m;  
};  
```  
  
 実行時に新しい順序クラスのインスタンス`B`新しいで構築された構文します。  
  
1.  クラスの初期化リスト`B`が評価されます。 `_m`にメンバーを初期化`0`(`0`の初期化されていない値には、`_m`クラスのメンバー)。  
  
2.  基本クラスのコンス トラクター`A`が呼び出されます。 `_n`にメンバーを初期化`1`です。  
  
3.  クラスのコード本体`B`を実行します。  
  
 同様の構文がこれらのコード例に異なる結果を生成することに注意してください。 クラスのコンス トラクター`B`基底クラスからの値に依存`A`をそのメンバーを初期化します。 ただし、クラスのコンス トラクター`A`まだ呼び出されています。 このような依存関係は、継承されたクラスが基底クラス コンス トラクターで発生するメモリまたはリソースの割り当てに依存する場合、特に危険なことができます。  
  
## <a name="what-this-means-going-from-managed-extensions-for-c-to-visual-c-2010"></a>この意味 c++ マネージ拡張から Visual C 2010 に移動  
 多くの場合にクラスのコンス トラクターの実行順序を変更する必要があります、プログラマに対して透過的に基底クラスに継承するクラスの動作の概念があるないためです。 ただし、これらのコード例に示すよう継承するクラスのコンス トラクターは、影響する可能性が大幅にその初期化リストは、基本クラスのメンバーの値に依存している場合。 移動を検討する新しい構文で、c++ マネージ拡張からコードを移動するときに実行が確実に、クラスのコンス トラクターの本体には、このようなコンストラクトが最後に発生します。  
  
## <a name="see-also"></a>関連項目  
 [マネージ型 (C + + CL)](../dotnet/managed-types-cpp-cl.md)   
 [コンストラクター](../cpp/constructors-cpp.md)   
 