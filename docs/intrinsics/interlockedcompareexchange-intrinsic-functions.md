---
title: "_InterlockedCompareExchange Intrinsic Functions | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedCompareExchange_HLERelease"
  - "_InterlockedCompareExchange8_nf"
  - "_InterlockedCompareExchange16_acq_cpp"
  - "_InterlockedCompareExchange_acq_cpp"
  - "_InterlockedCompareExchange16_rel_cpp"
  - "_InterlockedCompareExchange64_rel_cpp"
  - "_InterlockedCompareExchange_cpp"
  - "_InterlockedCompareExchange16_cpp"
  - "_InterlockedCompareExchange64_acq_cpp"
  - "_InterlockedCompareExchange_acq"
  - "_InterlockedCompareExchange64_rel"
  - "_InterlockedCompareExchange64_nf"
  - "_InterlockedCompareExchange_rel_cpp"
  - "_InterlockedCompareExchange16_nf"
  - "_InterlockedCompareExchange8"
  - "_InterlockedCompareExchange64_np"
  - "_InterlockedCompareExchange16_rel"
  - "_InterlockedCompareExchange64_acq"
  - "_InterlockedCompareExchange8_rel"
  - "_InterlockedCompareExchange_HLEAcquire"
  - "_InterlockedCompareExchange64_HLERelease"
  - "_InterlockedCompareExchange64_cpp"
  - "_InterlockedCompareExchange_np"
  - "_InterlockedCompareExchange8_acq"
  - "_InterlockedCompareExchange16_acq"
  - "_InterlockedCompareExchange_rel"
  - "_InterlockedCompareExchange64_HLEAcquire"
  - "_InterlockedCompareExchange64"
  - "_InterlockedCompareExchange16"
  - "_InterlockedCompareExchange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_InterlockedCompareExchange intrinsic"
  - "_InterlockedCompareExchange_acq intrinsic"
  - "_InterlockedCompareExchange_rel intrinsic"
  - "_InterlockedCompareExchange16 intrinsic"
  - "_InterlockedCompareExchange64 intrinsic"
  - "_InterlockedCompareExchange64_acq intrinsic"
  - "_InterlockedCompareExchange64_rel intrinsic"
  - "InterlockedCompareExchange intrinsic"
  - "InterlockedCompareExchange_acq intrinsic"
  - "InterlockedCompareExchange_rel intrinsic"
  - "InterlockedCompareExchange16 intrinsic"
  - "InterlockedCompareExchange64 intrinsic"
  - "InterlockedCompareExchange64_acq intrinsic"
  - "InterlockedCompareExchange64_rel intrinsic"
ms.assetid: c3ad79c0-a523-4930-a3a4-69a65d7d5c81
caps.latest.revision: 26
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _InterlockedCompareExchange Intrinsic Functions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 インタロックされた比較および交換を実行します。  
  
## 構文  
  
