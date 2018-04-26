---
title: function クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- functional/std::function
- functional/std::function::result_type
- functional/std::function::assign
- functional/std::function::swap
- functional/std::function::target
- functional/std::function::target_type
- functional/std::function::operator unspecified
- functional/std::function::operator()
dev_langs:
- C++
helpviewer_keywords:
- std::function [C++]
- std::function [C++], result_type
- std::function [C++], assign
- std::function [C++], swap
- std::function [C++], target
- std::function [C++], target_type
ms.assetid: 7b5ca76b-9ca3-4d89-8fcf-cad70a4aeae6
caps.latest.revision: 26
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 879999f279493c10509900c040ca6f5171c215b4
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="function-class"></a>function クラス

呼び出し可能オブジェクトのラッパー。

## <a name="syntax"></a>構文

```cpp
template <class Fty>
class function  // Fty of type Ret(T1, T2, ..., TN)
    : public unary_function<T1, Ret>       // when Fty is Ret(T1)
    : public binary_function<T1, T2, Ret>  // when Fty is Ret(T1, T2)
{
public:
    typedef Ret result_type;

    function();
    function(nullptr_t);
    function(const function& right);
    template <class Fty2>
        function(Fty2 fn);
    template <class Fty2, class Alloc>
        function(reference_wrapper<Fty2>, const Alloc& Ax);

    template <class Fty2, class Alloc>
        void assign(Fty2, const Alloc& Ax);
    template <class Fty2, class Alloc>
        void assign(reference_wrapper<Fty2>, const Alloc& Ax);
    function& operator=(nullptr_t);
    function& operator=(const function&);
    template <class Fty2>
        function& operator=(Fty2);
    template <class Fty2>
        function& operator=(reference_wrapper<Fty2>);

    void swap(function&);
    explicit operator bool() const;

    result_type operator()(T1, T2, ....., TN) const;
    const std::type_info& target_type() const;
    template <class Fty2>
        Fty2 *target();

    template <class Fty2>
        const Fty2 *target() const;

    template <class Fty2>
        void operator==(const Fty2&) const = delete;
    template <class Fty2>
        void operator!=(const Fty2&) const = delete;
};
```

### <a name="parameters"></a>パラメーター

`Fty` ラップする関数の型。

`Ax` アロケーター関数。

## <a name="remarks"></a>コメント

このテンプレート クラスは、呼び出しシグネチャが `Ret(T1, T2, ..., TN)` である呼び出しラッパーです。 これを使用して、同一形式のラッパーでさまざまな呼び出し可能オブジェクトを囲みます。

一部のメンバー関数は、目的のターゲット オブジェクトの名前を示すオペランドを取ります。 その場合、オペランドは次のような方法で指定できます。

`fn` - 呼び出し可能オブジェクト`fn`。呼び出しの後に、`function` オブジェクトが `fn` のコピーを保持します。

`fnref` - `fnref.get()` によって指定される呼び出し可能オブジェクト。呼び出しの後に、`function` オブジェクトが `fnref.get()` を参照します。

`right` - `function` オブジェクト `right` によって保持される呼び出し可能オブジェクト (存在する場合)

`npc`- null ポインター。呼び出し後に `function` オブジェクトは空になります。

いずれの場合でも、`INVOKE(f, t1, t2, ..., tN)` で、`f` は呼び出し可能オブジェクトであり、`t1, t2, ..., tN` それぞれ型 `T1, T2, ..., TN` の左辺値であり、整形されている必要があります。`Ret` が void ではない場合、`Ret` に変換できます。

