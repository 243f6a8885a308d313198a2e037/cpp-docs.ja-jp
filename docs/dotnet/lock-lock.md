---
title: "lock::lock |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- lock::lock
- lock.lock
- msclr.lock.lock
- msclr::lock::lock
dev_langs: C++
helpviewer_keywords: lock constructor
ms.assetid: c9ad6c71-36ec-49c5-8ebd-f5c3a0cc94f0
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0bc0c0e61b4500bae9589cbf6b536f1a23ae45c8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="locklock"></a>lock::lock
構築、`lock`オブジェクト、必要に応じて、指定された時間、またはまったく恒久的に、ロックの取得を待機しています。  
  
## <a name="syntax"></a>構文  
  
```  
template<class T> lock(  
   T ^ _object  
);  
template<class T> lock(  
   T ^ _object,  
   int _timeout  
);  
template<class T> lock(  
   T ^ _object,  
   System::TimeSpan _timeout  
);  
template<class T> lock(  
   T ^ _object,  
   lock_later  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `_object`  
 ロックするオブジェクト。  
  
 `_timeout`  
 タイムアウト値 (ミリ秒単位) として、<xref:System.TimeSpan>です。  
  
## <a name="exceptions"></a>例外  
 スロー<xref:System.ApplicationException>ロックの取得がタイムアウトする前に発生しない場合。  
  
## <a name="remarks"></a>コメント  
 コンス トラクターの最初の 3 つのフォームに対するロックの取得しようとしました。 `_object` 、指定されたタイムアウト期間内 (または<xref:System.Threading.Timeout.Infinite>が指定されない場合)。  
  
 コンス トラクターの 4 番目の形式でのロックを取得しない`_object`です。 `lock_later`メンバーである、 [lock_when 列挙](../dotnet/lock-when-enum.md)です。 使用して[lock::acquire](../dotnet/lock-acquire.md)または[lock::try_acquire](../dotnet/lock-try-acquire.md)ここでは、ロックを取得します。  
  
 デストラクターが呼び出されたときに、ロックが自動的に解放されます。  
  
 `_object` として <xref:System.Threading.ReaderWriterLock> を使用することはできません。  場合は、コンパイラ エラーが発生します。  
  
## <a name="example"></a>例  
 この例では、複数のスレッド間でクラスの 1 つのインスタンスで使用します。  クラスは、その内部データへのアクセスがスレッドごとに一貫していることを確認するのに自体に対するロックを使用します。  メイン アプリケーション スレッドは、ワーカー スレッドがまだ存在していて、そのタスクを完了したすべてのワーカー スレッドまで終了を待機を定期的に確認するクラスの同じインスタンスでロックを使用します。  
  
```  
// msl_lock_lock.cpp  
// compile with: /clr  
#include <msclr/lock.h>  
  
using namespace System;  
using namespace System::Threading;  
using namespace msclr;  
  
ref class CounterClass {  
private:  
   int Counter;     
  
public:  
   property int ThreadCount;  
  
   // function called by multiple threads, use lock to keep Counter consistent  
   // for each thread  
   void UseCounter() {  
      try {  
         lock l(this); // wait infinitely  
  
         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,   
            Counter);  
  
         for (int i = 0; i < 10; i++) {  
            Counter++;  
            Thread::Sleep(10);  
         }  
  
         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,   
            Counter);  
  
         Counter = 0;  
         // lock is automatically released when it goes out of scope and its destructor is called  
      }  
      catch (...) {  
         Console::WriteLine("Couldn't acquire lock!");  
      }  
  
      ThreadCount--;  
   }  
};  
  
int main() {  
   // create a few threads to contend for access to the shared data  
   CounterClass^ cc = gcnew CounterClass;  
   array<Thread^>^ tarr = gcnew array<Thread^>(5);  
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);  
   for (int i = 0; i < tarr->Length; i++) {  
      tarr[i] = gcnew Thread(startDelegate);  
      cc->ThreadCount++;  
      tarr[i]->Start();  
   }  
  
   // keep our main thread alive until all worker threads have completed  
   lock l(cc, lock_later); // don't lock now, just create the object  
   while (true) {  
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't  
         if (0 == cc->ThreadCount) {  
            Console::WriteLine("All threads completed.");  
            break; // all threads are gone, exit while  
         }  
         else {  
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);  
            l.release(); // some threads exist, let them do their work  
         }  
      }  
   }  
}  
```  
  
```Output  
In thread 3, Counter = 0  
In thread 3, Counter = 10  
In thread 5, Counter = 0  
In thread 5, Counter = 10  
In thread 7, Counter = 0  
In thread 7, Counter = 10  
In thread 4, Counter = 0  
In thread 4, Counter = 10  
In thread 6, Counter = 0  
In thread 6, Counter = 10  
All threads completed.  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー ファイル** \<msclr\lock.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>関連項目  
 [lock のメンバー](../dotnet/lock-members.md)   
 [ロック:: ~ ロック](../dotnet/lock-tilde-lock.md)   
 [lock::acquire](../dotnet/lock-acquire.md)   
 [lock::try_acquire](../dotnet/lock-try-acquire.md)