---
title: Compatibilidad de versiones en .NET Framework
ms.custom: updateeachrelease
ms.date: 04/10/2018
helpviewer_keywords:
- .NET Framework, version compatibility
- .NET Framework 4.5, compatibility with earlier versions
- .NET Framework versions, compatibility
ms.assetid: 2f25e522-456a-48c3-8a53-e5f39275649f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d3d0e2dbd57d9581d1c8b0ca42d1e9d556d8905
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44198509"
---
# <a name="version-compatibility-in-the-net-framework"></a>Compatibilidad de versiones en .NET Framework
La compatibilidad con versiones anteriores significa que una aplicación desarrollada en una versión determinada de una plataforma se ejecutará en las versiones posteriores de esa plataforma. .NET Framework intenta maximizar la compatibilidad con versiones anteriores. El código fuente escrito para una versión de .NET Framework debe compilarse en versiones posteriores de .NET Framework y los binarios que se ejecutan en una versión de .NET Framework deberán comportarse del mismo modo en versiones posteriores de .NET Framework.  
  
<a name="Apps"></a>   
## <a name="version-compatibility-for-apps"></a>Compatibilidad de versiones de las aplicaciones  
 De manera predeterminada, una aplicación se ejecuta en la versión de .NET Framework para la que se creó. Si esa versión no está presente y en el archivo de configuración de la aplicación no se han definido las versiones compatibles, puede producirse un error de inicialización de .NET Framework. En este caso, el intento de ejecutar la aplicación no se realizará correctamente.  
  
 Para definir las versiones concretas en las que se ejecuta la aplicación, agregue uno o varios elementos [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) archivo de configuración de la aplicación. Cada elemento `<supportedRuntime>` muestra una versión compatible del runtime; el primer elemento especifica la versión de mayor preferencia y el último, la de menor preferencia.  
  
```xml  
<configuration>  
   <startup>  
      <supportedRuntime version="v2.0.50727" />  
      <supportedRuntime version="v4.0" />  
   </startup>  
</configuration>  
```  
  
 Para más información, consulte [Cómo: Configurar una aplicación para admitir .NET Framework 4 o 4.x](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md).  
  
## <a name="version-compatibility-for-components"></a>Compatibilidad de versiones de los componentes  
 Una aplicación puede controlar la versión de .NET Framework en la que se ejecuta, pero un componente no puede hacerlo. Los componentes y las bibliotecas de clases se cargan en el contexto de una aplicación determinada y, por consiguiente, se ejecutan automáticamente en la versión de .NET Framework de la aplicación.  
  
 Debido a esta restricción, las garantías de compatibilidad son especialmente importantes en los componentes. A partir de .NET Framework 4, puede especificar el grado en el que se espera que un componente siga siendo compatible entre diversas versiones aplicando el atributo <xref:System.Runtime.Versioning.ComponentGuaranteesAttribute?displayProperty=nameWithType> a dicho componente. Las herramientas pueden usar este atributo para detectar posibles infracciones de la garantía de compatibilidad en futuras versiones de un componente.  
  