```  
long _InterlockedCompareExchange(  
   long volatile * Destination,  
   long Exchange,  
   long Comparand  
);  
long _InterlockedCompareExchange_acq(  
   long volatile * Destination,  
   long Exchange,  
   long Comparand  
);  
long _InterlockedCompareExchange_HLEAcquire(  
   long volatile * Destination,  
   long Exchange,  
   long Comparand  
);  
long _InterlockedCompareExchange_HLERelease(  
   long volatile * Destination,  
   long Exchange,  
   long Comparand  
);  
long _InterlockedCompareExchange_np(  
   long volatile * Destination,  
   long Exchange,  
   long Comparand  
);  
long _InterlockedCompareExchange_rel(  
   long volatile * Destination,  
   long Exchange,  
   long Comparand  
);  
char _InterlockedCompareExchange8(  
   char volatile * Destination,  
   char Exchange,  
   char Comparand  
);  
char _InterlockedCompareExchange8_acq(  
   char volatile * Destination,  
   char Exchange,  
   char Comparand  
);  
char _InterlockedCompareExchange8_nf(  
   char volatile * Destination,  
   char Exchange,  
   char Comparand  
);  
char _InterlockedCompareExchange8_rel(  
   char volatile * Destination,  
   char Exchange,  
   char Comparand  
);  
short _InterlockedCompareExchange16(  
   short volatile * Destination,  
   short Exchange,  
   short Comparand  
);  
short _InterlockedCompareExchange16_acq(  
   short volatile * Destination,  
   short Exchange,  
   short Comparand  
);  
short _InterlockedCompareExchange16_nf(  
   short volatile * Destination,  
   short Exchange,  
   short Comparand  
);  
short _InterlockedCompareExchange16_np(  
   short volatile * Destination,  
   short Exchange,  
   short Comparand  
);  
short _InterlockedCompareExchange16_rel(  
   short volatile * Destination,  
   short Exchange,  
   short Comparand  
);  
__int64 _InterlockedCompareExchange64(  
   __int64 volatile * Destination,  
   __int64 Exchange,  
   __int64 Comparand  
);  
__int64 _InterlockedCompareExchange64_acq(  
   __int64 volatile * Destination,  
   __int64 Exchange,  
   __int64 Comparand  
);  
__int64 _InterlockedCompareExchange64_HLEAcquire (  
   __int64 volatile * Destination,  
   __int64 Exchange,  
   __int64 Comparand  
);  
__int64 _InterlockedCompareExchange64_HLERelease(  
   __int64 volatile * Destination,  
   __int64 Exchange,  
   __int64 Comparand  
);  
__int64 _InterlockedCompareExchange64_nf(  
   __int64 volatile * Destination,  
   __int64 Exchange,  
   __int64 Comparand  
);  
__int64 _InterlockedCompareExchange64_np(  
   __int64 volatile * Destination,  
   __int64 Exchange,  
   __int64 Comparand  
);  
__int64 _InterlockedCompareExchange64_rel(  
   __int64 volatile * Destination,  
   __int64 Exchange,  
   __int64 Comparand  
);  
```  
  
#### パラメーター  
 \[入力、出力\] `Destination`  
 対象値へのポインター。  符号は無視されます。  
  
 \[入力\] `Exchange`  
 Exchange の値。  符号は無視されます。  
  
 \[入力\] `Comparand`  
 対象と比較する値。  符号は無視されます。  
  
## 戻り値  
 戻り値は、`Destination` ポインターの初期値です。  
  
## 必要条件  
  
|組み込み|アーキテクチャ|ヘッダー|  
|----------|-------------|----------|  
|`_InterlockedCompareExchange`, `_InterlockedCompareExchange8`, `_InterlockedCompareExchange16`, `_InterlockedCompareExchange64`|x86、ARM、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedCompareExchange_acq`, `_InterlockedCompareExchange_rel`, `_InterlockedCompareExchange8_acq`, `_InterlockedCompareExchange8_nf`, `_InterlockedCompareExchange8_rel`,`_InterlockedCompareExchange16_acq`, `_InterlockedCompareExchange16_nf`, `_InterlockedCompareExchange16_rel`, `_InterlockedCompareExchange64_acq`, `_InterlockedCompareExchange64_nf`, `_InterlockedCompareExchange64_rel`,|ARM|\<intrin.h\>|  
|`_InterlockedCompareExchange_np`、`_InterlockedCompareExchange16_np`、`_InterlockedCompareExchange64_np`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedCompareExchange_HLEAcquire`, `_InterlockedCompareExchange_HLERelease`, `_InterlockedCompareExchange64_HLEAcquire`, `_InterlockedCompareExchange64_HLERelease`|x86、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\<immintrin.h\>|  
  
