---
title: DataGridView (Control, formularios Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- tables [Windows Forms]
- data grids [Windows Forms
- data [Windows Forms], displaying in tabular format
- grid controls [Windows Forms]
- datasets [Windows Forms], user interface
- Windows Forms, displaying data
- data presentation
- tabular data [Windows Forms], displaying on Windows Forms
- datasets [Windows Forms], displaying in DataGridView control
- DataGridView control [Windows Forms]
ms.assetid: dbee73f2-bba6-4874-9389-cd21d44309be
ms.openlocfilehash: 2ef387437befe3df67e261b719140456a3fde9dd
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43397224"
---
# <a name="datagridview-control-windows-forms"></a>DataGridView (Control, formularios Windows Forms)
El control `DataGridView` proporciona una forma eficaz y flexible de mostrar datos en formato de tabla. Puede usar el control `DataGridView` para mostrar vistas de solo lectura de una pequeña cantidad de datos, o puede ampliarlo para mostrar vistas editables de conjuntos de datos muy grandes.  
  
 Puede ampliar el control `DataGridView` de varias maneras para construir comportamientos personalizados en sus aplicaciones. Por ejemplo, puede especificar mediante programación sus propios algoritmos de ordenación y puede crear sus propios tipos de celdas. Puede personalizar fácilmente la apariencia del control `DataGridView` eligiendo entre varias propiedades. Se pueden usar muchos tipos de almacenes de datos como origen de datos, o el control `DataGridView` puede funcionar sin ningún origen de datos enlazado a él.  
  
 En los temas de esta sección se describen los conceptos y las técnicas que puede usar para compilar características de `DataGridView` en sus aplicaciones.  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general del control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)  
 Proporciona temas que describen los arquitectura y los conceptos fundamentales del control `DataGridView` de Windows Forms.  
  
 [Funcionalidad predeterminada en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/default-functionality-in-the-windows-forms-datagridview-control.md)  
 Describe la apariencia y el comportamiento predeterminados del control `DataGridView` de Windows Forms cuándo está enlazado a un origen de datos.  
  
 [Tipos de columnas en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 Describe los tipos de columna en el control `DataGridView` de Windows Forms que se usan para mostrar datos y permitir a los usuarios modificar o agregar datos.  
  
 [Características básicas de columnas, filas y celdas en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 Proporciona temas que describen las propiedades de celda, fila y columna que se usan habitualmente.  
  
 [Estilo y formato básicos del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 Proporciona temas que describen cómo modificar la apariencia básica del control y el formato de presentación de los datos de celda.  
  
 [Mostrar datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 Proporciona temas que describen cómo rellenar el control con datos manualmente o desde un origen de datos externo.  
  
 [Cambiar el tamaño de columnas y filas en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)  
 Proporciona temas que describen cómo ajustar automáticamente el tamaño de las filas y columnas al contenido de la celda o al ancho disponible del control.  
  
 [Ordenar datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)  
 Proporciona temas que describen las características de ordenación en el control.  
  
 [Entrada de datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 Proporciona temas que describen cómo cambiar la forma en que los usuarios agregan y modifican datos en el control.  
  
 [Selección y uso del Portapapeles con el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)  
 Proporciona temas que describen las características de selección de celdas, filas y columnas en el control.  
  
 [Programar con celdas, filas y columnas en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 Proporciona temas que describen cómo programar con objetos de columna, fila y celda.  
  
 [Personalizar el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 Proporciona temas que describen el dibujo personalizado de celdas y filas de `DataGridView`, y la creación de tipos derivados de celda, columna y fila.  
  
 [Ajuste del rendimiento del control DataGridView en Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 Proporciona temas que describen cómo usar eficazmente el control para evitar problemas de rendimiento cuando se trabaja con grandes cantidades de datos.  
  
 [Control predeterminado de teclado y mouse en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)  
 Describe cómo los usuarios pueden interactuar con el control `DataGridView` mediante un teclado y un mouse.  
  
 [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)  
 Describe cómo el control `DataGridView` mejora y reemplaza el control <xref:System.Windows.Forms.DataGrid>.  
  
 Consulte también [mediante el diseñador con el DataGridView Control de Windows Forms](using-the-designer-with-the-windows-forms-datagridview-control.md).  
  
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Forms.DataGridView>  
 Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.BindingSource>  
 Proporciona documentación de referencia para el componente <xref:System.Windows.Forms.BindingSource>. El control <xref:System.Windows.Forms.DataGridView> y el componente <xref:System.Windows.Forms.BindingSource> están diseñados para funcionar en estrecha colaboración.  
  
## <a name="see-also"></a>Vea también  
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
