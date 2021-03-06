---
title: FormatFromRawValue (función) (referencia de API no administrada)
description: FormatFromRawValue (función) convierte los datos de rendimiento sin procesar en un formato especificado.
ms.date: 11/21/2017
api_name:
- FormatFromRawValue
api_location:
- PerfCounter.dll
api_type:
- DLLExport
f1_keywords:
- FormatFromRawValue
helpviewer_keywords:
- FormatFromRawValue function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95ef445d41672c5c2895bd7115afb6a73a57e8f9
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44086142"
---
# <a name="formatfromrawvalue-function"></a>FormatFromRawValue (función)
Convierte un valor de datos de rendimiento sin procesar al formato especificado, o bien dos valores de datos de rendimiento sin procesar si la conversión de formato es de duración definida.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```  
int FormatFromRawValue (
   [in] uint                    dwCounterType, 
   [in] uint                    dwFormat, 
   [in] long*                   pTimeBase,
   [in] PDH_RAW_COUNTER*        pRawValue1,
   [in] PDH_RAW_COUNTER*        pRawValue2,
   [out] PDH_FMT_COUNTERVALUE*  pFmtValue
); 
```  

## <a name="parameters"></a>Parámetros

`dwCounterType`  
[in] El tipo de contador. Para obtener una lista de tipos de contador, vea [WMI Performance Counter Types](/windows/desktop/WmiSdk/wmi-performance-counter-types). `dwCounterType` puede ser cualquier tipo de contador excepto `PERF_LARGE_RAW_FRACTION` y `PERF_LARGE_RAW_BASE`. 

`dwFormat`  
[in] El formato que se va a convertir los datos de rendimiento sin procesar. Puede ser uno de los siguientes valores:

|Constante  |Valor  |Descripción |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |0x00000200 | Devuelve el valor calculado como un valor de punto flotante de precisión doble. | 
| `PDH_FMT_LARGE` | 0x00000400 | Devuelve el valor calculado como un entero de 64 bits. |
| `PDH_FMT_LONG` | 0x00000100 | Devuelve el valor calculado como un entero de 32 bits. |

Uno de los valores anteriores puede ser ORed con uno de los siguientes indicadores de escalado:

|Constante  |Valor  |Descripción |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | 0x00001000 | No se aplican los factores de escala del contador. |
| `PDH_FMT_1000` | 0x00002000 | Multiplica el valor final por 1.000. | 

`pTimeBase`  
[in] Un puntero a la base de tiempo, si es necesario para la conversión de formato. Si no es necesaria para la conversión de formato base la información de tiempo, se omite el valor de este parámetro.

`pRawValue1` [in] Un puntero a un [ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) estructura que representa un valor de rendimiento sin procesar.

`pRawValue2` [in] Un puntero a un [ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) estructura que representa un segundo valor de rendimiento sin procesar. Si no es necesario un segundo valor de rendimiento sin procesar, este parámetro debe ser `null`.

`pFmtValue` [out] Un puntero a un [ `PDH_FMT_COUNTERVALUE` ](https://msdn.microsoft.com/library/windows/desktop/aa373050(v=vs.85).aspx) estructura que recibe el valor de rendimiento con formato.

## <a name="return-value"></a>Valor devuelto

Esta función devuelve los valores siguientes:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `ERROR_SUCCESS` | 0 | La llamada de función es correcta. |
| `PDH_INVALID_ARGUMENT` | 0xC0000BBD | Un argumento requerido falta o es incorrecta. | 
| `PDH_INVALID_HANDLE` | 0xC0000BBC | El identificador no es un objeto PDH válido. |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [FormatFromRawValue](https://msdn.microsoft.com/library/ms231047(v=vs.85).aspx) función.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Biblioteca:** PerfCounter.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
