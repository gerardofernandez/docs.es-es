---
title: Deshabilitar RealTimeStylus para las aplicaciones de WPF
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: ddf4a7f4488f957b2f413d61ad02aa59beba30f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545667"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a>Deshabilitar RealTimeStylus para las aplicaciones de WPF
Windows Presentation Foundation (WPF) incorpora compatibilidad para procesar la entrada táctil de Windows 7. La compatibilidad procede a través de la entrada de lápiz en tiempo real de la plataforma de tableta como <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, y <xref:System.Windows.UIElement.OnStylusMove%2A> eventos. Windows 7 también proporciona la entrada de multitoque como mensajes de ventana de Win32 WM_TOUCH. Estas dos API son mutuamente excluyentes en el mismo HWND. Habilitar táctil a través de la plataforma de tableta (el valor predeterminado para las aplicaciones WPF) deshabilita WM_TOUCH los mensajes de entrada. Como resultado, para usar WM_TOUCH para recibir mensajes de entrada táctil de una ventana de WPF, debe deshabilitar la compatibilidad con el lápiz integradas en WPF. Esto es aplicable en un escenario como una ventana de WPF que hospeda un componente que usa WM_TOUCH.  
  
 Para deshabilitar la escucha de WPF a la entrada de lápiz, quite cualquier compatibilidad de tableta agregada por la ventana de WPF.  
  
## <a name="example"></a>Ejemplo  
 El código de ejemplo siguiente muestra cómo quitar la compatibilidad de plataforma de tableta predeterminada mediante la reflexión.  
  
```  
public static void DisableWPFTabletSupport()  
{  
    // Get a collection of the tablet devices for this window.    
    TabletDeviceCollection devices = System.Windows.Input.Tablet.TabletDevices;  
  
    if (devices.Count > 0)  
    {     
        // Get the Type of InputManager.  
        Type inputManagerType = typeof(System.Windows.Input.InputManager);  
  
        // Call the StylusLogic method on the InputManager.Current instance.  
        object stylusLogic = inputManagerType.InvokeMember("StylusLogic",  
                    BindingFlags.GetProperty | BindingFlags.Instance | BindingFlags.NonPublic,  
                    null, InputManager.Current, null);  
  
        if (stylusLogic != null)  
        {  
            //  Get the type of the stylusLogic returned from the call to StylusLogic.  
            Type stylusLogicType = stylusLogic.GetType();  
  
            // Loop until there are no more devices to remove.  
            while (devices.Count > 0)  
            {  
                // Remove the first tablet device in the devices collection.  
                stylusLogicType.InvokeMember("OnTabletRemoved",  
                        BindingFlags.InvokeMethod | BindingFlags.Instance | BindingFlags.NonPublic,  
                        null, stylusLogic, new object[] { (uint)0 });  
            }                  
        }  
  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Interceptar entradas del lápiz óptico](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md)
