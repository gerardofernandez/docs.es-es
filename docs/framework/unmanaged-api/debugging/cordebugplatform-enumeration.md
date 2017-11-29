---
title: "CorDebugPlatform (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugPlatformEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugPlatformEnum
helpviewer_keywords: CorDebugPlatformEnum enumeration [.NET Framework debugging]
ms.assetid: c5444816-7378-4521-afd3-bf5e4b5303d5
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 52842d40895a658ec9dbb1263f18c48ec999a0ef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugplatform-enumeration"></a><span data-ttu-id="c491a-102">CorDebugPlatform (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c491a-102">CorDebugPlatform Enumeration</span></span>
<span data-ttu-id="c491a-103">Proporciona valores de plataforma de destino que usan el [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="c491a-103">Provides target platform values that are used by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c491a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c491a-104">Syntax</span></span>  
  
```  
typedef enum CorDebugPlatform  
{  
    CORDB_PLATFORM_WINDOWS_X86,    // Windows on Intel x86  
    CORDB_PLATFORM_WINDOWS_AMD64,  // Windows x64 (AMD64, Intel EM64T)  
    CORDB_PLATFORM_WINDOWS_IA64,   // Windows on Intel IA-64  
    CORDB_PLATFORM_MAC_PPC,        // Macintosh OS on PowerPC  
    CORDB_PLATFORM_MAC_X86,        // Macintosh OS on Intel x86  
    CORDB_PLATFORM_WINDOWS_ARM,    // Windows on ARM  
    CORDB_PLATFORM_MAC_AMD64       // MacOS on Intel x64  
} CorDebugPlatform;  
```  
  
## <a name="members"></a><span data-ttu-id="c491a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="c491a-105">Members</span></span>  
  
|<span data-ttu-id="c491a-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="c491a-106">Member</span></span>|<span data-ttu-id="c491a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c491a-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c491a-108">CORDB_PLATFORM_WINDOWS_X86</span><span class="sxs-lookup"><span data-stu-id="c491a-108">CORDB_PLATFORM_WINDOWS_X86</span></span>|<span data-ttu-id="c491a-109">La plataforma de destino es Windows ejecutándose en hardware Intel x86.</span><span class="sxs-lookup"><span data-stu-id="c491a-109">The target platform is Windows running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="c491a-110">CORDB_PLATFORM_WINDOWS_AMD64</span><span class="sxs-lookup"><span data-stu-id="c491a-110">CORDB_PLATFORM_WINDOWS_AMD64</span></span>|<span data-ttu-id="c491a-111">La plataforma de destino es Windows de 64 bits ejecutándose en hardware AMD64 o Intel EM64T.</span><span class="sxs-lookup"><span data-stu-id="c491a-111">The target platform is 64 bit Windows running on AMD64 or Intel EM64T hardware.</span></span>|  
|<span data-ttu-id="c491a-112">CORDB_PLATFORM_WINDOWS_IA64</span><span class="sxs-lookup"><span data-stu-id="c491a-112">CORDB_PLATFORM_WINDOWS_IA64</span></span>|<span data-ttu-id="c491a-113">La plataforma de destino es Windows de 32 bits ejecutándose en hardware IA-64.</span><span class="sxs-lookup"><span data-stu-id="c491a-113">The target platform is 32 bit Windows running on Intel IA-64 hardware.</span></span>|  
|<span data-ttu-id="c491a-114">CORDB_PLATFORM_MAC_PPC</span><span class="sxs-lookup"><span data-stu-id="c491a-114">CORDB_PLATFORM_MAC_PPC</span></span>|<span data-ttu-id="c491a-115">La plataforma de destino es el sistema operativo de Macintosh ejecutándose en hardware PowerPC.</span><span class="sxs-lookup"><span data-stu-id="c491a-115">The target platform is the Macintosh operating system running on PowerPC hardware.</span></span>|  
|<span data-ttu-id="c491a-116">CORDB_PLATFORM_MAC_X86</span><span class="sxs-lookup"><span data-stu-id="c491a-116">CORDB_PLATFORM_MAC_X86</span></span>|<span data-ttu-id="c491a-117">La plataforma de destino es el sistema operativo de Macintosh ejecutándose en hardware Intel x86.</span><span class="sxs-lookup"><span data-stu-id="c491a-117">The target platform is the Macintosh operating system running on Intel x86 hardware.</span></span>|  
|<span data-ttu-id="c491a-118">CORDB_PLATFORM_WINDOWS_ARM</span><span class="sxs-lookup"><span data-stu-id="c491a-118">CORDB_PLATFORM_WINDOWS_ARM</span></span>|<span data-ttu-id="c491a-119">La plataforma de destino es el sistema operativo de Macintosh ejecutándose en hardware de ARM de Windows.</span><span class="sxs-lookup"><span data-stu-id="c491a-119">The target platform is the Macintosh operating system running on Windows ARM hardware.</span></span>|  
|<span data-ttu-id="c491a-120">CORDB_PLATFORM_MAC_AMD64</span><span class="sxs-lookup"><span data-stu-id="c491a-120">CORDB_PLATFORM_MAC_AMD64</span></span>|<span data-ttu-id="c491a-121">La plataforma de destino es el sistema operativo de Macintosh ejecutándose en hardware AMD64.</span><span class="sxs-lookup"><span data-stu-id="c491a-121">The target platform is the Macintosh operating system running on AMD64 hardware.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c491a-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c491a-122">Requirements</span></span>  
 <span data-ttu-id="c491a-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c491a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c491a-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c491a-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c491a-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c491a-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c491a-126">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c491a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
 <span data-ttu-id="c491a-127">Los miembros `CORDB_PLATFORM_WINDOWS_ARM` y `CORDB_PLATFORM_MAC_AMD64` están disponible en .NET Framework 4.5.2 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="c491a-127">The `CORDB_PLATFORM_WINDOWS_ARM` and `CORDB_PLATFORM_MAC_AMD64` members are available in the .NET Framework 4.5.2 and later versions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c491a-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="c491a-128">See Also</span></span>  
 [<span data-ttu-id="c491a-129">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="c491a-129">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)