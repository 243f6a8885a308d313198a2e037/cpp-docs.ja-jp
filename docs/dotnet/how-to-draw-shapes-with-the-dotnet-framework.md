---
title: "方法: .NET Framework を使用して図形を描画 |Microsoft ドキュメント"
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
helpviewer_keywords:
- GDI+, drawing shapes
- drawing, shapes
- shapes
- shapes, drawing
ms.assetid: ffad5ae7-6ef4-4550-8940-be3f209a101d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c5fc48eefb44049e4cff010b16c9567e443ba5db
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2018
---
# <a name="how-to-draw-shapes-with-the-net-framework"></a>方法: .NET Framework を使用して形状を描画する
次のコード例では、<xref:System.Drawing.Graphics>を変更するクラス、<xref:System.Windows.Forms.Form.OnPaint%2A>へのポインターを取得するイベント ハンドラー、<xref:System.Drawing.Graphics>メイン フォームのオブジェクト。 このポインターを使用して、フォームの背景色を設定し、行と円弧を使用して、描画、<xref:System.Drawing.Graphics.DrawLine%2A?displayProperty=fullName>と<xref:System.Drawing.Graphics.DrawArc%2A>メソッドです。  
  
## <a name="example"></a>例  
  
```  
#using <system.drawing.dll>  
using namespace System;  
using namespace System::Drawing;  
// ...  
protected:   
virtual Void Form1::OnPaint(PaintEventArgs^ pe ) override  
{  
   Graphics^ g = pe->Graphics;  
   g->Clear(Color::AntiqueWhite);  
  
   Rectangle rect = Form::ClientRectangle;  
   Rectangle smallRect;  
   smallRect.X = rect.X + rect.Width / 4;  
   smallRect.Y = rect.Y + rect.Height / 4;  
   smallRect.Width = rect.Width / 2;  
   smallRect.Height = rect.Height / 2;  
  
   Pen^ redPen = gcnew Pen(Color::Red);  
   redPen->Width = 4;  
   g->DrawLine(redPen, 0, 0, rect.Width, rect.Height);  
  
   Pen^ bluePen = gcnew Pen(Color::Blue);  
   bluePen->Width = 10;  
   g->DrawArc( bluePen, smallRect, 90, 270 );  
}  
```  
  
## <a name="see-also"></a>参照  
 [.NET プログラミング C + +/CLI (Visual C)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [System::Drawing 名前空間](https://msdn.microsoft.com/en-us/library/system.drawing.aspx)