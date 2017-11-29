---
title: Interfaz ICorDebugProcess6
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 34a10ac2-882c-4797-8369-f120e8e640c7
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 222007d03d8ace00f97c01cf2a02f0dc293bbf78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess6-interface"></a><span data-ttu-id="4e20a-102">Interfaz ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="4e20a-102">ICorDebugProcess6 Interface</span></span>
<span data-ttu-id="4e20a-103">Extiende lógicamente la ICorDebugProcess (interfaz) para habilitar características como la descodificación de eventos de depuración administrados que están codificados en eventos de depuración de excepción nativos o la división de módulos virtuales.</span><span class="sxs-lookup"><span data-stu-id="4e20a-103">Logically extends the ICorDebugProcess interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4e20a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="4e20a-104">Methods</span></span>  
  
|<span data-ttu-id="4e20a-105">Método</span><span class="sxs-lookup"><span data-stu-id="4e20a-105">Method</span></span>|<span data-ttu-id="4e20a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="4e20a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4e20a-107">Método DecodeEvent</span><span class="sxs-lookup"><span data-stu-id="4e20a-107">DecodeEvent Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md)|<span data-ttu-id="4e20a-108">Descodifica los eventos de depuración administrados encapsulados en la carga de los eventos de depuración de excepción nativos especialmente diseñados.</span><span class="sxs-lookup"><span data-stu-id="4e20a-108">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>|  
|[<span data-ttu-id="4e20a-109">Método EnableVirtualModuleSplitting</span><span class="sxs-lookup"><span data-stu-id="4e20a-109">EnableVirtualModuleSplitting Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md)|<span data-ttu-id="4e20a-110">Habilita o deshabilita la división de módulos virtuales.</span><span class="sxs-lookup"><span data-stu-id="4e20a-110">Enables or disables virtual module splitting.</span></span>|  
|[<span data-ttu-id="4e20a-111">GetCode (método)</span><span class="sxs-lookup"><span data-stu-id="4e20a-111">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getcode-method.md)|<span data-ttu-id="4e20a-112">Obtiene información sobre el código administrado en una dirección de código determinado.</span><span class="sxs-lookup"><span data-stu-id="4e20a-112">Gets information about the managed code at a particular code address.</span></span>|  
|[<span data-ttu-id="4e20a-113">Método GetExportStepInfo</span><span class="sxs-lookup"><span data-stu-id="4e20a-113">GetExportStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md)|<span data-ttu-id="4e20a-114">Proporciona información sobre las funciones exportadas en tiempo de ejecución para ayudar a recorrer el código administrado.</span><span class="sxs-lookup"><span data-stu-id="4e20a-114">Provides information on runtime exported functions to help step through managed code.</span></span>|  
|[<span data-ttu-id="4e20a-115">Método MarkDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="4e20a-115">MarkDebuggerAttached Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-markdebuggerattached-method.md)|<span data-ttu-id="4e20a-116">Cambia el estado interno del código que se está depurando para que el método <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> de la biblioteca de clases .NET Framework devuelva `true`.</span><span class="sxs-lookup"><span data-stu-id="4e20a-116">Changes the internal state of the debugee so that the <xref:System.Diagnostics.Debugger.IsAttached%2A?displayProperty=nameWithType> method in the .NET Framework Class Library returns `true`.</span></span>|  
|[<span data-ttu-id="4e20a-117">Método ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="4e20a-117">ProcessStateChanged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)|<span data-ttu-id="4e20a-118">Notifica a [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) que está ejecutando el proceso.</span><span class="sxs-lookup"><span data-stu-id="4e20a-118">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e20a-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4e20a-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4e20a-120">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4e20a-120">The interface is available with .NET Native only.</span></span> <span data-ttu-id="4e20a-121">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="4e20a-121">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e20a-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e20a-122">Requirements</span></span>  
 <span data-ttu-id="4e20a-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e20a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e20a-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e20a-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e20a-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e20a-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e20a-126">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e20a-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e20a-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e20a-127">See Also</span></span>  
 [<span data-ttu-id="4e20a-128">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4e20a-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4e20a-129">Depuración</span><span class="sxs-lookup"><span data-stu-id="4e20a-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)