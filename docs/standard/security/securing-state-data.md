---
title: Proteger los datos de estado
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- security [.NET Framework], state data
- code security, state data
- secure coding, state data
- state data security
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3c821177ca897e617885425217ac0b6659b5ea6e
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2018
ms.locfileid: "44493594"
---
# <a name="securing-state-data"></a>Proteger los datos de estado
Las aplicaciones que administran datos confidenciales o realizan cualquier tipo de decisiones de seguridad necesitan mantener los datos bajo control y no pueden permitir que otro código potencialmente malintencionado acceda directamente a los datos. La mejor manera de proteger los datos en memoria es declarar los datos como variables privadas o internas (con el ámbito limitado al mismo ensamblado). Sin embargo, incluso estos datos están sujetos a acceso, por lo que debe tenerse en cuenta lo siguiente:  
  
-   Al usar mecanismos de reflexión, se puede obtener y establecer miembros privados en el código de plena confianza al que puede hacer referencia el objeto.  
  
-   Con la serialización, el código de plena confianza puede obtener y establecer eficazmente miembros privados si pueden acceder a los datos correspondientes en el formulario serializado del objeto.  
  
-   En la depuración, se pueden leer estos datos.  
  
 Asegúrese de que ninguno de sus métodos o propiedades expone estos valores de manera involuntaria.  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de codificación segura](../../../docs/standard/security/secure-coding-guidelines.md)
