---
title: "名前空間の関数を Concurrency::graphics::direct3d |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11ee1d42-333e-4ae9-95ac-4cf68c06d13d
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: aa7e91237eaa9ced297e2c5748359c23bb436df8
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencygraphicsdirect3d-namespace-functions"></a>Concurrency::graphics::direct3d 名前空間の関数
||||  
|-|-|-|  
|[get_sampler 関数](#get_sampler)|[get_texture 関数](#get_texture)|[make_sampler 関数](#make_sampler)|  
|[make_texture 関数](#make_texture)|[msad4 関数](#msad4)|  
  
##  <a name="a-namegetsamplera--getsampler-function"></a><a name="get_sampler"></a>get_sampler 関数  
 指定されたサンプラー オブジェクトを表す特定のアクセラレータ ビューについて、D3D サンプラーの状態インターフェイスを取得します。  
  
```  
IUnknown* get_sampler(
    const Concurrency::accelerator_view& _Av,  
    const sampler& _Sampler) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Av`  
 D3D サンプラーの状態が作成される D3D アクセラレータ ビュー。  
  
 `_Sampler`  
 基になる D3D サンプラーの状態インターフェイスが作成されるサンプラー オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 特定のサンプラーを表す D3D サンプラーの状態に対応する IUnknown インターフェイス ポインター。  
  
##  <a name="a-namegettexturea--gettexture-function"></a><a name="get_texture"></a>get_texture 関数  
 指定した基になる Direct3D テクスチャ インターフェイスを取得[テクスチャ](texture-class.md)オブジェクトです。  
  
```  
template<
    typename value_type,  
    int _Rank  
>  
_Ret_ IUnknown *get_texture(
    const texture<value_type, _Rank>& _Texture) restrict(cpu);

 
template<
    typename value_type,  
    int _Rank  
>  
_Ret_ IUnknown *get_texture(
    const writeonly_texture_view<value_type, _Rank>& _Texture) restrict(cpu);

 
template<
    typename value_type,  
    int _Rank  
>  
_Ret_ IUnknown *get_texture(
    const texture_view<value_type, _Rank>& _Texture) restrict(cpu);

 
```  
  
### <a name="parameters"></a>パラメーター  
 `value_type`  
 テクスチャの要素型。  
  
 `_Rank`  
 テクスチャのランク。  
  
 `_Texture`  
 基になる Direct3D テクスチャ インターフェイスが返される accelerator_view に関連付けられているテクスチャまたはテクスチャ ビュー。  
  
### <a name="return-value"></a>戻り値  
 テクスチャの基になる Direct3D テクスチャに対応する IUnknown インターフェイス ポインター。  
  
##  <a name="a-namemakesamplera--makesampler-function"></a><a name="make_sampler"></a>make_sampler 関数  
 D3D サンプラーの状態インターフェイス ポインターからサンプラーを作成します。  
  
```  
sampler make_sampler(_In_ IUnknown* _D3D_sampler) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_D3D_sampler`  
 サンプラーを作成する基になる D3D サンプラーの状態の IUnknown インターフェイス ポインター。  
  
### <a name="return-value"></a>戻り値  
 サンプラーは、指定された D3D サンプラーの状態を表します。  
  
##  <a name="a-namemaketexturea--maketexture-function"></a><a name="make_texture"></a>make_texture 関数  
 作成、[テクスチャ](texture-class.md)指定されたパラメーターを使用してオブジェクトです。  
  
```  
template<
    typename value_type,  
    int _Rank  
>  
texture<value_type, _Rank> make_texture(
    const Concurrency::accelerator_view& _Av,  
    _In_ IUnknown* _D3D_texture,  
    DXGI_FORMAT _View_format = DXGI_FORMAT_UNKNOWN) restrict(cpu);
```  
  
### <a name="parameters"></a>パラメーター  
 `value_type`  
 テクスチャの要素の型。  
  
 `_Rank`  
 テクスチャのランク。  
  
 `_Av`  
 テクスチャが作成される D3D アクセラレータ ビュー。  
  
 `_D3D_texture`  
 テクスチャを作成する基になる D3D テクスチャの IUnknown インターフェイス ポインター。  
  
 `_View_format`  
 このテクスチャから作成されるビューに使用する DXGI 形式。 DXGI_FORMAT_UNKNOWN (既定値) を渡して _D3D_texture の基になる形式とこのテンプレートの value_type から形式が派生します。 用意された形式は、_D3D_texture の基になる形式との互換性が必要です。  
  
### <a name="return-value"></a>戻り値  
 用意された D3D テクスチャを使用するテクスチャ。  
  
##  <a name="a-namemsad4a--msad4-function"></a><a name="msad4"></a>msad4 関数  
 4 バイトの参照値と 8 バイトのソース値を比較し、4 個の合計値のベクターを累積します。 各合計は、参照値とソース値の異なるバイト アラインメントの差の絶対値のマスク合計に対応します。  
  
```  
inline uint4 msad4(
    uint _Reference,  
    uint2 _Source,  
    uint4 _Accum) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Reference`  
 1 個の uint 値の 4 バイトの参照配列。  
  
 `_Source`  
 2 個の uint 値のベクター内の 8 バイトのソース配列。  
  
 `_Accum`  
 参照値とソース値の異なるバイト アラインメントの差の絶対値のマスク合計に加算される 4 個の値のベクター。  
  
### <a name="return-value"></a>戻り値  
 4 つの合計のベクターを返します。 各合計は、参照値とソース値の異なるバイト アラインメントの差の絶対値のマスク合計に対応します。  
  
## <a name="see-also"></a>関連項目  
 [Concurrency::graphics::direct3d Namespace](concurrency-graphics-direct3d-namespace.md)

