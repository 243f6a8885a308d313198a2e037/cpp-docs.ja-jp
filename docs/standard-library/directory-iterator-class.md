---
title: "directory_iterator クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- filesystem/std::experimental::filesystem::directory_iterator
- filesystem/std::experimental::filesystem::_Directory_iterator::_Directory_iterator
- filesystem/std::experimental::filesystem::directory_iterator::directory_iterator
- filesystem/std::experimental::filesystem::directory_iterator::increment
- filesystem/std::experimental::filesystem::directory_iterator::operator=
- filesystem/std::experimental::filesystem::directory_iterator::operator==
- filesystem/std::experimental::filesystem::directory_iterator::operator!=
- filesystem/std::experimental::filesystem::directory_iterator::operator*
- filesystem/std::experimental::filesystem::directory_iterator::operator-&gt;
- filesystem/std::experimental::filesystem::directory_iterator::operator++
dev_langs: C++
ms.assetid: dca2ecf8-3e69-4644-a83d-705061e10cc8
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::experimental::filesystem::directory_iterator
- std::experimental::filesystem::_Directory_iterator::_Directory_iterator
- std::experimental::filesystem::directory_iterator
- std::experimental::filesystem::directory_iterator::directory_iterator
- std::experimental::filesystem::directory_iterator::increment
- std::experimental::filesystem::directory_iterator::operator=
- std::experimental::filesystem::directory_iterator::operator==
- std::experimental::filesystem::directory_iterator::operator!=
- std::experimental::filesystem::directory_iterator::operator*
- std::experimental::filesystem::directory_iterator::operator-&gt;
- std::experimental::filesystem::directory_iterator::operator++
ms.workload: cplusplus
ms.openlocfilehash: 2c490c3a56cfcff17d965a9cd635a92fff7f5a95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="directoryiterator-class"></a>directory_iterator クラス
ディレクトリのファイル名を走査する入力反復子を表します。 反復子 X の場合、式 *X の結果は、ファイル名とそのステータスに関する既知の情報をラップする directory_entry クラスのオブジェクトになります。  
  
 このクラスは、走査するディレクトリの名前を表す path 型のオブジェクト (ここでは、説明のために mydir という名前にします) と、ディレクトリ シーケンス内の現在のファイル名を表す directory_entry 型のオブジェクト (myentry という名前にします) を格納します。 既定で構築される型 directory_entry のオブジェクトは、空の mydir のパス名を持ち、end-of-sequence 反復子を表します。  
  
 たとえば、def と ghi のエントリを持つディレクトリ abc がある場合、次のコードは  
  
 `for (directory_iterator next(path("abc")), end; next != end; ++next)     visit(next->path());`  
  
 引数 path("abc/def") および path("abc/ghi") を使用して visit を呼び出します。  
  
 詳細およびコード例については、「[ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
class directory_iterator;  
```  
  
## <a name="directoryiteratordirectoryiterator"></a>directory_iterator::directory_iterator  
  
```  
directory_iterator() noexcept;  
explicit directory_iterator(const path& pval);

directory_iterator(const path& pval, error_code& ec) noexcept;  
directory_iterator(const directory_iterator&) = default;  
directory_iterator(directory_iterator&&) noexcept = default;  
```  
  
 1 つ目のコンストラクターは、end-of-sequence 反復子を生成します。 2 番目と 3 番目のコンストラクターは、mydir に pval を格納してから、mydir をディレクトリとして開いて読み取ろうとします。 成功した場合は、ディレクトリの最初のファイル名を myentry に格納し、成功しなかった場合は end-of-sequence 反復子を生成します。  
  
 既定のコンストラクターは想定どおりの動作をします。  
  
## <a name="directoryiteratorincrement"></a>directory_iterator::increment  
  
```  
directory_iterator& increment(error_code& ec) noexcept;  
```  
  
 この関数は、ディレクトリ内の次のファイル名に進もうとします。 成功した場合は、myentry にそのファイル名を格納します。成功しなかった場合は、end-of-sequence 反復子を生成します。  
  
## <a name="directoryiteratoroperator"></a>directory_iterator::operator! =  
  
```  
bool operator!=(const directory_iterator& right) const;
```  
  
 このメンバー演算子は、!(*this == right) を返します。  
  
## <a name="directoryiteratoroperator"></a>directory_iterator::operator=  
  
```  
directory_iterator& operator=(const directory_iterator&) = default;  
directory_iterator& operator=(directory_iterator&&) noexcept = default;  
```  
  
 この既定のメンバー代入演算子は想定どおりに動作します。  
  
## <a name="directoryiteratoroperator"></a>directory_iterator::operator==  
  
```  
bool operator==(const directory_iterator& right) const;
```  
  
 このメンバー演算子は、*this と right の両方が end-of-sequence 反復子の場合または両方が end-of-sequence 反復子でない場合にのみ、true を返します。  
  
## <a name="directoryiteratoroperator"></a>directory_iterator::operator*  
  
```  
const directory_entry& operator*() const;
```  
  
 このメンバー演算子は、myentry を返します。  
  
## <a name="directoryiteratoroperator-"></a>directory_iterator::operator->  
  
```  
const directory_entry * operator->() const;
```  
  
 このメンバー関数は、&**this を返します。  
  
## <a name="directoryiteratoroperator"></a>directory_iterator::operator++  
  
```  
directory_iterator& operator++();
directory_iterator& operator++(int);
```  
  
 1 つ目のメンバー関数は、increment() を呼び出してから、*this を返します。 2 つ目のメンバー関数は、オブジェクトのコピーを作成して、increment() を呼び出してから、そのコピーを返します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<experimental/filesystem>  
  
 **名前空間:** std::experimental::filesystem  
  
## <a name="see-also"></a>参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem>](../standard-library/filesystem.md)   
 [ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md)

