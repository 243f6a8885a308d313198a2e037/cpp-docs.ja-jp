---
title: "CStringT クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CString
- CStringT
- ATL::CStringT
- ATL.CStringT
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], in ATL
- shared classes, CStringT
- CStringT class
ms.assetid: 7cacc59c-425f-40f1-8f5b-6db921318ec9
caps.latest.revision: 33
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 9660db5ff0d41a31f7d2a4e824df4e4bdf6a00e6
ms.lasthandoff: 02/24/2017

---
# <a name="cstringt-class"></a>CStringT クラス
このクラスを表します。、`CStringT`オブジェクトです。  
  
## <a name="syntax"></a>構文  
  
```  
 
template<typename BaseType, class StringTraits>  
class CStringT :   
public CSimpleStringT<BaseType,
                      _CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>
                      ::c_bIsMFCDLLTraits>  
 
```  
  
#### <a name="parameters"></a>パラメーター  
 `BaseType`  
 String クラスの文字型。 次のいずれかの値を指定します。  
  
- `char`(ANSI 文字列を)。  
  
- `wchar_t`(Unicode 文字列を)。  
  
- **TCHAR** (の ANSI および Unicode 文字列)。  
  
 `StringTraits`  
 String クラスには、C ランタイム (CRT) ライブラリのサポートと文字列リソースがある場所が必要なかどうかを判断します。 次のいずれかの値を指定します。  
  
- **StrTraitATL<> </> ** |`char` |**TCHAR、ChTraitsCRT<> </> ** |`char` |**TCHAR > >**  
  
     クラスは、CRT のサポートとリソースの文字列によって指定されたモジュール内の検索が必要です。 `m_hInstResource` (アプリケーションのモジュールのクラスのメンバー)。  
  
- **StrTraitATL<> </> ** |`char` |**TCHAR、ChTraitsOS<> </> ** |`char` |**TCHAR > >**  
  
     クラスに、CRT のサポートおよびによって指定されたモジュール内のリソース文字列を検索は必要ありません`m_hInstResource`(アプリケーションのモジュールのクラスのメンバー)。  
  
- **StrTraitMFC<> </> ** |`char` |**TCHAR、ChTraitsCRT<> </> ** |`char` |**TCHAR > >**  
  
     クラスには、CRT のサポートと MFC の標準の検索アルゴリズムを使用してリソース文字列の検索が必要です。  
  
