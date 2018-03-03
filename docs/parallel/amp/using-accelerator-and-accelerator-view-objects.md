---
title: "アクセラレータおよび accelerator_view オブジェクトを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 18f0dc66-8236-4420-9f46-1a14f2c3fba1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8cc676407a88979679a362b3d36f361614524432
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="using-accelerator-and-acceleratorview-objects"></a>アクセラレータおよび accelerator_view オブジェクトの使用
使用することができます、[アクセラレータ](../../parallel/amp/reference/accelerator-class.md)と[accelerator_view](../../parallel/amp/reference/accelerator-view-class.md)デバイスまたはエミュレーターで、C++ AMP コードを実行するを指定するクラス。 システムには、メモリの量、共有メモリ サポート、デバッグ サポート、または倍精度サポートによって異なる複数のデバイスまたはエミュレーターがある場合があります。 C++ Accelerated Massive Parallelism (C++ AMP) には、使用できるアクセラレータの調査、既定としての設定、parallel_for_each の複数の呼び出しのための複数の accelerator_views の指定、特別なデバッグ タスクの実行のために使用できる API が用意されています。  
  
## <a name="using-the-default-accelerator"></a>既定のアクセラレータを使用する  
 C++ AMP ランタイムでは、特定のアクセラレータを選択するコードを記述しない限り、既定のアクセラレータが選択されます。 ランタイムは次のように既定のアクセラレータを選択します。  
  
1.  アプリがデバッグ モードで実行されている場合は、デバッグをサポートするアクセラレータ。  
  
2.  または、設定されている場合は、CPPAMP_DEFAULT_ACCELERATOR 環境変数で指定されるアクセラレータ。  
  
3.  または、エミュレートされていないデバイス。  
  
4.  または、使用できるメモリ量が最大のデバイス。  
  
5.  または、ディスプレイにアタッチされていないデバイス。  
  
 また、ランタイムは既定のアクセラレータとして `access_type` の `access_type_auto` を指定します。 これは、サポートされていて、パフォーマンス特性 (帯域幅と待機時間) が専用の (共有されない) メモリと同じになることがわかっている場合には、既定のアクセラレータが共有メモリを使用することを意味します。  
  
 既定のアクセラレータを構築し、プロパティを調べることによって、既定のアクセラレータのプロパティを確認できます。 次のコード例では、既定のアクセラレータのパス、アクセラレータ メモリの量、共有メモリ サポート、倍精度サポート、および制限された倍精度のサポートを出力します。  
  
```cpp  
void default_properties() {  
    accelerator default_acc;  
    std::wcout << default_acc.device_path << "\n";  
    std::wcout << default_acc.dedicated_memory << "\n";  
    std::wcout << (accs[i].supports_cpu_shared_memory ?   
        "CPU shared memory: true" : "CPU shared memory: false") << "\n";  
    std::wcout << (accs[i].supports_double_precision ?   
        "double precision: true" : "double precision: false") << "\n";  
    std::wcout << (accs[i].supports_limited_double_precision ?   
        "limited double precision: true" : "limited double precision: false") << "\n";  
}  
 
```  
  
### <a name="cppampdefaultaccelerator-environment-variable"></a>CPPAMP_DEFAULT_ACCELERATOR 環境変数  
 CPPAMP_DEFAULT_ACCELERATOR 環境変数を設定して、既定のアクセラレータの `accelerator::device_path` を指定できます。 パスはハードウェアに依存します。 次のコードは、`accelerator::get_all` 関数を使用して、使用できるアクセラレータの一覧を取得し、各アクセラレータのパスと特性を表示します。  
  
```cpp  
void list_all_accelerators()  
{  
    std::vector<accelerator> accs = accelerator::get_all();  
  
    for (int i = 0; i <accs.size(); i++) {  
        std::wcout << accs[i].device_path << "\n";  
        std::wcout << accs[i].dedicated_memory << "\n";  
        std::wcout << (accs[i].supports_cpu_shared_memory ?   
            "CPU shared memory: true" : "CPU shared memory: false") << "\n";  
        std::wcout << (accs[i].supports_double_precision ?   
            "double precision: true" : "double precision: false") << "\n";  
        std::wcout << (accs[i].supports_limited_double_precision ?   
            "limited double precision: true" : "limited double precision: false") << "\n";  
    }  
}  
```  
  
