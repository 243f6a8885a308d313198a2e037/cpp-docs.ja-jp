---
title: "WeakReference::WeakReference コンストラクター (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/WeakReference::WeakReference"
ms.assetid: b2f712e0-3ee0-4a05-b861-973b4a212609
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WeakReference::WeakReference コンストラクター (C++/CX)
WeakReference を構築するさまざまな方法を提供します。  
  
## 構文  
  
```scr  
WeakReference();  
WeakReference(decltype(__nullptr));  
WeakReference(const WeakReference& __otherArg);  
WeakReference(WeakReference&& __otherArg);  
explicit WeakReference(const volatile ::Platform::Object^ const __otherArg);  
```  
  
## 使用例  
  
```scr  
  
MyClass^ mc = ref new MyClass(); WeakReference wr(mc); MyClass^ copy2 = wr.Resolve<MyClass>();  
  
```  
  
## 解説  
  
## 必要条件  
  
## 参照  
 [プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)   
 [Platform::WeakReference クラス](../cppcx/platform-weakreference-class.md)