- **StrTraitMFC<> </> ** |`char` |**TCHAR、ChTraitsOS<> </> ** |`char` |**TCHAR > >**  
  
     クラスは、CRT のサポートおよび MFC の標準の検索アルゴリズムを使用してリソース文字列を検索には必要ありません。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CStringT::CStringT](#cstringt)|構築、`CStringT`さまざまな方法でオブジェクトです。|  
|[CStringT:: ~ CStringT](#_dtorcstringt)|`CStringT` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CStringT::AllocSysString](#allocsysstring)|割り当てる、`BSTR`から`CStringT`データ。|  
|[CStringT::AnsiToOem](#ansitooem)|ANSI 文字セットを OEM 文字セットからのインプレース変換を使用できます。|  
|[CStringT::AppendFormat](#appendformat)|書式付きデータを追加すると、既存`CStringT`オブジェクトです。|  
|[CStringT::Collate](#collate)|(大文字と小文字がロケールに固有の情報に、2 つの文字列を比較します。|  
|[CStringT::CollateNoCase](#collatenocase)|2 つの文字列 (ロケール固有の情報、大文字小文字を区別) を比較します。|  
|[CStringT::Compare](#compare)|2 つの文字列 (大文字小文字を区別) を比較します。|  
|[CStringT::CompareNoCase](#comparenocase)|2 つの文字列 (大文字と小文字) を比較します。|  
|[CStringT::Delete](#delete)|文字列から文字を削除します。|  
|[CStringT::Find](#find)|文字または文字列内の部分文字列を検索します。|  
|[CStringT::FindOneOf](#findoneof)|セットから最初の一致する文字を検索します。|  
|[CStringT::Format](#format)|文字列として書式設定`sprintf`です。|  
|[CStringT::FormatMessage](#formatmessage)|メッセージ文字列の書式を設定します。|  
|[CStringT::FormatMessageV](#formatmessagev)|可変個引数リストを使用してメッセージ文字列の書式を設定します。|  
|[CStringT::FormatV](#formatv)|可変個引数リストを使用して、文字列の書式を設定します。|  
|[CStringT::GetEnvironmentVariable](#getenvironmentvariable)|文字列を指定された環境変数の値に設定します。|  
|[CStringT::Insert](#insert)|単一の文字または部分文字列を文字列内の指定したインデックス位置に挿入します。|  
|[CStringT::Left](#left)|文字列の左側の部分を抽出します。|  
|[CStringT::LoadString](#loadstring)|既存のロード`CStringT`Windows リソースからのオブジェクト。|  
|[CStringT::MakeLower](#makelower)|この文字列を小文字のすべての文字に変換します。|  
|[CStringT::MakeReverse](#makereverse)|文字列を反転させます。|  
|[CStringT::MakeUpper](#makeupper)|この文字列を大文字のすべての文字に変換します。|  
|[CStringT::Mid](#mid)|文字列の中央部を抽出します。|  
|[CStringT::OemToAnsi](#oemtoansi)|OEM 文字セットを ANSI 文字セットからのインプレース変換を使用できます。|  
|[CStringT::Remove](#remove)|削除には、文字列から文字が示されます。|  
|[CStringT::Replace](#replace)|置換には、その他の文字を含むが示されます。|  
|[CStringT::ReverseFind](#reversefind)|文字列内の文字を検索します。末尾から開始します。|  
|[CStringT::Right](#right)|文字列の右側の部分を抽出します。|  
|[名称](#setsysstring)|既存の設定`BSTR`のデータを`CStringT`オブジェクトです。|  
|[CStringT::SpanExcluding](#spanexcluding)|識別される文字のセットに含まれていない最初の文字で始まる文字列から文字を抽出`pszCharSet`します。|  
|[CStringT::SpanIncluding](#spanincluding)|セット内の文字のみを含む部分文字列を抽出します。|  
|[CStringT::Tokenize](#tokenize)|抽出では、対象の文字列でトークンを指定します。|  
|[CStringT::Trim](#trim)|文字列から先頭および末尾の空白文字がすべてを削除します。|  
|[CStringT::TrimLeft](#trimleft)|文字列の先頭の空白文字を削除します。|  
|[CStringT::TrimRight](#trimright)|末尾の空白文字の文字列を削除します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 =](#operator_eq)|新しい値を代入する`CStringT`オブジェクトです。|  
|[CStringT::operator +](#operator_add)|2 つの文字列または文字と文字列を連結します。|  
|[CStringT::operator + = 演算子](#operator_add_eq)|既存の文字列の末尾に新しい文字列を連結します。|  
|[CStringT::operator = =](#operator_eq_eq)|2 つの文字列が論理的に等しいかどうかを決定します。|  
|[CStringT::operator! =](#operator_neq)|2 つの文字列が等しい論理的にないかどうかを判断します。|  
|[CStringT::operator&lt;](#operator_lt)|演算子の左辺の文字列がより小さいかどうかを判断右側にある文字列。|  
|[CStringT::operator&gt;](#operator_gt)|演算子の左側にある文字列が右側にある文字列より大きいかどうかを判断します。|  
|[CStringT::operator&lt;=](#operator_lt_eq)|演算子の左側にある文字列が右側にある文字列以下かどうかを判断します。|  
|[CStringT::operator&gt;=](#operator_gt_eq)|演算子の左側にある文字列が右側にある文字列以上かを判断します。|  
  
## <a name="remarks"></a>コメント  
 `CStringT`継承[CSimpleStringT クラス](../../atl-mfc-shared/reference/csimplestringt-class.md)します。 文字の操作、並べ替え、および検索などの高度な機能がによって実装される`CStringT`します。  
  
> [!NOTE]
> `CStringT`オブジェクトでは、例外をスローできます。 これが発生したときに、`CStringT`オブジェクトが何らかの理由がメモリ不足です。  
  
 A`CStringT`オブジェクトは、文字の可変長シーケンスで構成されます。 `CStringT`関数と Basic に似た構文を使用する演算子を提供します。 文字列連結演算子および比較演算子は、簡略化されたメモリ管理、と共に作成`CStringT`オブジェクトの通常の文字配列より簡単に使用します。  
  
> [!NOTE]
>  作成することができますが`CStringT`を含むインスタンスには、null 文字が埋め込まれているはお勧めしています。 メソッドと演算子を呼び出すことで`CStringT`埋め込まれた null 文字が含まれているオブジェクトは、意図しない結果を生成することです。  
  
 さまざまな組み合わせを使用して、`BaseType`と`StringTraits`パラメーター`CStringT`ことができますが、次の種類にはあらかじめ定義されています ATL ライブラリでのオブジェクトします。  
  
 ATL アプリケーションを使用する場合  
  
 `CString`、 `CStringA`、および`CStringW`(MFC90 MFC DLL からエクスポートされます。DLL) に Dll のユーザーからことはありません。 これは回避するため`CStringT`乗数値 に定義されているからです。  
  
> [!NOTE]
>  エクスポートするときに、リンカー エラーが発生した場合、`CString`の MFC 拡張 DLL では、Visual C .NET 2002 からクラスを派生し、回避策を適用して、サポート技術情報の記事「リンク エラー時に、インポート CString-Derived クラス」(Q309801)」の説明に従ってこれは Visual C .NET 2003 で修正されたために、回避策のコードを削除する必要があります。 MSDN ライブラリ cd-rom またはでは、サポート技術情報の記事を検索できます[http://support.microsoft.com/support](http://support.microsoft.com/support)します。  
  
 次の文字列型は、MFC ベースのアプリケーション内で使用できます。  
  
|CStringT 型|宣言|  
|-------------------|-----------------|  
|`CStringA`|ANSI 文字は、CRT のサポートを持つ文字列を入力します。|  
|`CStringW`|Unicode 文字では、CRT のサポートを持つ文字列を入力します。|  
|`CString`|ANSI と Unicode 文字型の CRT のサポート。|  
  
 次の文字列で使用できる種類はプロジェクトの場所**ATL_CSTRING_NO_CRT**が定義されています。  
  
|CStringT 型|宣言|  
|-------------------|-----------------|  
|**CAtlStringA**|ANSI 文字は、CRT サポートのない文字列を入力します。|  
|**CAtlStringW**|Unicode 文字では、CRT サポートのない文字列を入力します。|  
|**CAtlString**|CRT をサポートしていない ANSI と Unicode 文字型。|  
  
 次の文字列で使用できる種類はプロジェクトの場所**ATL_CSTRING_NO_CRT**が定義されていません。  
  
|CStringT 型|宣言|  
|-------------------|-----------------|  
|**CAtlStringA**|ANSI 文字は、CRT のサポートを持つ文字列を入力します。|  
|**CAtlStringW**|Unicode 文字では、CRT のサポートを持つ文字列を入力します。|  
|**CAtlString**|ANSI と Unicode 文字型の CRT のサポート。|  
  
 `CString`オブジェクトは、次の特徴もあります。  
  
- `CStringT`オブジェクトは、連結演算の結果として拡張可能です。  
  
- `CStringT`オブジェクトは従います"セマンティクスを value"です。 考えてみてください、`CStringT`オブジェクトとして文字列へのポインターではなく、実際の文字列として。  
  
-   自由に置き換えることができます`CStringT`するオブジェクトを`PCXSTR`関数の引数。  
  
-   文字列バッファーに対してカスタム メモリ管理します。 詳細については、次を参照してください。[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)します。  
  
## <a name="cstringt-predefined-types"></a>CStringT 組み込み型  
 `CStringT`テンプレート引数を使用して、文字の種類の定義 (どちらか[wchar_t](../../c-runtime-library/standard-types.md)または[char](../../c-runtime-library/standard-types.md)) がサポートされてメソッドのパラメーターの型が複雑になります。 定義済みの型の一連の定義し、全体で使用されるこの問題を簡略化、`CStringT`クラスです。 次の表に、さまざまな種類を示します。  
  
|名前|説明|  
|----------|-----------------|  
|`XCHAR`|単一の文字 (どちらか`wchar_t`または`char`) と同じ文字型を持つ、`CStringT`オブジェクトです。|  
|**YCHAR**|単一の文字 (どちらか`wchar_t`または`char`) と反対の文字型を持つ、`CStringT`オブジェクトです。|  
|`PXSTR`|文字の文字列へのポインター (どちらか`wchar_t`または`char`) と同じ文字型を持つ、`CStringT`オブジェクトです。|  
|**PYSTR**|文字の文字列へのポインター (どちらか`wchar_t`または`char`) と反対の文字型を持つ、`CStringT`オブジェクトです。|  
|`PCXSTR`|ポインター、 **const**文字の文字列 (どちらか`wchar_t`または`char`) と同じ文字型を持つ、`CStringT`オブジェクトです。|  
|**PCYSTR**|ポインター、 **const**文字の文字列 (どちらか`wchar_t`または`char`) と反対の文字型を持つ、`CStringT`オブジェクトです。|  
  
> [!NOTE]
>  以前のドキュメント化されていないメソッドを使用するコード`CString`(よう**AssignCopy**) の次のドキュメント化されたメソッドを使用するコードに置き換える必要があります`CStringT`(など`GetBuffer`または`ReleaseBuffer`)。 これらのメソッドを継承`CSimpleStringT`します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)  
  
 `CStringT`  
  
## <a name="requirements"></a>要件  
  
|Header|を使用します。|  
|------------|-------------|  
|cstringt.h|MFC 専用の文字列オブジェクト|  
|atlstr.h|非 MFC の string オブジェクト|  
  
##  <a name="a-nameallocsysstringa--cstringtallocsysstring"></a><a name="allocsysstring"></a>CStringT::AllocSysString  
 型のオートメーションと互換性のある文字列を割り当てます`BSTR`の内容をコピーし、`CStringT`終端の null 文字を含む、そこにオブジェクトです。  
  
```  
BSTR AllocSysString() const;  
```  
  
### <a name="return-value"></a>戻り値  
 新しく割り当てられた文字列です。  
  
### <a name="remarks"></a>コメント  
 MFC プログラムで、[関数クラス](../../mfc/reference/cmemoryexception-class.md)が、十分なメモリが存在する場合にスローされます。 ATL のプログラムで、 [CAtlException](../../atl/reference/catlexception-class.md)がスローされます。 この関数は通常、オートメーションで文字列を返すに使用します。  
  
 一般的には、この文字列は、COM 関数に渡される場合は [in] としてパラメーターで文字列を解放する呼び出し元が必要です。 使用してこれ行う[SysFreeString](http://msdn.microsoft.com/en-us/8f230ee3-5f6e-4cb9-a910-9c90b754dcd3)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 詳細については、次を参照してください。[割り当てと解放するメモリの BSTR を](../../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md)します。  
  
 Windows での OLE 割り当て関数の詳細については、次を参照してください。 [SysAllocString](http://msdn.microsoft.com/en-us/9e0437a2-9b4a-4576-88b0-5cb9d08ca29b)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次の例は、`CStringT::AllocSysString` の使い方を示しています。  
  
 [!code-cpp[NVC_ATLMFC_Utilities #&105;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_1.cpp)]  
  
##  <a name="a-nameansitooema--cstringtansitooem"></a><a name="ansitooem"></a>CStringT::AnsiToOem  
 これですべての文字変換`CStringT`は ANSI 文字セットに OEM 文字セットからのオブジェクト。  
  
```  
void AnsiToOem();
```  
  
### <a name="remarks"></a>コメント  
 この関数は使用できない場合`_UNICODE`が定義されています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&106;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_2.cpp)]  
  
##  <a name="a-nameappendformata--cstringtappendformat"></a><a name="appendformat"></a>CStringT::AppendFormat  
 書式付きデータを追加すると、既存`CStringT`オブジェクトです。  
  
```  
void __cdecl AppendFormat(PCXSTR pszFormat, [, argument] ...);
void __cdecl AppendFormat(UINT nFormatID, [, argument] ...);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszFormat`  
 コントロールの書式設定文字列。  
  
 `nFormatID`  
 コントロールの書式設定文字列を含む文字列リソースの識別子です。  
  
 `argument`  
 省略可能な引数。  
  
### <a name="remarks"></a>コメント  
 この関数の書式化して、一連の文字や値を追加、`CStringT`です。 各オプションの引数 (存在する場合) が変換されに対応する書式指定に応じて追加`pszFormat`によって識別される文字列リソースまたは`nFormatID`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&107;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_3.cpp)]  
  
##  <a name="a-namecollatea--cstringtcollate"></a><a name="collate"></a>CStringT::Collate  
 汎用テキスト関数を使用して&2; つの文字列を比較`_tcscoll`します。  
  
```  
int Collate(PCXSTR psz) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `psz`  
 その他の文字列の比較に使用します。  
  
### <a name="return-value"></a>戻り値  
 文字列が同じですが、 < 0="" if="" this=""> `CStringT`オブジェクトより小さい`psz`、または > 0 の場合は、この`CStringT`オブジェクトがより大きい`psz`します。  
  
### <a name="remarks"></a>コメント  
 汎用テキスト関数`_tcscoll`TCHAR で定義されています。H にマップするか、 `strcoll`、 `wcscoll`、または`_mbscoll`コンパイル時に定義されている文字セットによって異なります。 各関数は、使用中で現在のコード ページに基づいて文字列の大文字小文字の区別の比較を実行します。 詳細については、次を参照してください。 [strcoll、wcscoll、_mbscoll、_strcoll_l、_wcscoll_l、_mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)します。  
  
##  <a name="a-namecollatenocasea--cstringtcollatenocase"></a><a name="collatenocase"></a>CStringT::CollateNoCase  
 汎用テキスト関数を使用して&2; つの文字列を比較`_tcscoll`します。  
  
```  
int CollateNoCase(PCXSTR psz) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `psz`  
 その他の文字列の比較に使用します。  
  
### <a name="return-value"></a>戻り値  
 文字列が一致している場合は 0 (大文字)、 < 0="" if="" this=""> `CStringT`オブジェクトより小さい`psz`(大文字)、または > 0 の場合は、この`CStringT`オブジェクトがより大きい`psz`(大文字と小文字)。  
  
### <a name="remarks"></a>コメント  
 汎用テキスト関数`_tcscoll`TCHAR で定義されています。H にマップするか、 `stricoll`、 `wcsicoll`、または`_mbsicoll`コンパイル時に定義されている文字セットによって異なります。 各関数は、現在使用されているコード ページに従って、文字列の小文字を区別しない比較を実行します。 詳細については、次を参照してください。 [strcoll、wcscoll、_mbscoll、_strcoll_l、_wcscoll_l、_mbscoll_l](../../c-runtime-library/reference/strcoll-wcscoll-mbscoll-strcoll-l-wcscoll-l-mbscoll-l.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&109;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_4.cpp)]  
  
##  <a name="a-namecomparea--cstringtcompare"></a><a name="compare"></a>CStringT::Compare  
 2 つの文字列 (大文字小文字を区別) を比較します。  
  
```  
int Compare(PCXSTR psz) const; 
```  
  
### <a name="parameters"></a>パラメーター  
 `psz`  
 その他の文字列の比較に使用します。  
  
### <a name="return-value"></a>戻り値  
 文字列が同じですが、 < 0="" if="" this=""> `CStringT`オブジェクトより小さい`psz`、または > 0 の場合は、この`CStringT`オブジェクトがより大きい`psz`します。  
  
### <a name="remarks"></a>コメント  
 汎用テキスト関数`_tcscmp`TCHAR で定義されています。H にマップするか、 `strcmp`、 `wcscmp`、または`_mbscmp`コンパイル時に定義されている文字セットによって異なります。 各関数は、文字列を区別する比較を実行し、ロケールの影響を受けません。 詳細については、次を参照してください。 [strcmp、wcscmp、_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)します。  
  
 文字列に埋め込まれた null が含まれている場合の比較の目的で、文字列と見なされます最初の埋め込まれた null 文字で切り捨てられます。  
  
### <a name="example"></a>例  
 次の例は、`CStringT::Compare` の使い方を示しています。  
  
 [!code-cpp[NVC_ATLMFC_Utilities #&110;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_5.cpp)]  
  
##  <a name="a-namecomparenocasea--cstringtcomparenocase"></a><a name="comparenocase"></a>CStringT::CompareNoCase  
 2 つの文字列 (大文字と小文字) を比較します。  
  
```  
int CompareNoCase(PCXSTR psz) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `psz`  
 その他の文字列の比較に使用します。  
  
### <a name="return-value"></a>戻り値  
 文字列が一致している場合は&0; (大文字)、 <0 if="" this=""></0> `CStringT`オブジェクトより小さい`psz`(大文字)、または >&0; (ゼロ) の場合は、この`CStringT`オブジェクトがより大きい`psz`(大文字と小文字)。  
  
### <a name="remarks"></a>コメント  
 汎用テキスト関数`_tcsicmp`TCHAR で定義されています。H にマップするか、 `_stricmp`、`_wcsicmp`または`_mbsicmp`コンパイル時に定義されている文字セットによって異なります。 各関数では、文字列の小文字を区別しない比較を実行します。 比較によって異なります、 `LC_CTYPE` 、ロケールの側面が`LC_COLLATE`です。 詳細については、次を参照してください。 [_stricmp、_wcsicmp、_mbsicmp、_stricmp_l、_wcsicmp_l、_mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&111;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_6.cpp)]  
  
##  <a name="a-namecstringta--cstringtcstringt"></a><a name="cstringt"></a>CStringT::CStringT  
 `CStringT` オブジェクトを構築します。  
  
```  
CStringT() throw() :   
    CThisSimpleString(StringTraits::GetDefaultManager());
 
explicit CStringT(IAtlStringMgr* pStringMgr) throw() :   
    CThisSimpleString( pStringMgr); 

CStringT(const VARIANT& varSrc);
 
CStringT(const VARIANT& varSrc, IAtlStringMgr* pStringMgr);
 
CStringT(const CStringT& strSrc) :   
    CThisSimpleString( strSrc);

 operator CSimpleStringT<
                    BaseType, 
                    !_CSTRING_IMPL_::_MFCDLLTraitsCheck<BaseType, StringTraits>
                    :: c_bIsMFCDLLTraits> &()  
 
template <bool bMFCDLL>  
CStringT(const CSimpleStringT<BaseType, bMFCDLL>& strSrc) :   
    CThisSimpleString( strSrc);
 
template <class SystemString>  
CStringT(SystemString^ pString) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(const XCHAR* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CSTRING_EXPLICIT CStringT(const YCHAR* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(LPCSTR pszSrc, IAtlStringMgr* pStringMgr) :   
    CThisSimpleString( pStringMgr);
 
CStringT(LPCWSTR pszSrc, IAtlStringMgr* pStringMgr) :   
    CThisSimpleString( pStringMgr);
 
CSTRING_EXPLICIT CStringT(const unsigned char* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
/*CSTRING_EXPLICIT*/ CStringT(char* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CSTRING_EXPLICIT CStringT(unsigned char* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CSTRING_EXPLICIT CStringT(wchar_t* pszSrc) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(const unsigned char* pszSrc, IAtlStringMgr* pStringMgr) :   
    CThisSimpleString( pStringMgr);
 
CSTRING_EXPLICIT CStringT(char ch, int nLength = 1) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CSTRING_EXPLICIT CStringT(wchar_t ch, int nLength = 1) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(const XCHAR* pch, int nLength) :   
    CThisSimpleString( pch, nLength, StringTraits::GetDefaultManager());
 
CStringT(const YCHAR* pch, int nLength) :   
    CThisSimpleString( StringTraits::GetDefaultManager());
 
CStringT(const XCHAR* pch, int nLength, AtlStringMgr* pStringMgr) :   
    CThisSimpleString( pch, nLength, pStringMgr);
 
CStringT(const YCHAR* pch, int nLength, IAtlStringMgr* pStringMgr) :   
    CThisSimpleString( pStringMgr);
```  
  
### <a name="parameters"></a>パラメーター  
 `pch`  
 長さの文字の配列へのポインター `nLength`、null 終端できます。  
  
 `nLength`  
 内の文字の数のカウント`pch`します。  
  
 `ch`  
 1 文字です。  
  
 `pszSrc`  
 これにコピーされる null で終わる文字列`CStringT`オブジェクトです。  
  
 `pStringMgr`  
 メモリ マネージャーへのポインター、`CStringT`オブジェクトです。 詳細については`IAtlStringMgr`とメモリ管理を`CStringT`を参照してください[CStringT によるメモリ管理](../../atl-mfc-shared/memory-management-with-cstringt.md)します。  
  
 `strSrc`  
 既存の`CStringT`オブジェクトにコピーされる`CStringT`オブジェクトです。 詳細については`CThisString`と`CThisSimpleString`、「解説」セクションを参照してください。  
  
 `varSrc`  
 これにコピーされる variant オブジェクト`CStringT`オブジェクトです。  
  
 `BaseType`  
 String クラスの文字型。 次のいずれかの値を指定します。  
  
 `char`(ANSI 文字列を)。  
  
 `wchar_t`(Unicode 文字列を)。  
  
 `TCHAR`(ANSI と Unicode 文字列を)。  
  
 `bMFCDLL`  
 プロジェクトが MFC DLL (TRUE) であるかどうかを指定するブール値 (FALSE)。  
  
 `SystemString`  
 必要があります`System::String`、および/clr でプロジェクトをコンパイルする必要があります。  
  
 `pString`  
 ハンドル、`CStringT`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 コンス トラクターは、入力データを新しい割り当て済み記憶域にコピー、するために注意してくださいメモリ不足の例外が発生する可能性があります。 変換関数として機能するこれらのコンス トラクターのいくつか注意してください。 置き換えるには、たとえば、これにより、`LPTSTR`場所、`CStringT`オブジェクトが必要です。  
  
- `CStringT`( `LPCSTR` `lpsz` ): Unicode の構築`CStringT`ANSI 文字列から。 このコンス トラクターは次の例で示すように文字列リソースの読み込みに使用することもできます。  
  
- `CStringT(``LPCWSTR` `lpsz` ): を構築、 `CStringT` Unicode 文字列からです。  
  
- `CStringT`( `const unsigned char*` `psz` ): 構築できるように、`CStringT`へのポインターから`unsigned char`します。  
  
> [!NOTE]
>  定義、 **_CSTRING_DISABLE_NARROW_WIDE_CONVERSION**マクロの間で文字列の暗黙的な変換をオフにする[!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)]と[!INCLUDE[TLA#tla_unicode](../../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)]文字列。 マクロは、変換をサポートするコンス トラクターをコンパイルから除外します。  
  
 なお、`strSrc`パラメーターには、いずれかを指定できます、`CStringT`または`CThisSimpleString`オブジェクトです。 `CStringT`、その既定のインスタンス化のいずれか ( `CString`、 `CStringA`、または`CStringW`); の`CThisSimpleString`を使用して、`this`ポインター。 `CThisSimpleString`インスタンスが宣言されて、 [CSimpleStringT クラス](../../atl-mfc-shared/reference/csimplestringt-class.md)よりも小さい組み込みの機能を持つ小さな文字列クラスは、`CStringT`クラスです。  
  
 オーバー ロードされた演算子`CSimpleStringT<>&()`を構築、`CStringT`オブジェクトから、`CSimpleStringT`宣言します。  
  
> [!NOTE]
>  作成することができますが`CStringT`を含むインスタンスには、null 文字が埋め込まれているはお勧めしています。 メソッドと演算子を呼び出すことで`CStringT`埋め込まれた null 文字が含まれているオブジェクトは、意図しない結果を生成することです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&112;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_7.cpp)]  
  
##  <a name="a-namedtorcstringta--cstringtcstringt"></a><a name="_dtorcstringt"></a>CStringT:: ~ CStringT  
 `CStringT` オブジェクトを破棄します。  
  
```  
~CStringT() throw();
```  
  
### <a name="remarks"></a>コメント  
 `CStringT` オブジェクトを破棄します。  
  
##  <a name="a-namedeletea--cstringtdelete"></a><a name="delete"></a>CStringT::Delete  
 指定したインデックス位置にある文字で始まる文字列から文字を削除します。  
  
```  
int Delete(int iIndex, int nCount = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 `iIndex`  
 最初の文字の&0; から始まるインデックス、`CStringT`を削除するオブジェクト。  
  
 `nCount`  
 削除する文字数。  
  
### <a name="return-value"></a>戻り値  
 変更後の文字列の長さ。  
  
### <a name="remarks"></a>コメント  
 場合`nCount`文字列、文字列の残りの部分が削除ではありません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&113;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_8.cpp)]  
  
```Output  
Before: Soccer is best,
    but hockey is quicker!  
After: Soccer best,
    but hockey is quicker!  
```  
  
##  <a name="a-namefinda--cstringtfind"></a><a name="find"></a>CStringT::Find  
 文字または部分文字列の最初の一致にこの文字列を検索します。  
  
```  
int Find(PCXSTR pszSub, int iStart=0) const throw();
int Find(XCHAR ch, int iStart=0) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszSub`  
 検索する部分文字列。  
  
 `iStart`  
 では、検索を開始する文字列または最初から開始する場合は 0 で文字のインデックス。  
  
 `ch`  
 検索する&1; つの文字。  
  
### <a name="return-value"></a>戻り値  
 この最初の文字の&0; から始まるインデックス`CStringT`で部分文字列または文字が見つからない場合は-1。 要求された部分文字列または文字に一致するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 両方の単一の文字を受け入れるように、関数がオーバー ロード (ランタイム関数と似ています`strchr`) と文字列 (のような`strstr`)。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&114;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_9.cpp)]  
  
##  <a name="a-namefindoneofa--cstringtfindoneof"></a><a name="findoneof"></a>CStringT::FindOneOf  
 この文字列に含まれている任意の文字と一致する最初の文字を検索`pszCharSet`します。  
  
```  
int FindOneOf(PCXSTR pszCharSet) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszCharSet`  
 検索用に文字を含む文字列です。  
  
### <a name="return-value"></a>戻り値  
 この文字列の最初の文字の&0; から始まるインデックス`pszCharSet`; が一致しない場合は –&1; です。  
  
### <a name="remarks"></a>コメント  
 内の文字のいずれかの最初に見つかった`pszCharSet`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&115;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_10.cpp)]  
  
##  <a name="a-nameformata--cstringtformat"></a><a name="format"></a>CStringT::Format  
 書式付きデータを書き込みます、 `CStringT` 、同じ方法[sprintf_s](../../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md) C スタイルの文字配列にデータを書式設定します。  
  
```  
void __cdecl Format(UINT nFormatID, [, argument]...);
void __cdecl Format(PCXSTR pszFormat,  [, argument] ...);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFormatID`  
 コントロールの書式設定文字列を含む文字列リソースの識別子です。  
  
 `pszFormat`  
 コントロールの書式設定文字列。  
  
 `argument`  
 省略可能な引数。  
  
### <a name="remarks"></a>コメント  
 この関数は、書式設定し、一連の文字や値の保存、`CStringT`です。 各オプションの引数 (存在する場合) が変換されに対応する書式指定に応じて`pszFormat`によって識別される文字列リソースまたは`nFormatID`です。  
  
 文字列オブジェクト自体がパラメーターとして提供されている場合、呼び出しは失敗`Format`します。 たとえば、次のコードは、予期しない結果になります。  
  
 [!code-cpp[NVC_ATLMFC_Utilities&116; 位](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_11.cpp)]  
  
 詳細については、「[書式指定構文: printf 関数と wprintf 関数](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)」をご覧ください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&117;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_12.cpp)]  
  
##  <a name="a-nameformatmessagea--cstringtformatmessage"></a><a name="formatmessage"></a>CStringT::FormatMessage  
 メッセージ文字列の書式を設定します。  
  
```  
void __cdecl FormatMessage(UINT nFormatID, [, argument]...);
void __cdecl FormatMessage(PCXSTR pszFormat, [, argument]...);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFormatID`  
 書式設定されていないメッセージのテキストを含んでいる文字列リソースの識別子です。  
  
 `pszFormat`  
 コントロールの書式設定文字列を指します。 挿入のためのスキャン、それに従って書式設定されます。 書式指定文字列は、ランタイム関数に似た`printf`-なパラメーターが任意の順序で挿入できることを除いて書式指定文字列のスタイルを設定します。  
  
 `argument`  
 省略可能な引数。  
  
### <a name="remarks"></a>コメント  
 関数には、入力としてメッセージの定義が必要です。 メッセージ定義によって決定される`pszFormat`によって識別される文字列リソースまたは`nFormatID`です。 関数は、書式設定されたメッセージ テキストをコピー、`CStringT`オブジェクト、埋め込まれているいずれかの処理が要求された場合、シーケンスを挿入します。  
  
> [!NOTE]
> `FormatMessage`新しい形式の文字列のシステム メモリを割り当てようとします。 この試行が失敗すると、自動的にメモリ不足例外がスローされます。  
  
 挿入ごとに対応するパラメーター以下を持つ必要があります、`pszFormat`または`nFormatID`パラメーター。 メッセージ テキストには、いくつかのエスケープ シーケンスは、メッセージを動的に書式設定するためサポートされています。 詳細については、Windows を参照してください。 [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351)で機能、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&118;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_13.cpp)]  
  
##  <a name="a-nameformatmessageva--cstringtformatmessagev"></a><a name="formatmessagev"></a>CStringT::FormatMessageV  
 可変個引数リストを使用してメッセージ文字列の書式を設定します。  
  
```  
void FormatMessageV(PCXSTR pszFormat, va_list* pArgList);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszFormat`  
 コントロールの書式設定文字列を指します。 挿入のためのスキャン、それに従って書式設定されます。 書式指定文字列は、ランタイム関数に似た`printf`-なパラメーターが任意の順序で挿入できることを除いて書式指定文字列のスタイルを設定します。  
  
 `pArgList`  
 引数リストへのポインター。  
  
### <a name="remarks"></a>コメント  
 関数に必要な入力値としてメッセージの定義によって決まります`pszFormat`します。 関数は、形式のメッセージ テキストとする引数の変数の一覧をコピー、`CStringT`オブジェクト、埋め込まれているいずれかの処理が要求された場合、シーケンスを挿入します。  
  
> [!NOTE]
> `FormatMessageV`呼び出し[CStringT::FormatMessage](#formatmessage)、新しい形式の文字列のシステム メモリの割り当てにされます。 この試行が失敗すると、自動的にメモリ不足例外がスローされます。  
  
 詳細については、Windows を参照してください。 [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351)で機能、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameformatva--cstringtformatv"></a><a name="formatv"></a>CStringT::FormatV  
 可変個引数リストを使用してメッセージ文字列の書式を設定します。  
  
```  
void FormatV(PCXSTR pszFormat, va_list args);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszFormat`  
 コントロールの書式設定文字列を指します。 挿入のためのスキャン、それに従って書式設定されます。 書式指定文字列は、ランタイム関数に似た`printf`-なパラメーターが任意の順序で挿入できることを除いて書式指定文字列のスタイルを設定します。  
  
 `args`  
 引数リストへのポインター。  
  
### <a name="remarks"></a>コメント  
 書式設定された文字列と引数の変数のリストを書き込み、 `CStringT` 、同じ文字列方法`vsprintf_s`C スタイルの文字配列にデータを書式設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&119;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_14.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities #&120;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_15.cpp)]  
  
##  <a name="a-namegetenvironmentvariablea--cstringtgetenvironmentvariable"></a><a name="getenvironmentvariable"></a>CStringT::GetEnvironmentVariable  
 文字列を指定された環境変数の値に設定します。  
  
```  
BOOL GetEnvironmentVariable(PCXSTR pszVar);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszVar`  
 環境変数を指定する null で終わる文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出し元プロセスの環境ブロックから、指定された変数の値を取得します。 値は、文字の null で終わる文字列の形式でです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&121;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_16.cpp)]  
  
##  <a name="a-nameinserta--cstringtinsert"></a><a name="insert"></a>CStringT::Insert  
 単一の文字または部分文字列を文字列内の指定したインデックス位置に挿入します。  
  
```  
int Insert(int iIndex, PCXSTR psz);
int Insert(int iIndex, XCHAR ch);
```  
  
### <a name="parameters"></a>パラメーター  
 `iIndex`  
 位置の前に、挿入が行われます文字のインデックス。  
  
 `psz`  
 挿入する部分文字列へのポインター。  
  
 `ch`  
 挿入する文字。  
  
### <a name="return-value"></a>戻り値  
 変更後の文字列の長さ。  
  
### <a name="remarks"></a>コメント  
 `iIndex`パラメーターが文字または部分文字列を確保するために移動する最初の文字を識別します。 場合`nIndex`0 の場合は、文字列全体の前に、挿入が発生します。 場合`nIndex`が、関数、文字列の長さが現在の文字列に連結され、いずれかで新しいマテリアルが提供されるよりも大きい`ch`または`psz`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&122;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_17.cpp)]  
  
##  <a name="a-namelefta--cstringtleft"></a><a name="left"></a>CStringT::Left  
 この `nCount` オブジェクトから左端の `CStringT` 文字を抽出し、抽出された部分文字列のコピーを返します。  
  
```  
CStringT Left(int nCount) const; 
```  
  
### <a name="parameters"></a>パラメーター  
 `nCount`  
 この `CStringT` オブジェクトから抽出する文字数。  
  
### <a name="return-value"></a>戻り値  
 指定の文字範囲のコピーを含む `CStringT` オブジェクト。 返された `CStringT` オブジェクトは空の場合があります。  
  
### <a name="remarks"></a>コメント  
 `nCount` が文字列の長さを超える場合、文字列全体が抽出されます。 `Left` は、Basic `Left` 関数に類似します。  
  
 マルチバイト文字セット (MBCS) では、`nCount` は 8 ビットの各並びを文字として処理します。したがって、`nCount` では 2 で乗算されたマルチバイト文字数が返されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&#123;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_18.cpp)]  
  
##  <a name="a-nameloadstringa--cstringtloadstring"></a><a name="loadstring"></a>CStringT::LoadString  
 識別される、Windows の文字列リソースを読み取ります`nID`を既存`CStringT`オブジェクトです。  
  
```  
BOOL LoadString(HINSTANCE hInstance, UINT nID, WORD wLanguageID);
BOOL LoadString(HINSTANCE hInstance, UINT nID);
BOOL LoadString(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `hInstance`  
 モジュールのインスタンスへのハンドル。  
  
 `nID`  
 Windows の文字列リソース id です。  
  
 `wLanguageID`  
 文字列リソースの言語です。  
  
### <a name="return-value"></a>戻り値  
 リソースの負荷が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 文字列リソースを読み込みます ( `nID`) 指定したモジュールから ( `hInstance`)、指定した言語を使用して ( `wLanguage`)。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&124;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_19.cpp)]  
  
##  <a name="a-namemakelowera--cstringtmakelower"></a><a name="makelower"></a>CStringT::MakeLower  
 変換、`CStringT`小文字の文字列オブジェクト。  
  
```  
CStringT& MakeLower();
```  
  
### <a name="return-value"></a>戻り値  
 結果として得られる小文字の文字列。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&125;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_20.cpp)]  
  
##  <a name="a-namemakereversea--cstringtmakereverse"></a><a name="makereverse"></a>CStringT::MakeReverse  
 内の文字の順序を反転、`CStringT`オブジェクトです。  
  
```  
CStringT& MakeReverse();
```  
  
### <a name="return-value"></a>戻り値  
 その結果には、文字列が取り消されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&126;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_21.cpp)]  
  
##  <a name="a-namemakeuppera--cstringtmakeupper"></a><a name="makeupper"></a>CStringT::MakeUpper  
 変換、`CStringT`オブジェクトを大文字の文字列です。  
  
```  
CStringT& MakeUpper();
```  
  
### <a name="return-value"></a>戻り値  
 結果として得られる大文字の文字列です。  
  
### <a name="remarks"></a>コメント  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&#127;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_22.cpp)]  
  
##  <a name="a-namemida--cstringtmid"></a><a name="mid"></a>CStringT::Mid  
 長さの部分文字列を抽出`nCount`これから文字`CStringT`オブジェクトの位置以降にある`iFirst`(0 から始まる)。  
  
```  
CStringT Mid(int iFirst, int nCount) const;
CStringT Mid(int iFirst) const; 
```  
  
### <a name="parameters"></a>パラメーター  
 `iFirst`  
 この最初の文字の&0; から始まるインデックス`CStringT`抽出された部分文字列に含まれるオブジェクト。  
  
 `nCount`  
 この `CStringT` オブジェクトから抽出する文字数。 このパラメーターが指定されていない場合は、文字列の残りの部分を抽出します。  
  
### <a name="return-value"></a>戻り値  
 指定の文字範囲のコピーを含む `CStringT` オブジェクト。 なお、返された`CStringT`オブジェクトを空にすることがあります。  
  
### <a name="remarks"></a>コメント  
 関数は、抽出された部分文字列のコピーを返します。 `Mid`ですが、基本的な Mid 関数に似ています (Basic でのインデックスは&1; から始まります) です。  
  
 マルチバイト文字セット (MBCS)、`nCount`は各 8 ビット文字; は、先行バイトと後続バイト マルチバイト文字が 2 つの文字としてカウントが 1 つを参照します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&128;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_23.cpp)]  
  
##  <a name="a-nameoemtoansia--cstringtoemtoansi"></a><a name="oemtoansi"></a>CStringT::OemToAnsi  
 これですべての文字変換`CStringT`から OEM 文字セットの ANSI 文字セットをオブジェクトです。  
  
```  
void OemToAnsi();
```  
  
### <a name="remarks"></a>コメント  
 この機能は利用可能な場合は`_UNICODE`が定義されています。  
  
### <a name="example"></a>例  
 例を参照してください[CStringT::AnsiToOem](#ansitooem)します。  
  
##  <a name="a-nameoperatoradda--cstringtoperator-"></a><a name="operator_add"></a>CStringT::operator +  
 2 つの文字列または文字と文字列を連結します。  
  
```  
friend CStringT operator+(const CStringT& str1, const CStringT& str2);
friend CStringT operator+(const CStringT& str1, PCXSTR psz2);
friend CStringT operator+(PCXSTR psz1, const CStringT& str2,);
friend CStringT operator+(char ch1, const CStringT& str2,);
friend CStringT operator+(const CStringT& str1, char ch2);
friend CStringT operator+(const CStringT& str1, wchar_t ch2);
friend CStringT operator+(wchar_t ch1, const CStringT& str2,);
```  
  
### <a name="parameters"></a>パラメーター  
 `ch1`  
 文字列に連結する ANSI または Unicode 文字。  
  
 `ch2`  
 文字列に連結する ANSI または Unicode 文字。  
  
 `str1`  
 A`CStringT`文字列または文字で連結します。  
  
 `str2`  
 A`CStringT`文字列または文字で連結します。  
  
 `psz1`  
 文字列または文字で連結する null で終わる文字列へのポインター。  
  
 `psz2`  
 文字列または文字で連結する文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 7 つのオーバー ロード形式の`CStringT::operator+`関数です。 最初のバージョンでは、既存の&2; つを連結`CStringT`オブジェクトです。 次の&2; つ連結、`CStringT`オブジェクトおよび null で終わる文字列。 次の&2; つ連結、`CStringT`オブジェクトと ANSI 文字です。 最後の&2; つ連結、`CStringT`オブジェクトと Unicode 文字。  
  
> [!NOTE]
>  作成することができますが`CStringT`を含むインスタンスには、null 文字が埋め込まれているはお勧めしています。 メソッドと演算子を呼び出すことで`CStringT`埋め込まれた null 文字が含まれているオブジェクトは、意図しない結果を生成することです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&140;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_24.cpp)]  
  
##  <a name="a-nameoperatoraddeqa--cstringtoperator-"></a><a name="operator_add_eq"></a>CStringT::operator + = 演算子  
 文字列の末尾に文字を連結します。  
  
```  
CStringT& operator+=(const CThisSimpleString& str);

template<bool bMFCDLL>  
CStringT& operator+=(const const CSimpleStringT<BaseType, bMFCDLL>& str);

template<int t_nSize>  
CStringT& operator+=(const CStaticString<XCHAR, t_nSize>& strSrc);
CStringT& operator+=(PCXSTR pszSrc);
CStringT& operator+=(PCYSTR pszSrc);
CStringT& operator+=(char ch);
CStringT& operator+=(unsigned char ch);
CStringT& operator+=(wchar_t ch);
CStringT& operator+=(const VARIANT& var);
```  
  
### <a name="parameters"></a>パラメーター  
 str  
 `CThisSimpleString` オブジェクトへの参照。  
  
 `bMFCDLL`  
 プロジェクトが MFC DLL であるかどうかどうか指定するブール値。  
  
 `BaseType`  
 文字列の基本型です。  
  
 `var`  
 この文字列に連結するバリアント型のオブジェクト。  
  
 `ch`  
 文字列に連結する ANSI または Unicode 文字。  
  
 `pszSrc`  
 連結された場合、元の文字列へのポインター。  
  
 `strSrc`  
 A`CStringT`この文字列に連結します。  
  
### <a name="remarks"></a>コメント  
 この演算子は別`CStringT`オブジェクト、文字のポインター、または単一の文字。 注意すべき文字が次のように追加されて新しい記憶域を割り当てることがあるために、連結演算子を使用するたびに、例外が発生する可能性がそのメモリ`CStringT`オブジェクトです。  
  
 詳細について`CThisSimpleString`の「解説」セクションを参照してください[CStringT::CStringT](#cstringt)します。  
  
> [!NOTE]
>  作成することができますが`CStringT`を含むインスタンスには、null 文字が埋め込まれているはお勧めしています。 メソッドと演算子を呼び出すことで`CStringT`埋め込まれた null 文字が含まれているオブジェクトは、意図しない結果を生成することです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&141;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_25.cpp)]  
  
##  <a name="a-nameoperatoreqeqa--cstringtoperator-"></a><a name="operator_eq_eq"></a>CStringT::operator = =  
 2 つの文字列が論理的に等価かどうかを判断します。  
  
```  
friend bool operator==(const CStringT& str1, const CStringT& str2) throw();
friend bool operator==(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator==(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator==(const CStringT& str1, XCHAR ch2) throw();
friend bool operator==(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator==(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator==(XCHAR ch1, const CStringT& str2,) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `ch1`  
 比較のための ANSI または Unicode 文字。  
  
 `ch2`  
 比較のための ANSI または Unicode 文字。  
  
 `str1`  
 A`CStringT`比較します。  
  
 `str2`  
 A`CStringT`比較します。  
  
 `psz1`  
 比較対象の null で終わる文字列へのポインター。  
  
 `psz2`  
 比較対象の null で終わる文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 文字列または左側にある文字が文字列または右側にある、文字に一致し、TRUE または FALSE を返すかどうかをテストします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&142;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_26.cpp)]  
  
##  <a name="a-nameoperatorneqa--cstringtoperator-"></a><a name="operator_neq"></a>CStringT::operator! =  
 2 つの文字列が等しい論理的にないかどうかを判断します。  
  
```  
friend bool operator!=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator!=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator!=(const CStringT& str1, PCYSTR psz2) throw();
friend bool operator!=(const CStringT& str1, XCHAR ch2) throw();
friend bool operator!=(PCXSTR psz1, const CStringT& str2) throw();
friend bool operator!=(PCYSTR psz1, const CStringT& str2,) throw();
friend bool operator!=(XCHAR ch1, const CStringT& str2,) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `ch1`  
 文字列に連結する ANSI または Unicode 文字。  
  
 `ch2`  
 文字列に連結する ANSI または Unicode 文字。  
  
 `str1`  
 A`CStringT`比較します。  
  
 `str2`  
 A`CStringT`比較します。  
  
 `psz1`  
 比較対象の null で終わる文字列へのポインター。  
  
 `psz2`  
 比較対象の null で終わる文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 文字列または左側にある文字が文字列または右側にある文字と等しくないかどうか。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&143;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_27.cpp)]  
  
##  <a name="a-nameoperatorlta--cstringtoperator-lt"></a><a name="operator_lt"></a>CStringT::operator&lt;  
 演算子の左側にある文字列が右側にある文字列より小さいかどうかを判断します。  
  
```  
friend bool operator<(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<(PCXSTR psz1, const CStringT& str2) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `str1`  
 A`CStringT`比較します。  
  
 `str2`  
 A`CStringT`比較します。  
  
 `psz1`  
 比較対象の null で終わる文字列へのポインター。  
  
 `psz2`  
 比較対象の null で終わる文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 文字列、文字までの間の辞書順比較します。  
  
-   2 つの対応する文字が等しくない場合、比較の結果は文字列間の比較の結果として取得されます。  
  
-   不等が見つからなくても、1 つの文字列に他より多くの文字がある場合、短い文字列は長い文字列より小さいと見なされます。  
  
-   不等が見つからず、各文字列の文字数が同じである場合、文字列が等しくなります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&144;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_28.cpp)]  
  
##  <a name="a-nameoperatorgta--cstringtoperator-gt"></a><a name="operator_gt"></a>CStringT::operator&gt;  
 演算子の左側にある文字列が右側にある文字列より大きいかどうかを決定します。  
  
```  
friend bool operator>(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>(PCXSTR psz1, const CStringT& str2) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `str1`  
 A`CStringT`比較します。  
  
 `str2`  
 A`CStringT`比較します。  
  
 `psz1`  
 比較対象の null で終わる文字列へのポインター。  
  
 `psz2`  
 比較対象の null で終わる文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 文字列、文字までの間の辞書順比較します。  
  
-   2 つの対応する文字が等しくない場合、比較の結果は文字列間の比較の結果として取得されます。  
  
-   不等が見つからなくても、1 つの文字列に他より多くの文字がある場合、短い文字列は長い文字列より小さいと見なされます。  
  
-   不等が見つからず、各文字列の文字数が同じである場合、文字列が等しくなります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&145;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_29.cpp)]  
  
##  <a name="a-nameoperatorlteqa--cstringtoperator-lt"></a><a name="operator_lt_eq"></a>CStringT::operator&lt;=  
 演算子の左側にある文字列が右側にある文字列以下かどうかを判断します。  
  
```  
friend bool operator<=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator<=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator<=(PCXSTR psz1, const CStringT& str2) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `str1`  
 A`CStringT`比較します。  
  
 `str2`  
 A`CStringT`比較します。  
  
 `psz1`  
 比較対象の null で終わる文字列へのポインター。  
  
 `psz2`  
 比較対象の null で終わる文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 文字列、文字までの間の辞書順比較します。  
  
-   2 つの対応する文字が等しくない場合、比較の結果は文字列間の比較の結果として取得されます。  
  
-   不等が見つからなくても、1 つの文字列に他より多くの文字がある場合、短い文字列は長い文字列より小さいと見なされます。  
  
-   不等が見つからず、各文字列の文字数が同じである場合、文字列が等しくなります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&146;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_30.cpp)]  
  
##  <a name="a-nameoperatorgteqa--cstringtoperator-gt"></a><a name="operator_gt_eq"></a>CStringT::operator&gt;=  
 演算子の左側にある文字列が右側にある文字列以上であるかどうかを判断します。  
  
```  
friend bool operator>=(const CStringT& str1, const CStringT& str2) throw();
friend bool operator>=(const CStringT& str1, PCXSTR psz2) throw();
friend bool operator>=(PCXSTR psz1, const CStringT& str2) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `str1`  
 A`CStringT`比較します。  
  
 `str2`  
 A`CStringT`比較します。  
  
 `psz1`  
 比較対象の文字列へのポインター。  
  
 `psz2`  
 比較対象の文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 文字列、文字までの間の辞書順比較します。  
  
-   2 つの対応する文字が等しくない場合、比較の結果は文字列間の比較の結果として取得されます。  
  
-   不等が見つからなくても、1 つの文字列に他より多くの文字がある場合、短い文字列は長い文字列より小さいと見なされます。  
  
-   不等が見つからず、各文字列の文字数が同じである場合、文字列が等しくなります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities&#147;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_31.cpp)]  
  
##  <a name="a-nameremovea--cstringtremove"></a><a name="remove"></a>CStringT::Remove  
 文字列から指定した文字のすべてのインスタンスを削除します。  
  
```  
int Remove(XCHAR chRemove);
```  
  
### <a name="parameters"></a>パラメーター  
 `chRemove`  
 文字列から削除する文字。  
  
### <a name="return-value"></a>戻り値  
 文字数は、文字列から削除します。 文字列が変更されていない場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 文字の比較では大文字小文字を区別します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&129;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_32.cpp)]  
  
##  <a name="a-namereplacea--cstringtreplace"></a><a name="replace"></a>CStringT::Replace  
 2 つのバージョンがある`Replace`です。最初のバージョンでは、別の部分文字列を使用して部分文字列の&1; つまたは複数のコピーが置き換えられます。 両方の部分文字列は、null で終わるです。 2 番目のバージョンでは、別の文字を使用して、文字の&1; つまたは複数のコピーが置き換えられます。 格納されている文字データの両方のバージョンが動作`CStringT`します。  
  
```  
int Replace(PCXSTR pszOld, PCXSTR pszNew);
int Replace(XCHAR chOld, XCHAR chNew);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszOld`  
 置き換えられる null で終わる文字列へのポインター`pszNew`します。  
  
 `pszNew`  
 置換する null で終わる文字列へのポインター`pszOld`します。  
  
 `chOld`  
 置き換えられる文字`chNew`します。  
  
 `chNew`  
 文字の置換`chOld`します。  
  
### <a name="return-value"></a>戻り値  
 文字列が変更されていない場合は、置き換えられた文字または部分文字列、または&0; の数を返します。  
  
### <a name="remarks"></a>コメント  
 `Replace`文字列の長さを変更できます`pszNew`と`pszOld`する同じ長さにする必要はありませんし、古いの部分文字列の複数のコピーを新しいものに変更できます。 この関数では、大文字と小文字を実行します。  
  
 例として`CStringT`インスタンスが`CString`、 `CStringA`、および`CStringW`です。  
  
 `CStringA`、`Replace`は ANSI またはマルチバイト (MBCS) 文字とします。 `CStringW`、`Replace`ワイド文字が連携します。  
  
 `CString`、文字データ型は次の表に、定数が定義されているかどうかに基づいて、コンパイル時に選択します。  
  
|定義済み定数|文字データ型|  
|----------------------|-------------------------|  
|`_UNICODE`|ワイド文字|  
|`_MBCS`|マルチバイト文字|  
|なし|1 バイト文字|  
|両方|未定義|  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&200;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_33.cpp)]  
  
##  <a name="a-namereversefinda--cstringtreversefind"></a><a name="reversefind"></a>CStringT::ReverseFind  
 これが検索`CStringT`文字の最後の一致のオブジェクト。  
  
```  
int ReverseFind(XCHAR ch) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `ch`  
 検索する文字。  
  
### <a name="return-value"></a>戻り値  
 この最後の文字の&0; から始まるインデックス`CStringT`文字が見つからない場合は、-1 を指定した文字と一致するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 関数は、ランタイム関数に似た`strrchr`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&130;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_34.cpp)]  
  
##  <a name="a-namerighta--cstringtright"></a><a name="right"></a>CStringT::Right  
 最後の抽出 (つまり、右端にある)`nCount`これから文字`CStringT`オブジェクトし、抽出された部分文字列のコピーを返します。  
  
```  
CStringT Right(int nCount) const; 
```  
  
### <a name="parameters"></a>パラメーター  
 `nCount`  
 この `CStringT` オブジェクトから抽出する文字数。  
  
### <a name="return-value"></a>戻り値  
 指定の文字範囲のコピーを含む `CStringT` オブジェクト。 なお、返された`CStringT`オブジェクトを空にすることができます。  
  
### <a name="remarks"></a>コメント  
 `nCount` が文字列の長さを超える場合、文字列全体が抽出されます。 `Right`Basic に似た`Right`機能 (点が異なりますが、Basic でのインデックスは、0 から始まる)。  
  
 マルチバイト文字セット (MBCS)、`nCount`は各 8 ビット文字; は、先行バイトと後続バイト マルチバイト文字が 2 つの文字としてカウントが 1 つを参照します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&131;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_35.cpp)]  
  
##  <a name="a-namesetsysstringa--cstringtsetsysstring"></a><a name="setsysstring"></a>名称  
 再割り当て、`BSTR`が指す`pbstr`の内容をコピーし、`CStringT`を含め、そこにオブジェクト、`NULL`文字です。  
  
```  
BSTR SetSysString(BSTR* pbstr) const; 
```  
  
### <a name="parameters"></a>パラメーター  
 `pbstr`  
 文字の文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 新しい文字列。  
  
### <a name="remarks"></a>コメント  
 内容に応じて、`CStringT`オブジェクト、値の`BSTR`によって参照される`pbstr`を変更することができます。 関数、`CMemoryException`十分なメモリが存在する場合。  
  
 この関数は通常、自動化のために、参照によって渡される文字列の値を変更する使用します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&132;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_36.cpp)]  
  
##  <a name="a-namespanexcludinga--cstringtspanexcluding"></a><a name="spanexcluding"></a>CStringT::SpanExcluding  
 識別される文字のセットに含まれていない最初の文字で始まる文字列から文字を抽出`pszCharSet`します。  
  
```  
CStringT SpanExcluding(PCXSTR pszCharSet) const; 
```  
  
### <a name="parameters"></a>パラメーター  
 `pszCharSet`  
 文字列は、一連の文字として解釈されます。  
  
### <a name="return-value"></a>戻り値  
 追加されていない文字列内の文字を含む部分文字列`pszCharSet`、文字列内の最初の文字で始まるでも文字列内にある最初の文字で終わる`pszCharSet`(つまり、文字列とは見つかった文字列の最初の文字を除く最初の文字で始まる`pszCharSet`)。 内の文字に文字列全体を返す`pszCharSet`文字列内にあります。  
  
### <a name="remarks"></a>コメント  
 `SpanExcluding`抽出し、最初に見つかった位置の文字の前にすべての文字を返す`pszCharSet`(から文字、つまり`pszCharSet`文字列で、次のすべての文字は返されません)。 文字`pszCharSet`し、文字列内に見つかるは`SpanExcluding`文字列全体を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&133;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_37.cpp)]  
  
##  <a name="a-namespanincludinga--cstringtspanincluding"></a><a name="spanincluding"></a>CStringT::SpanIncluding  
 識別される文字のセットに含まれる最初の文字で始まる文字列から文字を抽出`pszCharSet`します。  
  
```  
CStringT SpanIncluding(PCXSTR pszCharSet) const; 
```  
  
### <a name="parameters"></a>パラメーター  
 `pszCharSet`  
 文字列は、一連の文字として解釈されます。  
  
### <a name="return-value"></a>戻り値  
 部分文字列に含まれる文字列内の文字を含む`pszCharSet`文字列の最初の文字で始まる、および終了に含まれていない文字列の文字が見つかったときに`pszCharSet.``SpanIncluding`文字列の最初の文字が指定されたセット内にない場合は、空の部分文字列を返します。  
  
### <a name="remarks"></a>コメント  
 文字列の最初の文字がない場合、文字セットで、`SpanIncluding`空の文字列を返します。 それ以外の場合は、セット内の連続する文字のシーケンスを返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&134;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_38.cpp)]  
  
##  <a name="a-nametokenizea--cstringttokenize"></a><a name="tokenize"></a>CStringT::Tokenize  
 対象の文字列内の次のトークンを検索します。  
  
```  
CStringT Tokenize(PCXSTR pszTokens, int& iStart) const; 
```  
  
### <a name="parameters"></a>パラメーター  
 `pszTokens`  
 トークン区切り記号を含む文字列。 これらの区切り記号の順序は重要ではありません。  
  
 `iStart`  
 検索を開始する&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 A`CStringT`現在のトークンの値を格納するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 `Tokenize`関数はターゲット文字列内の次のトークンを検索します。 文字セット`pszTokens`検索されたトークンの可能な区切り記号を指定します。 呼び出すたびに`Tokenize`関数が始まる`iStart`、先行する区切り記号をスキップし、返します。、`CStringT`次の区切り記号文字までの文字の文字列であり、現在のトークンを格納するオブジェクト。 値`iStart`文字列の末尾に達した場合、終了の区切り記号の文字または-1 の直後の位置を更新します。 以上のトークンへの呼び出しのシリーズではターゲット文字列の残りから分けることが`Tokenize`を使用して、`iStart`を次のトークンが読み込まれる文字列の位置を追跡します。 空の文字列を返す以上トークンがある場合に、 `iStart` -1 に設定されます。  
  
 CRT とは異なりなどの関数をトークン化[strtok_s、_strtok_s_l、wcstok_s、_wcstok_s_l、_mbstok_s、_mbstok_s_l](../../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md)、`Tokenize`対象の文字列を変更しません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&135;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_39.cpp)]  
  
### <a name="remarks"></a>コメント  
 この例の出力は次のとおりです。  
  
 `Resulting Token: First`  
  
 `Resulting Token: Second`  
  
 `Resulting Token: Third`  
  
##  <a name="a-nametrima--cstringttrim"></a><a name="trim"></a>CStringT::Trim  
 先頭と末尾の文字の文字列を削除します。  
  
```  
CStringT& Trim(XCHAR chTarget);
CStringT& Trim(PCXSTR pszTargets);
CStringT& Trim();
```  
  
### <a name="parameters"></a>パラメーター  
 `chTarget`  
 トリムされる文字。  
  
 `pszTargets`  
 トリムされる文字を含む文字列へのポインター。 すべて先頭と末尾の文字の出現回数`pszTarget`から除去されることは、`CStringT`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 トリミングされた文字列を返します。  
  
### <a name="remarks"></a>コメント  
 次のいずれかの先頭および末尾の出現をすべて削除します。  
  
-   指定された文字`chTarget.`  
  
-   指定された文字列で検出されたすべての文字`pszTargets.`  
  
-   空白。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&136;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_40.cpp)]  
  
### <a name="remarks"></a>コメント  
 この例の出力は次のとおりです。  
  
 `Before: "******Soccer is best, but liquor is quicker!!!!!"`  
  
 `After : "Soccer is best, but liquor is quicker"`  
  
##  <a name="a-nametrimlefta--cstringttrimleft"></a><a name="trimleft"></a>CStringT::TrimLeft  
 文字列の先頭から文字をトリムします。  
  
```  
CStringT& TrimLeft(XCHAR chTarget);
CStringT& TrimLeft(PCXSTR pszTargets);
CStringT& TrimLeft();
```  
  
### <a name="parameters"></a>パラメーター  
 `chTarget`  
 トリムされる文字。  
  
 `pszTargets`  
 トリムされる文字を含む文字列へのポインター。 内の文字の先頭をすべて`pszTarget`から除去されることは、`CStringT`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 その結果には、文字列が切り捨てられます。  
  
### <a name="remarks"></a>コメント  
 次のいずれかの先頭および末尾の出現をすべて削除します。  
  
-   指定された文字`chTarget.`  
  
-   指定された文字列で検出されたすべての文字`pszTargets.`  
  
-   空白。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&137;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_41.cpp)]  
  
##  <a name="a-nametrimrighta--cstringttrimright"></a><a name="trimright"></a>CStringT::TrimRight  
 文字の文字列の末尾をトリミングします。  
  
```  
CStringT& TrimRight(XCHAR chTarget);
CStringT& TrimRight(PCXSTR pszTargets);
CStringT& TrimRight();
```  
  
### <a name="parameters"></a>パラメーター  
 `chTarget`  
 トリムされる文字。  
  
 `pszTargets`  
 トリムされる文字を含む文字列へのポインター。 末尾の文字のすべて`pszTarget`から除去されることは、`CStringT`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 返します。、`CStringT`トリミングされた文字列を格納します。  
  
### <a name="remarks"></a>コメント  
 末尾に、次のいずれかの出現を削除します。  
  
-   指定された文字`chTarget.`  
  
-   指定された文字列で検出されたすべての文字`pszTargets.`  
  
-   空白。  
  
 `CStringT& TrimRight(XCHAR chTarget)`バージョンは、文字の&1; つのパラメーターを受け入れるしの末尾から、その文字のすべてのコピーを削除`CStringT`文字列データです。 文字列の末尾から開始し、先頭近くに動作します。 別の文字が見つかったとき、または停止時`CSTringT`文字データが不足しています。  
  
 `CStringT& TrimRight(PCXSTR pszTargets)`のバージョンでは検索するさまざまなすべての文字を含む null で終わる文字列。 これらの文字のすべてのコピーを削除して、`CStringT`オブジェクトです。 文字列の末尾から開始し、先頭近くに動作します。 対象の文字列に含まれていない文字が見つかったとき、または停止時`CStringT`文字データが不足しています。 最後の部分文字列全体の対象の文字列の一致を試みない`CStringT`します。  
  
 `CStringT& TrimRight()`バージョン パラメーターは不要です。 末尾から末尾の空白文字をトリム、`CStringT`文字列。 空白文字は、改行文字、スペースやタブにできます。  
  
-  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities #&138;](../../atl-mfc-shared/codesnippet/cpp/cstringt-class_42.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL と MFC クラスの共有](../../atl-mfc-shared/atl-mfc-shared-classes.md)   
 [CSimpleStringT クラス](../../atl-mfc-shared/reference/csimplestringt-class.md)