## <a name="backward-compatibility-and-the-net-framework-45"></a>Compatibilidad con versiones anteriores de .NET Framework 4.5  
 .NET Framework 4.5 y versiones posteriores son compatibles con las aplicaciones creadas con versiones anteriores de .NET Framework. Es decir, las aplicaciones y los componentes creados con versiones anteriores funcionarán sin necesidad de modificación en .NET Framework 4.5 y versiones posteriores. Pero, de forma predeterminada, las aplicaciones se ejecutan en la versión de Common Language Runtime para la que se han desarrollado, por lo que puede tener que proporcionar un archivo de configuración para permitir que la aplicación se ejecute en .NET Framework 4.5 o versiones posteriores. Para más información, consulte la sección [Compatibilidad de versiones de las aplicaciones](#Apps), anteriormente en este artículo.  
  
 En la práctica, esta compatibilidad puede verse interrumpida por cambios en apariencia intrascendentes realizados en .NET Framework y cambios en las técnicas de programación. Por ejemplo, las mejoras de rendimiento realizadas en .NET Framework 4.5 pueden provocar una condición de carrera que no se daba en versiones anteriores. De igual forma, si se usa una ruta de acceso codificada de forma rígida en los ensamblados .NET Framework, se realiza una comparación de igualdad con una determinada versión de .NET Framework y se obtiene el valor de un campo privado usando la reflexión, no habrá compatibilidad con versiones anteriores. Además, cada una de las versiones de .NET Framework contiene revisiones de errores y cambios relacionados con la seguridad que pueden afectar a la compatibilidad de algunas aplicaciones y componentes.  
  
 Si la aplicación o el componente no funciona como se esperaba en .NET Framework 4.5 (o en sus versiones secundarias, [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1 o 4.7.2), use las listas de comprobación siguientes:  
  
-  Si la aplicación se ha desarrollado para ejecutarse en cualquier versión de .NET Framework a partir de .NET Framework 4.0, vea [Compatibilidad de aplicaciones en .NET Framework](application-compatibility.md) para generar listas de cambios entre la versión de .NET Framework de destino y la versión en la que se ejecuta la aplicación.  

- Si tiene una aplicación de .NET Framework 3.5, vea también [Problemas de migración de .NET Framework 4](../../../docs/framework/migration-guide/net-framework-4-migration-issues.md).

- Si tiene una aplicación de .NET Framework 2.0, vea también [Cambios en .NET Framework 3.5 SP1](https://go.microsoft.com/fwlink/?LinkId=186989).

- Si tiene una aplicación de .NET Framework 1.1, vea también [Cambios en .NET Framework 2.0](https://go.microsoft.com/fwlink/?LinkID=125263).  
  
-   Si va a volver a compilar código fuente existente para ejecutarlo en .NET Framework 4.5 o en sus versiones secundarias, o si va a desarrollar una nueva versión de una aplicación o un componente para [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] o sus versiones secundarias a partir de una base de código fuente existente, vea [Lo obsoleto en la biblioteca de clases .NET Framework](../../../docs/framework/whats-new/whats-obsolete.md) para conocer los miembros y tipos obsoletos, y aplique las soluciones indicadas. (El código compilado previamente seguirá ejecutándose con los tipos y miembros que se han marcado como obsoletos).  
  
-   Si considera que un cambio de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] dañó la aplicación, consulte [Esquema de la configuración de Common Language Runtime](../../../docs/framework/configure-apps/file-schema/runtime/index.md) para determinar si puede usar una configuración en tiempo de ejecución en el archivo de configuración de la aplicación para restaurar el comportamiento anterior.  
  
-   Si se produce un problema que no está documentado, abra una incidencia en el [sitio de la comunidad de desarrolladores de .NET](https://developercommunity.visualstudio.com/spaces/61/index.html) o en el [repositorio de GitHub de Microsoft/dotnet](https://github.com/microsoft/dotnet/issues).
  
## <a name="compatibility-and-side-by-side-execution"></a>Compatibilidad y ejecución en paralelo  
 Si no encuentra una solución conveniente para su problema, recuerde que .NET Framework 4.5 (o sus versiones secundarias) se ejecuta en paralelo con las versiones 1.1, 2.0 y 3.5, y es una actualización en contexto que reemplaza la versión 4. En el caso de las aplicaciones dirigidas a las versiones 1.1, 2.0 y 3.5, puede instalar la versión adecuada de .NET Framework en el equipo de destino para ejecutar la aplicación en su entorno más conveniente. Para más información acerca de la ejecución en paralelo, consulte [Ejecución en paralelo](../../../docs/framework/deployment/side-by-side-execution.md).  
  
## <a name="see-also"></a>Vea también  
 [Novedades](../../../docs/framework/whats-new/index.md)  
 [Lo obsoleto en la biblioteca de clases](../../../docs/framework/whats-new/whats-obsolete.md)  
 [Compatibilidad de aplicaciones](../../../docs/framework/migration-guide/application-compatibility.md)  
 [Directiva de ciclo de vida de soporte técnico de Microsoft .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=248212)  
 [Problemas de migración de .NET Framework 4](../../../docs/framework/migration-guide/net-framework-4-migration-issues.md)
