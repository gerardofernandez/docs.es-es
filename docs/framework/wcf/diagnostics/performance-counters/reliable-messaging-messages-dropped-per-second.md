---
title: Mensajes de mensajería de confianza quitados por segundo
ms.date: 03/30/2017
ms.assetid: a11b0b80-b242-48e1-b0bb-7f756db5486b
ms.openlocfilehash: 7722b32f99b302c5c272e095033879c9e04c7ee1
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44188925"
---
# <a name="reliable-messaging-messages-dropped-per-second"></a>Mensajes de mensajería de confianza quitados por segundo
Nombre de contador: sesiones de mensajería de confianza quitadas por segundo.  
  
## <a name="description"></a>Descripción  
 Número total de mensajes de mensajería de confianza que han sido quitados en este servicio en un segundo.  
  
 Este contador es de tipo de contador de rendimiento [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la siguiente fórmula.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
