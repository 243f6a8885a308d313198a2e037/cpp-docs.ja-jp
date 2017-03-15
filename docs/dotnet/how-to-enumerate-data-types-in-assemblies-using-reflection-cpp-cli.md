---
title: "方法: リフレクションを使用してアセンブリ内のデータ型を列挙する (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アセンブリ [C++]"
  - "アセンブリ [C++], 列挙型"
  - "データ型 [C++], 列挙"
  - "パブリック メンバー [C++]"
  - "パブリック型 [C++]"
  - "リフレクション [C++], 外部アセンブリ"
ms.assetid: c3578e6d-bb99-4599-80e1-ab795305f878
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: リフレクションを使用してアセンブリ内のデータ型を列挙する (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次のコードは、<xref:System.Reflection> を使用してパブリック型とメンバーを一覧表示します。  
  
 このコードは、アセンブリ名が指定されると、ローカル ディレクトリ内または GAC 内のいずれかで、アセンブリを開き記述を取得します。  正常に処理が完了すると、各型が、そのパブリック メンバーと共に表示されます。  
  
 ただし、<xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> では、ファイル拡張子を使用しないでください。  したがって、コマンド ライン引数に "mscorlib.dll" を使用するとエラーになります。一方、"mscorlib" のみを指定すると、.NET Framework の型が表示されます。  アセンブリ名を指定しないと、コードにより、現在のアセンブリ \(このコードにより生成された EXE\) 内の型が検出され、報告されます。  
  
## 使用例  
  
```  
// self_reflection.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Reflection;  
using namespace System::Collections;  
  
public ref class ExampleType {  
public:  
   ExampleType() {}  
   void Func() {}  
};  
  
int main() {  
   String^ delimStr = " ";  
   array<Char>^ delimiter = delimStr->ToCharArray( );  
   array<String^>^ args = Environment::CommandLine->Split( delimiter );  
  
// replace "self_reflection.exe" with an assembly from either the local  
// directory or the GAC  
   Assembly^ a = Assembly::LoadFrom("self_reflection.exe");  
   Console::WriteLine(a);  
  
   int count = 0;  
   array<Type^>^ types = a->GetTypes();  
   IEnumerator^ typeIter = types->GetEnumerator();  
  
   while ( typeIter->MoveNext() ) {  
      Type^ t = dynamic_cast<Type^>(typeIter->Current);  
      Console::WriteLine("   {0}", t->ToString());  
  
      array<MemberInfo^>^ members = t->GetMembers();  
      IEnumerator^ memberIter = members->GetEnumerator();  
      while ( memberIter->MoveNext() ) {  
         MemberInfo^ mi = dynamic_cast<MemberInfo^>(memberIter->Current);  
         Console::Write("      {0}", mi->ToString( ) );  
         if (mi->MemberType == MemberTypes::Constructor)  
            Console::Write("   (constructor)");  
  
         Console::WriteLine();  
      }  
      count++;  
   }  
   Console::WriteLine("{0} types found", count);  
}  
```  
  
## 参照  
 [リフレクション](../dotnet/reflection-cpp-cli.md)