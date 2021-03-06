---
title: 'Cómo: cambiar el Control MonthCalendar de formularios de Windows&#39;apariencia'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], calendar controls
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
ms.openlocfilehash: 4f91363764099cabfa1a7939ff07e627aeb6c815
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43802020"
---
# <a name="how-to-change-the-windows-forms-monthcalendar-control39s-appearance"></a>Cómo: cambiar el Control MonthCalendar de formularios de Windows&#39;apariencia
Los formularios de Windows <xref:System.Windows.Forms.MonthCalendar> control le permite personalizar la apariencia del calendario de muchas maneras. Por ejemplo, puede establecer la combinación de colores y elegir mostrar u ocultar los números de semana y la fecha actual.  
  
### <a name="to-change-the-month-calendars-color-scheme"></a>Para cambiar la combinación de colores del calendario mensual  
  
-   Establecer propiedades tales como <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> y <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>. El <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> propiedad también determina el color de fuente para los días de la semana. El <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> propiedad determina el color de las fechas que preceden y siguen el mes que se muestra o meses.  
  
    ```vb  
    MonthCalendar1.TitleBackColor = System.Drawing.Color.Blue  
    MonthCalendar1.TrailingForeColor = System.Drawing.Color.Red  
    MonthCalendar1.TitleForeColor = System.Drawing.Color.Yellow  
    ```  
  
    ```csharp  
    monthCalendar1.TitleBackColor = System.Drawing.Color.Blue;  
    monthCalendar1.TrailingForeColor = System.Drawing.Color.Red;  
    monthCalendar1.TitleForeColor = System.Drawing.Color.Yellow;  
    ```  
  
    ```cpp  
    monthCalendar1->TitleBackColor = System::Drawing::Color::Blue;  
    monthCalendar1->TrailingForeColor = System::Drawing::Color::Red;  
    monthCalendar1->TitleForeColor = System::Drawing::Color::Yellow;  
    ```  
  
    > [!NOTE]
    >  A partir de Windows Vista y según el tema, establecer algunas propiedades podría no cambiar la apariencia del calendario. Por ejemplo, si Windows está configurado para usar el tema de Aero, al establecer el <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, o <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> propiedades no tiene ningún efecto. Esto es debido a una versión actualizada del calendario se representa con un aspecto que se deriva en tiempo de ejecución del tema actual del sistema operativo. Si desea usar estas propiedades y habilitar la versión anterior del calendario, puede deshabilitar estilos visuales para su aplicación. Deshabilitar estilos visuales podría afectar a la apariencia y comportamiento de otros controles en la aplicación. Para deshabilitar estilos visuales en Visual Basic, abra el Diseñador de proyectos y desactive el **estilos visuales de XP habilitar** casilla de verificación. Para deshabilitar estilos visuales en C#, abra Program.cs y marque como comentario `Application.EnableVisualStyles();`. Para obtener más información sobre los estilos visuales, vea [Cómo: Habilitar estilos visuales de XP Windows](https://msdn.microsoft.com/library/0a038ade-31cf-4e56-9cfe-7a1e6b83b57f).  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a>Para mostrar la fecha actual en la parte inferior del control  
  
-   Establezca la propiedad <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> en `true`. En el ejemplo siguiente se alterna entre mostrar y omitir la fecha de hoy cuando se hace doble clic en el formulario.  
  
    ```vb  
    Private Sub Form1_DoubleClick(ByVal sender As Object, _  
    ByVal e As System.EventArgs) Handles MyBase.DoubleClick  
       ' Toggle between True and False.  
       MonthCalendar1.ShowToday = Not MonthCalendar1.ShowToday  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_DoubleClick(object sender, System.EventArgs e)  
    {  
       // Toggle between True and False.  
       monthCalendar1.ShowToday = !monthCalendar1.ShowToday;  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void Form1_DoubleClick(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          // Toggle between True and False.  
          monthCalendar1->ShowToday = !monthCalendar1->ShowToday;  
       }  
    ```  
  
     (Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a>Para mostrar los números de semana  
  
-   Establezca la propiedad <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> en `true`. Puede establecer esta propiedad en el código o en la ventana Propiedades.  
  
     Números de semana aparecen en una columna independiente a la izquierda del primer día de la semana.  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a>Vea también  
 [MonthCalendar (control)](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [Seleccionar un intervalo de fechas en el control MonthCalendar de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)  
 [Mostrar días específicos en negrita con el control MonthCalendar de formularios Windows Forms](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)  
 [Mostrar más de un mes en el control MonthCalendar de formularios Windows Forms](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)
