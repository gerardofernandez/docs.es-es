---
title: PrivacyNoticeBindingElement
ms.date: 03/30/2017
ms.assetid: 0cf110b1-e25b-4d67-986b-10cb04dc4826
ms.openlocfilehash: a4ae5153525d5468955a09d19e534c00114c6530
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485123"
---
# <a name="privacynoticebindingelement"></a>PrivacyNoticeBindingElement
PrivacyNoticeBindingElement  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class PrivacyNoticeBindingElement : BindingElement  
{  
  sint32 PrivacyNoticeVersion;  
  string Url;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase PrivacyNoticeBindingElement no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase PrivacyNoticeBindingElement tiene las propiedades siguientes:  
  
### <a name="privacynoticeversion"></a>PrivacyNoticeVersion  
 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 La versión del aviso de privacidad.  
  
### <a name="url"></a>Dirección URL  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 La dirección URL en la que se encuentra el aviso de privacidad.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
