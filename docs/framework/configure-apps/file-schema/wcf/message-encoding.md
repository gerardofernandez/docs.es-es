---
title: Codificación de mensajes
ms.date: 03/30/2017
ms.assetid: f30ee941-aca9-4c67-82a5-421568496f07
ms.openlocfilehash: cdfa83b722492a8b2a7b118ff70134916ed824fb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752499"
---
# <a name="message-encoding"></a>Codificación de mensajes
Codificar es el proceso de transformar un conjunto de caracteres Unicode en una secuencia de bytes. La descodificación es el proceso inverso. Windows Communication Foundation (WCF) incluye tres tipos de codificación para los mensajes SOAP: Texto, Binario y Mecanismo de optimización de transmisión del mensaje (MTOM).  
  
 La sección de configuración `binaryMessageEncoding` especifica la codificación de caracteres y control de versiones de mensaje usados para los mensajes XML basados en binario. El codificador del mensaje binario codifica los mensajes de Windows Communication Foundation (WCF) en binario en la conexión. Aunque esta codificación realiza transmisiones muy rápidas de mensajes, la interoperabilidad basada en estándares WS-* se pierde.  
  
 La sección de configuración `mtomMessageEncoding` especifica la codificación de caracteres y la versión del mensaje utilizado para un mensaje que utiliza una codificación del mecanismo de optimización de transmisión del mensaje (MTOM). (MTOM) es una tecnología eficaz para transmitir los datos binarios en mensajes de Windows Communication Foundation (WCF). El codificador MTOM intenta equilibrar la eficacia y la interoperabilidad. El codificador MTOM transmite la mayoría del XML en formato de texto, pero optimiza bloques grandes de datos binarios transmitiéndolos como son, sin convertirlos en texto.  
  
 La sección de configuración `textMessageEncoding` especifica un codificador de texto utilizado para crear mensajes basados en texto en la conexión. Los mensajes generados por este codificador son adecuados para la interoperabilidad basada en WS - *. Un servicio web o un cliente de servicios web, por lo general, pueden entender XML textual. Sin embargo, transmitir bloques grandes de datos binarios como texto es el método menos eficaz para codificar mensajes XML.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)  
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [Elección de un codificador de mensajes](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