## <a name="selecting-an-accelerator"></a>アクセラレータの選択  
 アクセラレータを選択するには、`accelerator::get_all` メソッドを使用して、使用できるアクセラレータの一覧を取得し、プロパティに基づいて 1 つを選択します。 この例では、最も多くのメモリを持つアクセラレータを選択する方法を示しています。  
  
```cpp  
void pick_with_most_memory()  
{  
    std::vector<accelerator> accs = accelerator::get_all();
    accelerator acc_chosen = accs[0];  
    
    for (int i = 0; i <accs.size(); i++) {  
        if (accs[i].dedicated_memory> acc_chosen.dedicated_memory) {  
            acc_chosen = accs[i];  
        }  
    }  
 
    std::wcout << "The accelerator with the most memory is "    
        << acc_chosen.device_path << "\n"  
        << acc_chosen.dedicated_memory << ".\n";  
}  
```  
  
> [!NOTE]
>  `accelerator::get_all` によって返されるアクセラレータの 1 つが、CPU アクセラレータです。 CPU アクセラレータではコードを実行できません。 CPU アクセラレータを除外するには、値を比較、 [device_path](reference/accelerator-class.md#device_path)プロパティによって返されるアクセラレータの`accelerator::get_all`の値を持つ、 [accelerator::cpu_accelerator](reference/accelerator-class.md#cpu_accelerator)です。 詳細については、この記事で後述する「特別なアクセラレータ」のセクションを参照してください。  
  
## <a name="shared-memory"></a>共有メモリ  
 共有メモリは、CPU とアクセラレータの両方からアクセスできるメモリです。 共有メモリの使用は CPU とアクセラレータ間でのデータのコピーによるオーバーヘッドを排除するか、大幅に低下させます。 メモリは共有されますが、CPU とアクセラレータの両方から同時にアクセスすることはできず、同時にアクセスすると未定義の動作が発生します。 アクセラレータ プロパティ[supports_cpu_shared_memory](reference/accelerator-class.md#supports_cpu_shared_memory)を返します`true`アクセラレータが共有メモリをサポートしている場合、 [default_cpu_access_type](reference/accelerator-class.md#default_cpu_access_type) の既定のプロパティを取得[access_type](reference/concurrency-namespace-enums-amp.md#access_type)に割り当てられたメモリに、 `accelerator`— たとえば、`array`に関連付けられている、 `accelerator`、または`array_view`でアクセスされるオブジェクト、`accelerator`です。 
  
 C++ AMP ランタイムは、各 `access_type` に最適な既定の `accelerator` を自動的に選択しますが、CPU からの読み込み、CPU からの書き込み、またはその両方が行われる場合、共有メモリのパフォーマンス特性 (帯域幅と待機時間) は専用 (共有されない) のアクセラレータ メモリのパフォーマンス特性より悪い場合があります。 共有メモリが CPU からの読み取りと書き込みの専用メモリと同様に使用される場合、ランタイムは既定値が `access_type_read_write` となり、それ以外の場合、ランタイムは保守的な既定値 `access_type` を選択し、計算のカーネルのメモリ アクセス パターンが別の `access_type` を利用する場合は、アプリケーションがそれをオーバーライドできるようにします。  
  
 次のコード例では、既定のアクセラレータが共有メモリをサポートし、既定のアクセスの種類をオーバーライドして、そこから `accelerator_view` を作成するかどうかを確認する方法を説明します。  
  
```cpp  
#include <amp.h>  
#include <iostream>  
  
using namespace Concurrency;  
  
int main()  
{  
    accelerator acc = accelerator(accelerator::default_accelerator);  
  
    // Early out if the default accelerator doesn’t support shared memory.  
    if (!acc.supports_cpu_shared_memory)  
    {  
        std::cout << "The default accelerator does not support shared memory" << std::endl;  
        return 1;  
    }  
  
    // Override the default CPU access type.  
    acc.set_default_cpu_access_type(access_type_read_write);  
  
    // Create an accelerator_view from the default accelerator. The  
    // accelerator_view reflects the default_cpu_access_type of the  
    // accelerator it’s associated with.  
    accelerator_view acc_v = acc.default_view;  
}  
```  
  
 `accelerator_view` は、関連付けられた `default_cpu_access_type` の `accelerator` を常に反映し、その `access_type` をオーバーライドまたは変更するためのインターフェイスを提供しません。  
  
## <a name="changing-the-default-accelerator"></a>既定のアクセラレータを変更する  
 `accelerator::set_default` メソッドを呼び出して、既定のアクセラレータを変更できます。 アプリの実行ごとに既定のアクセラレータを 1 度だけ変更することができますが、コードが GPU で実行される前に変更する必要があります。 `false` を返すアクセラレータを変更するための後続の関数の呼び出し。 `parallel_for_each` の呼び出しに別のアクセラレータを使用する場合は、この記事の「複数のアクセラレータを使用する」のセクションを参照してください。 次のコード例では、既定のアクセラレータをエミュレートおよびディスプレイへの接続が行われておらず、倍精度をサポートしているアクセラレータに設定します。  
  
```cpp  
bool pick_accelerator()  
{  
    std::vector<accelerator> accs = accelerator::get_all();
    accelerator chosen_one;  
 
    auto result = std::find_if(accs.begin(), accs.end(), 
        [] (const accelerator& acc) {  
            return !acc.is_emulated && 
                acc.supports_double_precision && 
                !acc.has_display;  
        });
  
    if (result != accs.end()) {  
        chosen_one = *(result);
    }
  
    std::wcout <<chosen_one.description <<std::endl;  
    bool success = accelerator::set_default(chosen_one.device_path);
    return success;  
}  
```  
  
## <a name="using-multiple-accelerators"></a>複数のアクセラレータを使用する  
 アプリで複数のアクセラレータを使用するには、次の 2 つの方法があります。  

-   渡すことができます`accelerator_view`オブジェクトへの呼び出しを[parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each)メソッドです。  
  
-   特定の `array` オブジェクトを使用して `accelerator_view` オブジェクトを構築することができます。 C+AMP ランタイムはラムダ式のキャプチャされた `accelerator_view` オブジェクトから `array` オブジェクトを選択します。  
  
## <a name="special-accelerators"></a>特別なアクセラレータ  
 3 つの特別なアクセラレータのデバイス パスは `accelerator` クラスのプロパティとして使用できます。  
  
- [accelerator::direct3d_ref データ メンバー](reference/accelerator-class.md#direct3d_ref): このシングル スレッドのアクセラレータは、汎用的なグラフィックス カードをエミュレートするためには CPU 上でソフトウェアを使用します。 これはデバッグのために既定で使用されますが、ハードウェア アクセラレータよりも遅いため、稼働中には役に立ちません。 また、DirectX SDK と Windows SDK でのみ使用が可能で、顧客のコンピューターにインストールされることはないと思われます。 詳細については、次を参照してください。 [GPU コードのデバッグ](/visualstudio/debugger/debugging-gpu-code)です。  
  
- [accelerator::direct3d_warp データ メンバー](reference/accelerator-class.md#direct3d_warp): Streaming SIMD Extensions (SSE) を使用するマルチコア Cpu で C++ AMP コードを実行するためこのアクセラレータがフォールバック ソリューションを提供します。  
  
- [accelerator::cpu_accelerator データ メンバー](reference/accelerator-class.md#cpu_accelerator): ステージング配列を設定するため、このアクセラレータを使用することができます。 これは C++ AMP コードを実行できません。 詳細については、次を参照してください。、 [C++ AMP でステージング配列](http://go.microsoft.com/fwlink/p/?linkId=248485)ネイティブ コードのブログでの並行プログラミングに投稿します。  
  
## <a name="interoperability"></a>相互運用性  
 C++ AMP ランタイムは、相互運用性をサポートしている、`accelerator_view`クラスと、Direct3D [ID3D11Device インターフェイス](http://go.microsoft.com/fwlink/p/?linkId=248488)です。 [Create_accelerator_view](reference/concurrency-direct3d-namespace-functions-amp.md#create_accelerator_view)メソッドは、`IUnknown`インターフェイスを返す、`accelerator_view`オブジェクト。 [Get_device](http://msdn.microsoft.com/en-us/8194125e-8396-4d62-aa8a-65831dea8439)メソッドは、`accelerator_view`オブジェクトを返す、`IUknown`インターフェイスです。  
  
## <a name="see-also"></a>参照  
 [C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [GPU コードのデバッグ](/visualstudio/debugger/debugging-gpu-code)   
 [accelerator_view クラス](../../parallel/amp/reference/accelerator-view-class.md)