空の `function` オブジェクトは、呼び出し可能オブジェクトまたは呼び出し可能オブジェクトへの参照を保持しません。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[function](#function)|空のラッパーまたは固定のシグネチャを持つ任意の型の呼び出し可能オブジェクトを格納するラッパーを作成します。|

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[result_type](#result_type)|格納された呼び出し可能オブジェクトの戻り値の型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[assign](#assign)|呼び出し可能オブジェクトをこの関数オブジェクトに割り当てます。|
|[swap](#swap)|2 つの呼び出し可能オブジェクトを入れ替えます。|
|[target](#target)|格納されている呼び出し可能オブジェクトが指定されたとおりに呼び出し可能かどうかをテストします。|
|[target_type](#target_type)|呼び出し可能オブジェクトの型情報を取得します。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[function::operator unspecified](#op_unspecified)|格納されている呼び出し可能オブジェクトが存在するかどうかをテストします。|
|[function::operator()](#op_call)|呼び出し可能オブジェクトを呼び出します。|
|[function::operator=](#op_eq)|格納されている呼び出し可能オブジェクトを置き換えます。|

## <a name="requirements"></a>要件

**ヘッダー:** \<functional>

**名前空間:** std

## <a name="assign"></a>  function::assign

呼び出し可能オブジェクトをこの関数オブジェクトに割り当てます。

```cpp
template <class Fx, class Alloc>
    void assign(
        Fx _Func,
        const Alloc& Ax);

template <class Fx, class Alloc>
    void assign(
        reference_wrapper<Fx> _Fnref,
        const Alloc& Ax);
```

### <a name="parameters"></a>パラメーター

`_Func` 呼び出し可能オブジェクト。

`_Fnref` 呼び出し可能オブジェクトを含む参照ラッパーです。

`Ax` アロケーター オブジェクト。

### <a name="remarks"></a>コメント

各メンバー関数は、`*this` によって保持されている `callable object` を `operand` として渡される呼び出し可能オブジェクトに置き換えます。 ストレージとアロケーターオブジェクト `Ax` の両方を割り当てます。

## <a name="function"></a>  function::function

空のラッパーまたは固定のシグネチャを持つ任意の型の呼び出し可能オブジェクトを格納するラッパーを作成します。

```cpp
function();
function(nullptr_t npc);
function(const function& right);
template <class Fx>
    function(Fx _Func);
template <class Fx>
    function(reference_wrapper<Fx> _Fnref);
template <class Fx, class Alloc>
    function(
        Fx _Func,
        const Alloc& Ax);

template <class Fx, class Alloc>
    function(
        reference_wrapper<Fx> _Fnref,
        const Alloc& Ax);
```

### <a name="parameters"></a>パラメーター

`right` コピー先の関数オブジェクト。

`Fx` 呼び出し可能オブジェクトの型。

`_Func` ラップする呼び出し可能オブジェクト。

`Alloc` アロケーターの型。

`Ax` アロケーター。

`_Fnref` ラップする呼び出し可能オブジェクトの参照。

### <a name="remarks"></a>コメント

最初の 2 つのコンストラクターは、空の `function` オブジェクトを構築します。 次の 3 つのコンストラクターは、オペランドとして渡される呼び出し可能オブジェクトを保持する `function` オブジェクトを構築します。 最後の 2 つのコンス トラクターは、アロケーター オブジェクト Ax を使用してストレージを割り当てます。

### <a name="example"></a>例

```cpp
// std__functional__function_function.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>
#include <vector>

int square(int val)
{
    return val * val;
}

class multiply_by
{
public:
    explicit multiply_by(const int n) : m_n(n) { }

    int operator()(const int x) const
    {
        return m_n * x;
    }

private:
    int m_n;
};

int main()
{

    typedef std::vector< std::function<int (int)> > vf_t;

    vf_t v;
    v.push_back(square);
    v.push_back(std::negate<int>());
    v.push_back(multiply_by(3));

    for (vf_t::const_iterator i = v.begin(); i != v.end(); ++i)
    {
        std::cout << (*i)(10) << std::endl;
    }

    std::function<int (int)> f = v[0];
    std::function<int (int)> g;

    if (f) {
        std::cout << "f is non-empty (correct)." << std::endl;
    } else {
        std::cout << "f is empty (can't happen)." << std::endl;
    }

    if (g) {
        std::cout << "g is non-empty (can't happen)." << std::endl;
    } else {
        std::cout << "g is empty (correct)." << std::endl;
    }

    return 0;
}
```

```Output
100
-10
30
f is non-empty (correct).
g is empty (correct).
```

## <a name="op_unspecified"></a>  function::operator unspecified

格納されている呼び出し可能オブジェクトが存在するかどうかをテストします。

```cpp
operator unspecified();
```

### <a name="remarks"></a>コメント

演算子は、オブジェクトが空ではない場合のみ、true の値を使用して `bool` に変換できる値を返します。 その値を使用して、オブジェクトが空かどうかをテストします。

### <a name="example"></a>例

```cpp
// std__functional__function_operator_bool.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn0;
    std::cout << std::boolalpha << "not empty == " << (bool)fn0 << std::endl;

    std::function<int (int)> fn1(neg);
    std::cout << std::boolalpha << "not empty == " << (bool)fn1 << std::endl;

    return (0);
    }
```

```Output
not empty == false
not empty == true
```

## <a name="op_call"></a>  function::operator()

呼び出し可能オブジェクトを呼び出します。

```cpp
result_type operator()(
    T1 t1,
    T2 t2, ...,
    TN tN);
```

### <a name="parameters"></a>パラメーター

`TN` N 番目の型は、引数を呼び出します。

`tN` N 番目の呼び出しの引数。

### <a name="remarks"></a>コメント

このメンバー関数は `INVOKE(fn, t1, t2, ..., tN, Ret)` を返します。ここで、`fn` は `*this` に保存されるターゲット オブジェクトです。 それを使用してラップされた呼び出し可能オブジェクトを呼び出します。

### <a name="example"></a>例

```cpp
// std__functional__function_operator_call.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn1(neg);
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "val == " << fn1(3) << std::endl;

    return (0);
    }
```

```Output
empty == false
val == -3
```

## <a name="op_eq"></a>  function::operator=

格納されている呼び出し可能オブジェクトを置き換えます。

```cpp
function& operator=(null_ptr_type npc);
function& operator=(const function& right);
template <class Fty>
    function& operator=(Fty fn);
template <class Fty>
    function& operator=(reference_wrapper<Fty> fnref);
```

### <a name="parameters"></a>パラメーター

`npc` Null ポインター定数です。

`right` コピー先の関数オブジェクト。

`fn` ラップする呼び出し可能オブジェクト。

`fnref` ラップする呼び出し可能オブジェクトの参照。

### <a name="remarks"></a>コメント

演算子はそれぞれ `*this` によって保持されている呼び出し可能オブジェクトを、オペランドとして渡された呼び出し可能オブジェクトに置き換えます。

### <a name="example"></a>例

```cpp
// std__functional__function_operator_as.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn0(neg);
    std::cout << std::boolalpha << "empty == " << !fn0 << std::endl;
    std::cout << "val == " << fn0(3) << std::endl;

    std::function<int (int)> fn1;
    fn1 = 0;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;

    fn1 = neg;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "val == " << fn1(3) << std::endl;

    fn1 = fn0;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "val == " << fn1(3) << std::endl;

    fn1 = std::cref(fn1);
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "val == " << fn1(3) << std::endl;

    return (0);
    }
```

```Output
empty == false
val == -3
empty == true
empty == false
val == -3
empty == false
val == -3
empty == false
val == -3
```

## <a name="result_type"></a>  function::result_type

格納された呼び出し可能オブジェクトの戻り値の型。

```cpp
typedef Ret result_type;
```

### <a name="remarks"></a>コメント

この typedef は、テンプレートの呼び出しシグネチャ内の型 `Ret` のシノニムです。 それを使用して、ラップされた呼び出し可能オブジェクトの戻り値の型を特定します。

### <a name="example"></a>例

```cpp
// std__functional__function_result_type.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn1(neg);
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;

    std::function<int (int)>::result_type val = fn1(3);
    std::cout << "val == " << val << std::endl;

    return (0);
    }
```

```Output
empty == false
val == -3
```

## <a name="swap"></a>  function::swap

2 つの呼び出し可能オブジェクトを入れ替えます。

```cpp
void swap(function& right);
```

### <a name="parameters"></a>パラメーター

`right` 交換する関数オブジェクト。

### <a name="remarks"></a>コメント

このメンバー関数は、 `*this` と `right` の間でターゲット オブジェクトを入れ替えます。 一定時間に実行し、例外をスローしません。

### <a name="example"></a>例

```cpp
// std__functional__function_swap.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn0(neg);
    std::cout << std::boolalpha << "empty == " << !fn0 << std::endl;
    std::cout << "val == " << fn0(3) << std::endl;

    std::function<int (int)> fn1;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << std::endl;

    fn0.swap(fn1);
    std::cout << std::boolalpha << "empty == " << !fn0 << std::endl;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "val == " << fn1(3) << std::endl;

    return (0);
    }
```

```Output
empty == false
val == -3
empty == true

empty == true
empty == false
val == -3
```

## <a name="target"></a>  function::target

格納されている呼び出し可能オブジェクトが指定されたとおりに呼び出し可能かどうかをテストします。

```cpp
template <class Fty2>
    Fty2 *target();
template <class Fty2>
    const Fty2 *target() const;
```

### <a name="parameters"></a>パラメーター

`Fty2` テスト対象の呼び出し可能オブジェクトの型。

### <a name="remarks"></a>コメント

型 `Fty2` は、引数の型 `T1, T2, ..., TN` と戻り値の型 `Ret` に対して呼び出し可能である必要があります。 `target_type() == typeid(Fty2)` の場合、メンバー テンプレート関数は、ターゲット オブジェクトのアドレスを返し、それ以外の場合は、0 を返します。

型 `Fty2` は、引数の型 `T1, T2, ..., TN` および戻り値の型 `Ret` に対して呼び出し可能であり、型 `Fty2, T1, T2, ..., TN` の左辺値 `fn, t1, t2, ..., tN` の場合、`INVOKE(fn, t1, t2, ..., tN)` が整形され、`Ret` が `void` ではない場合、`Ret` に変換可能です。

### <a name="example"></a>例

```cpp
// std__functional__function_target.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    typedef int (*Myfun)(int);
    std::function<int (int)> fn0(neg);
    std::cout << std::boolalpha << "empty == " << !fn0 << std::endl;
    std::cout << "no target == " << (fn0.target<Myfun>() == 0) << std::endl;

    Myfun *fptr = fn0.target<Myfun>();
    std::cout << "val == " << (*fptr)(3) << std::endl;

    std::function<int (int)> fn1;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "no target == " << (fn1.target<Myfun>() == 0) << std::endl;

    return (0);
    }

```

```Output
empty == false
no target == false
val == -3
empty == true
no target == true
```

## <a name="target_type"></a>  function::target_type

呼び出し可能オブジェクトの型情報を取得します。

```cpp
const std::type_info& target_type() const;
```

### <a name="remarks"></a>コメント

メンバー関数は、`*this` が空の場合、`typeid(void)` を返します。それ以外の場合 `typeid(T)` を返します。`T` はターゲット オブジェクトの型です。

### <a name="example"></a>例

```cpp
// std__functional__function_target_type.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn0(neg);
    std::cout << std::boolalpha << "empty == " << !fn0 << std::endl;
    std::cout << "type == " << fn0.target_type().name() << std::endl;

    std::function<int (int)> fn1;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "type == " << fn1.target_type().name() << std::endl;

    return (0);
    }
```

```Output
empty == false
type == int (__cdecl*)(int)
empty == true
type == void
```

## <a name="see-also"></a>関連項目

[mem_fn](../standard-library/functional-functions.md#mem_fn)<br/>
[reference_wrapper クラス](../standard-library/reference-wrapper-class.md)<br/>
