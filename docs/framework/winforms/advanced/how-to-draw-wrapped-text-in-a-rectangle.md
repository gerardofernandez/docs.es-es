---
title: 'Cómo: Dibujar texto ajustado en un rectángulo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
ms.openlocfilehash: c753be6a200f166e59e1330c7dbcf1fadc7588a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524978"
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a>Cómo: Dibujar texto ajustado en un rectángulo
Se puede dibujar texto ajustado en un rectángulo con el <xref:System.Drawing.Graphics.DrawString%2A> sobrecargar el método de la <xref:System.Drawing.Graphics> clase que toma un <xref:System.Drawing.Rectangle> o <xref:System.Drawing.RectangleF> parámetro. También se utiliza un <xref:System.Drawing.Brush> y <xref:System.Drawing.Font>.  
  
 También se puede dibujar texto ajustado en un rectángulo con el <xref:System.Windows.Forms.TextRenderer.DrawText%2A> sobrecargar el método de la <xref:System.Windows.Forms.TextRenderer> que toma un <xref:System.Drawing.Rectangle> y un <xref:System.Windows.Forms.TextFormatFlags> parámetro. También se utiliza un <xref:System.Drawing.Color> y <xref:System.Drawing.Font>.  
  
 En la siguiente ilustración muestra el resultado del texto dibujado en el rectángulo, cuando se usa el <xref:System.Drawing.Graphics.DrawString%2A> método.  
  
 ![Texto de las fuentes](../../../../docs/framework/winforms/advanced/media/csfontstext2.png "csfontstext2")  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>Para dibujar texto ajustado en un rectángulo con GDI +  
  
1.  Use la <xref:System.Drawing.Graphics.DrawString%2A> método sobrecargado, pasando el texto que desee, <xref:System.Drawing.Rectangle> o <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> y <xref:System.Drawing.Brush>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>Para dibujar texto ajustado en un rectángulo con GDI  
  
1.  Use la <xref:System.Windows.Forms.TextFormatFlags> valor de enumeración para especificar el texto debe ajustarse a la <xref:System.Windows.Forms.TextRenderer.DrawText%2A> método sobrecargado, pasando el texto que desee, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> y <xref:System.Drawing.Color>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Los ejemplos anteriores requieren:  
  
-   <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también  
 [Dibujar texto con GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [Utilizar fuentes y texto](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [Construir fuentes y familias de fuentes](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 [Dibujar texto en una ubicación especificada](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)
