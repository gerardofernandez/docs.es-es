---
title: "ICorDebugStackWalk::GetContext (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStackWalk.GetContext Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStackWalk::GetContext
helpviewer_keywords:
- GetContext method, ICorDebugStackWalk interface [.NET Framework debugging]
- ICorDebugStackWalk::GetContext method [.NET Framework debugging]
ms.assetid: 081d1c95-152b-4797-8552-18453eb7b14b
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2bdd910862e7198d616e79ec732708f708959d26
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugstackwalkgetcontext-method"></a><span data-ttu-id="8c4ed-102">ICorDebugStackWalk::GetContext (Método)</span><span class="sxs-lookup"><span data-stu-id="8c4ed-102">ICorDebugStackWalk::GetContext Method</span></span>
<span data-ttu-id="8c4ed-103">Devuelve el contexto para el marco actual en el [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="8c4ed-103">Returns the context for the current frame in the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c4ed-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8c4ed-104">Syntax</span></span>  
  
```  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8c4ed-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8c4ed-105">Parameters</span></span>  
 `contextFlags`  
 <span data-ttu-id="8c4ed-106">[in] Marcas que indican el contenido solicitado del búfer de contexto (se define en WinNT.h).</span><span class="sxs-lookup"><span data-stu-id="8c4ed-106">[in] Flags that indicate the requested contents of the context buffer (defined in WinNT.h).</span></span>  
  
 `contextBufSize`  
 <span data-ttu-id="8c4ed-107">[in] El tamaño asignado del búfer de contexto.</span><span class="sxs-lookup"><span data-stu-id="8c4ed-107">[in] The allocated size of the context buffer.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="8c4ed-108">[out] El tamaño real del contexto.</span><span class="sxs-lookup"><span data-stu-id="8c4ed-108">[out] The actual size of the context.</span></span> <span data-ttu-id="8c4ed-109">Este valor debe ser menor o igual que el tamaño del búfer de contexto.</span><span class="sxs-lookup"><span data-stu-id="8c4ed-109">This value must be less than or equal to the size of the context buffer.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="8c4ed-110">[out] El búfer de contexto.</span><span class="sxs-lookup"><span data-stu-id="8c4ed-110">[out] The context buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c4ed-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8c4ed-111">Return Value</span></span>  
 <span data-ttu-id="8c4ed-112">Este método devuelve los siguientes HRESULT específicos así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="8c4ed-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8c4ed-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8c4ed-113">HRESULT</span></span>|<span data-ttu-id="8c4ed-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c4ed-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8c4ed-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="8c4ed-115">S_OK</span></span>|<span data-ttu-id="8c4ed-116">El contexto para el marco actual se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="8c4ed-116">The context for the current frame was successfully returned.</span></span>|  
|<span data-ttu-id="8c4ed-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8c4ed-117">E_FAIL</span></span>|<span data-ttu-id="8c4ed-118">No se pudo devolver el contexto.</span><span class="sxs-lookup"><span data-stu-id="8c4ed-118">The context could not be returned.</span></span>|  
|<span data-ttu-id="8c4ed-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)</span><span class="sxs-lookup"><span data-stu-id="8c4ed-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT BUFFER)</span></span>|<span data-ttu-id="8c4ed-120">El búfer de contexto es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="8c4ed-120">The context buffer is too small.</span></span>|  
|<span data-ttu-id="8c4ed-121">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="8c4ed-121">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="8c4ed-122">El puntero de marco ya está al final de la pila; por lo tanto, no puede tener acceso a ningún marco adicional.</span><span class="sxs-lookup"><span data-stu-id="8c4ed-122">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="8c4ed-123">Excepciones</span><span class="sxs-lookup"><span data-stu-id="8c4ed-123">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c4ed-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8c4ed-124">Remarks</span></span>  
 <span data-ttu-id="8c4ed-125">Porque desenredo solo restaura un subconjunto de los registros, como los registros no volátiles, el contexto puede no coincidir exactamente con el estado del registro en el momento de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8c4ed-125">Because unwinding restores only a subset of the registers, such as non-volatile registers, the context may not exactly match the register state at the time of the call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c4ed-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8c4ed-126">Requirements</span></span>  
 <span data-ttu-id="8c4ed-127">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c4ed-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c4ed-128">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c4ed-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c4ed-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c4ed-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c4ed-130">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c4ed-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c4ed-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c4ed-131">See Also</span></span>  
 [<span data-ttu-id="8c4ed-132">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="8c4ed-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="8c4ed-133">Depuración</span><span class="sxs-lookup"><span data-stu-id="8c4ed-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)