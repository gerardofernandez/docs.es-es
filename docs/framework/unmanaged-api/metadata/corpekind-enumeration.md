---
title: "CorPEKind (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorPEKind
api_location: mscoree.dll
api_type: COM
f1_keywords: CorPEKind
helpviewer_keywords: CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 06e28a7e926d888c7c9274900ba90ac990fbb0e5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corpekind-enumeration"></a><span data-ttu-id="5b049-102">CorPEKind (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="5b049-102">CorPEKind Enumeration</span></span>
<span data-ttu-id="5b049-103">Contiene valores que describen un archivo ejecutable portable (PE), tal como lo devuelve una llamada a [IMetaDataImport2:: GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).</span><span class="sxs-lookup"><span data-stu-id="5b049-103">Contains values that describe a portable executable (PE) file, as returned from a call to [IMetaDataImport2::GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b049-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b049-104">Syntax</span></span>  
  
```  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a><span data-ttu-id="5b049-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="5b049-105">Members</span></span>  
  
|<span data-ttu-id="5b049-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="5b049-106">Member</span></span>|<span data-ttu-id="5b049-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b049-107">Description</span></span>|  
|------------|-----------------|  
|`peNot`|<span data-ttu-id="5b049-108">Indica que no es un archivo PE.</span><span class="sxs-lookup"><span data-stu-id="5b049-108">Indicates that this is not a PE file.</span></span>|  
|`peILOnly`|<span data-ttu-id="5b049-109">Indica que este archivo PE contiene sólo código administrado.</span><span class="sxs-lookup"><span data-stu-id="5b049-109">Indicates that this PE file contains only managed code.</span></span>|  
|`pe32BitRequired`|<span data-ttu-id="5b049-110">Indica que este archivo PE efectúa llamadas a Win32.</span><span class="sxs-lookup"><span data-stu-id="5b049-110">Indicates that this PE file makes Win32 calls.</span></span>|  
|`pe32Plus`|<span data-ttu-id="5b049-111">Indica que este archivo PE se ejecuta en una plataforma de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="5b049-111">Indicates that this PE file runs on a 64-bit platform.</span></span>|  
|`pe32Unmanaged`|<span data-ttu-id="5b049-112">Indica que este archivo PE es código nativo.</span><span class="sxs-lookup"><span data-stu-id="5b049-112">Indicates that this PE file is native code.</span></span>|  
|<span data-ttu-id="5b049-113">pe32BitPreferred</span><span class="sxs-lookup"><span data-stu-id="5b049-113">pe32BitPreferred</span></span>|<span data-ttu-id="5b049-114">Indica que este archivo PE es independiente de la plataforma y prefiere que se va a cargar en un entorno de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="5b049-114">Indicates that this PE file is platform-neutral and prefers to be loaded in a 32-bit environment.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b049-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5b049-115">Remarks</span></span>  
 <span data-ttu-id="5b049-116">Estos valores pueden utilizarse en combinaciones bit a bit.</span><span class="sxs-lookup"><span data-stu-id="5b049-116">These values can be used in bitwise combinations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b049-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5b049-117">Requirements</span></span>  
 <span data-ttu-id="5b049-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b049-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b049-119">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="5b049-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="5b049-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b049-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b049-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b049-121">See Also</span></span>  
 [<span data-ttu-id="5b049-122">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="5b049-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)