---
title: '&lt;httpWebRequest&gt; Element (Network Settings)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 1d1dce38e5188824ba1412d3f2a285bd2304f147
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32741973"
---
# <a name="lthttpwebrequestgt-element-network-settings"></a>&lt;httpWebRequest&gt; Element (Network Settings)
Personaliza los parámetros de solicitud Web.  
  
 \<configuration>  
\<System.NET >  
\<Configuración >  
\<httpWebRequest >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|**Attribute**|**Descripción**|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|Especifica la longitud máxima de un encabezado de respuesta, en kilobytes. El valor predeterminado es 64. Un valor de -1 indica que no va a imponerse ningún límite de tamaño de los encabezados de respuesta.|  
|`maximumErrorResponseLength`|Especifica la longitud máxima de una respuesta de error, en kilobytes. El valor predeterminado es 64. Un valor de -1 indica que no va a imponerse ningún límite de tamaño en la respuesta de error.|  
|`maximumUnauthorizedUploadLength`|Especifica la longitud máxima de una carga en respuesta a un código de error no autorizado, en bytes. El valor predeterminado es -1. Un valor de -1 indica que no va a imponerse ningún límite de tamaño en la carga.|  
|`useUnsafeHeaderParsing`|Especifica si está habilitado el análisis de encabezado no seguro. El valor predeterminado es `false`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|**Element**|**Descripción**|  
|-----------------|---------------------|  
|[Configuración](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Configura opciones de red básicas para el espacio de nombres <xref:System.Net>.|  
  
## <a name="remarks"></a>Comentarios  
 De manera predeterminada, .NET Framework aplica estrictamente RFC 2616 para analizar URI. Algunas respuestas del servidor pueden incluir caracteres de control en campos prohibidos, lo que hará que la <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> método produzca un <xref:System.Net.WebException>. Si **useUnsafeHeaderParsing** está establecido en **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> no se producirá en este caso; sin embargo, la aplicación será vulnerable a varios formatos de ataques de análisis de URI. La mejor solución es cambiar el servidor de modo que la respuesta no incluya caracteres de control.  
  
## <a name="configuration-files"></a>Archivos de configuración  
 Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar una mayor que la longitud máxima de encabezado normal.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpWebRequest  
        maximumResponseHeadersLength="128"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>  
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
