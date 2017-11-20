---
title: "Concurrency::graphics 名前空間の関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_graphics/Concurrency::fast_math::copy_async
- amp_graphics/Concurrency::fast_math::copy
dev_langs: C++
ms.assetid: ace01cd5-29d3-4356-930e-c81a61c5f934
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4277b01f702807435132cd92785aefe7f3ab30f8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="concurrencygraphics-namespace-functions"></a>Concurrency::graphics 名前空間の関数
|||  
|-|-|  
|[copy](#copy)|[copy_async](#copy_async)|  
  
##  <a name="copy"></a>copy 関数 (concurrency::graphics Namespace)  
 ソースのテクスチャをターゲットのバッファーにコピーするか、またはソースのバッファーをターゲットのバッファーにコピーします。 この関数の一般的な形式は `copy(src, dest)` です。  
  
```  
template <
    typename _Src_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture, void>::type>  
>  
void copy (
    const _Src_type& _Src,  
    _Out_ void* _Dst,  
    unsigned int _Dst_byte_size);

 
template <
    typename _Src_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture, void>::type  
>  
void copy(
    const _Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset,  
    const extent<_Src_type::rank>& _Copy_extent,  
    _Out_ void* _Dst,  
    unsigned int _Dst_byte_size);

 
template <
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
void copy(
    const void* _Src,  
    unsigned int _Src_byte_size, _Dst_type& _Dst);

 
template <
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
void copy(
    const void* _Src,  
    unsigned int _Src_byte_size,  
    _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Dst_type::rank>& _Copy_extent);

 
template <
    typename InputIterator,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
void copy(InputIterator first, InputIterator last, _Dst_type& _Dst);

 
template <
    typename InputIterator,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>void copy(InputIterator first, InputIterator last, _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Dst_type::rank>& _Copy_extent);

 
template <
    typename _Src_type,  
    typename OutputIterator,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& !details::texture_traits<OutputIterator>::is_texture, void>::type  
>  
void copy(
    const _Src_type& _Src, OutputIterator _Dst);

 
template <
    typename _Src_type,  
    typename OutputIterator,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& !details::texture_traits<OutputIterator>::is_texture, void>::type  
>  
void copy (
    const _Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset,  
    const extent<_Src_type::rank>& _Copy_extent, OutputIterator _Dst);

 
template <
    typename _Src_type,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
void copy (
    const _Src_type& _Src, _Dst_type& _Dst);

 
template <
    typename _Src_type,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& details::texture_traits<_Dst_type>::is_texture,  
    void>::type 
>  
void copy (
    const _Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset, _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Src_type::rank>& _Copy_extent);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Copy_extent`  
 コピーするテクスチャのセクションの範囲。  
  
 `_Dst`  
 コピー先のオブジェクト。  
  
 `_Dst_byte_size`  
 コピー先のバイト数。  
  
 `_Dst_type`  
 コピー先のオブジェクトの型。  
  
 `_Dst_offset`  
 コピー開始位置でのコピー先へのオフセット。  
  
 `InputIterator`  
 入力列挙子の型。  
  
 `OutputIterator`  
 出力反復子の型。  
  
 `_Src`  
 コピーするオブジェクト。  
  
 `_Src_byte_size`  
 コピー元のバイト数。  
  
 `_Src_type`  
 コピー元のオブジェクトの型。  
  
 `_Src_offset`  
 コピー開始位置からのコピー元へのオフセット。  
  
 `first`  
 ソース コンテナーへの先頭の反復子。  
  
 `last`  
 ソース コンテナーへの終了の反復子。  
  
##  <a name="copy_async"></a>copy_async 関数 (concurrency::graphics Namespace)  
 コピー先のバッファーにソース テクスチャを非同期的にコピーまたは転送先のバッファーにコピー元のバッファーをコピーしてから返します、 [completion_future](completion-future-class.md)待機できるオブジェクト。 アクセラレータでコードを実行しているときにデータはコピーできません。 この関数の一般的な形式は `copy(src, dest)` です。  
  
```  
template<
    typename _Src_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(
    const _Src_type& _Src,  
    _Out_ void* _Dst,  
    unsigned int _Dst_byte_size);

 
template<
    typename _Src_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(
    const _Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset,  
    const extent<_Src_type::rank>& _Copy_extent,  
    _Out_ void* _Dst,  
    unsigned int _Dst_byte_size);

 
template <
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(
    const void* _Src,  
    unsigned int _Src_byte_size, _Dst_type& _Dst);

 
template <
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(
    const void* _Src,  
    unsigned int _Src_byte_size, _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Dst_type::rank>& _Copy_extent);

 
template <
    typename InputIterator,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(InputIterator first, InputIterator last, _Dst_type& _Dst);

 
template <
    typename InputIterator,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(InputIterator first, InputIterator last, _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Dst_type::rank>& _Copy_extent);

 
template <
    typename _Src_type,  
    typename OutputIterator,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& !details::texture_traits<OutputIterator>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(_Src_type& _Src, OutputIterator _Dst);

 
template <
    typename _Src_type,  
    typename OutputIterator,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& !details::texture_traits<OutputIterator>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(_Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset,  
    const extent<_Src_type::rank>& _Copy_extent,  
    OutputIterator _Dst);

 
template <
    typename _Src_type,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(_Src_type& _Src, _Dst_type& _Dst);

 
template <
    typename _Src_type,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(_Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset, _Dst_type &_Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Src_type::rank>& _Copy_extent);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Copy_extent`  
 コピーするテクスチャのセクションの範囲。  
  
 `_Dst`  
 コピー先のオブジェクト。  
  
 `_Dst_byte_size`  
 コピー先のバイト数。  
  
 `_Dst_type`  
 コピー先のオブジェクトの型。  
  
 `_Dst_offset`  
 コピー開始位置でのコピー先へのオフセット。  
  
 `InputIterator`  
 入力列挙子の型。  
  
 `OutputIterator`  
 出力反復子の型。  
  
 `_Src`  
 コピーするオブジェクト。  
  
 `_Src_byte_size`  
 コピー元のバイト数。  
  
 `_Src_type`  
 コピー元のオブジェクトの型。  
  
 `_Src_offset`  
 コピー開始位置からのコピー元へのオフセット。  
  
 `first`  
 ソース コンテナーへの先頭の反復子。  
  
 `last`  
 ソース コンテナーへの終了の反復子。  

## <a name="requirements"></a>要件  
 **ヘッダー:** amp_graphics.h  
  
 **Namespace:** concurrency::graphics 

## <a name="see-also"></a>関連項目  
 [Concurrency::graphics 名前空間](concurrency-graphics-namespace.md)