## 解説  
 `_InterlockedCompareExchange` は、`Destination` 値と `Comparand` 値のアトミックな比較を実行します。  `Destination` 値が `Comparand` 値と等しい場合、`Exchange` 値は `Destination` で指定されたアドレスに格納されます。  それ以外の場合は演算が実行されません。  
  
 `_InterlockedCompareExchange` は、Win32 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] [InterlockedCompareExchange](http://msdn.microsoft.com/library/ms683560.aspx) 関数のコンパイラ組み込みサポートを提供します。  
  
 `_InterlockedCompareExchange` には、格納するデータ型、およびプロセッサ固有の取得または解放のセマンティクスを使用するかどうかに基づき、異なるいくつかの種類があります。  
  
 `_InterlockedCompareExchange` 関数は long 型の整数値で動作しますが、`_InterlockedCompareExchange8` は 8 ビット整数値、`_InterlockedCompareExchange16` は short 型の整数値、および `_InterlockedCompareExchange64` は 64 ビット整数値で動作します。  
  
 ARM プラットフォームでは、クリティカル セクションの最初と最後などでの取得と解放のセマンティクスのために、`_acq` および `_rel` サフィックスの付いた組み込みを使用します。  `_nf` \("フェンスなし"\) サフィックスの付いた ARM 組み込みはメモリ バリアとしては機能しません。  
  
 組み込みに `_np` \("プリフェッチなし"\) サフィックスが付いていると、コンパイラによってプリフェッチ操作が挿入される可能性がなくなります。  
  
 Hardware Lock Elision \(HLE\) 命令をサポートする Intel プラットフォームでは、`_HLEAcquire` および `_HLERelease` サフィックスの付いた組み込みにプロセッサへのヒントが含まれています。このヒントによりハードウェアでのロック書き込み手順を省くことで、パフォーマンスを向上させることができます。  HLE をサポートしていないプラットフォームでこれらの組み込みが呼び出された場合、ヒントは無視されます。  
  
 これらのルーチンは、組み込みとしてのみ使用できます。  
  
## 使用例  
 次の例では、単純な低レベルのスレッド同期に `_InterlockedCompareExchange` を使用しています。  マルチスレッド プログラミングの基本であるこの方法には制限がありますが、インタロックされた組み込みの代表的な使用例を示すために紹介します。  最適な結果を得るには Windows API を使用してください。  マルチスレッド プログラミングの詳細については、「[マルチスレッド Win32 プログラムの作成](../Topic/Writing%20a%20Multithreaded%20Win32%20Program.md)」を参照してください。  
  
```  
// intrinExample.cpp  
// compile with: /EHsc /O2  
// Simple example of using _Interlocked* intrinsics to  
// do manual synchronization  
//  
// Add [-DSKIP_LOCKING] to the command line to disable  
// the locking. This will cause the threads to execute out  
// of sequence.  
  
#define _CRT_RAND_S  
  
#include "windows.h"  
  
#include <iostream>  
#include <queue>  
#include <intrin.h>  
  
using namespace std;  
  
// --------------------------------------------------------------------  
  
// if defined, will not do any locking on shared data  
//#define SKIP_LOCKING  
  
// A common way of locking using _InterlockedCompareExchange.  
// Please refer to other sources for a discussion of the many issues  
// involved. For example, this particular locking scheme performs well   
// when lock contention is low, as the while loop overhead is small and  
// locks are acquired very quickly, but degrades as many callers want  
// the lock and most threads are doing a lot of interlocked spinning.  
// There are also no guarantees that a caller will ever acquire the  
// lock.  
namespace MyInterlockedIntrinsicLock  
{  
    typedef unsigned LOCK, *PLOCK;  
  
#pragma intrinsic(_InterlockedCompareExchange, _InterlockedExchange)  
  
    enum {LOCK_IS_FREE = 0, LOCK_IS_TAKEN = 1};  
  
    void Lock(PLOCK pl)   
    {  
#if !defined(SKIP_LOCKING)  
        // If *pl == LOCK_IS_FREE, it is set to LOCK_IS_TAKEN  
        // atomically, so only 1 caller gets the lock.  
        // If *pl == LOCK_IS_TAKEN,  
        // the result is LOCK_IS_TAKEN, and the while loop keeps spinning.  
        while (_InterlockedCompareExchange((long *)pl,  
                                           LOCK_IS_TAKEN, // exchange  
                                           LOCK_IS_FREE)  // comparand  
               == LOCK_IS_TAKEN)  
        {  
            // spin!  
        }  
        // This will also work.  
        //while (_InterlockedExchange(pl, LOCK_IS_TAKEN) ==   
        //                             LOCK_IS_TAKEN)  
        //{  
        //    // spin!  
        //}  
  
        // At this point, the lock is acquired.  
#endif  
    }  
  
    void Unlock(PLOCK pl) {  
#if !defined(SKIP_LOCKING)  
        _InterlockedExchange((long *)pl, LOCK_IS_FREE);  
#endif  
    }  
}  
  
// ------------------------------------------------------------------  
  
// Data shared by threads  
  
queue<int> SharedQueue;  
MyInterlockedIntrinsicLock::LOCK SharedLock;  
int TicketNumber;  
  
// ------------------------------------------------------------------  
  
DWORD WINAPI  
ProducerThread(  
    LPVOID unused  
    )  
{  
    unsigned int randValue;  
    while (1) {  
        // Acquire shared data. Enter critical section.  
        MyInterlockedIntrinsicLock::Lock(&SharedLock);  
  
        //cout << ">" << TicketNumber << endl;  
        SharedQueue.push(TicketNumber++);  
  
        // Release shared data. Leave critical section.  
        MyInterlockedIntrinsicLock::Unlock(&SharedLock);  
  
        rand_s(&randValue);  
        Sleep(randValue % 20);  
    }  
  
    return 0;  
}  
  
DWORD WINAPI  
ConsumerThread(  
    LPVOID unused  
    )  
{  
    while (1) {  
        // Acquire shared data. Enter critical section  
        MyInterlockedIntrinsicLock::Lock(&SharedLock);  
  
        if (!SharedQueue.empty()) {  
            int x = SharedQueue.front();  
            cout << "<" << x << endl;  
            SharedQueue.pop();  
        }  
  
        // Release shared data. Leave critical section  
        MyInterlockedIntrinsicLock::Unlock(&SharedLock);  
  
        unsigned int randValue;  
        rand_s(&randValue);  
        Sleep(randValue % 20);  
    }  
    return 0;  
}  
  
int main(  
    void  
    )  
{  
    const int timeoutTime = 500;  
    int unused1, unused2;  
    HANDLE threads[4];  
  
    // The program creates 4 threads:  
    // two producer threads adding to the queue  
    // and two consumers taking data out and printing it.  
    threads[0] = CreateThread(NULL,  
                              0,  
                              ProducerThread,  
                              &unused1,  
                              0,  
                              (LPDWORD)&unused2);  
  
    threads[1] = CreateThread(NULL,  
                              0,  
                              ConsumerThread,  
                              &unused1,  
                              0,  
                              (LPDWORD)&unused2);  
  
    threads[2] = CreateThread(NULL,  
                              0,  
                              ProducerThread,  
                              &unused1,  
                              0,  
                              (LPDWORD)&unused2);  
  
    threads[3] = CreateThread(NULL,  
                              0,  
                              ConsumerThread,  
                              &unused1,  
                              0,  
                              (LPDWORD)&unused2);  
  
    WaitForMultipleObjects(4, threads, TRUE, timeoutTime);  
  
    return 0;  
}  
```  
  
  **\<0**  
**\<1**  
**\<2**  
**\<3**  
**\<4**  
**\<5**  
**\<6**  
**\<7**  
**\<8**  
**\<9**  
**\<10**  
**\<11**  
**\<12**  
**\<13**  
**\<14**  
**\<15**  
**\<16**  
**\<17**  
**\<18**  
**\<19**  
**\<20**  
**\<21**  
**\<22**  
**\<23**  
**\<24**  
**\<25**  
**\<26**  
**\<27**  
**\<28**  
**\<29**   
## END Microsoft 固有の仕様  
  
## 参照  
 [\_InterlockedCompareExchange128](../intrinsics/interlockedcompareexchange128.md)   
 [\_InterlockedCompareExchangePointer の組み込み関数](../intrinsics/interlockedcompareexchangepointer-intrinsic-functions.md)   
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [x86 コンパイラとの競合](../Topic/Conflicts%20with%20the%20x86%20Compiler.md)