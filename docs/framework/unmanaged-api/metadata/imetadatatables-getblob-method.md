---
title: "IMetaDataTables::GetBlob (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetBlob
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetBlob
helpviewer_keywords:
- GetBlob method [.NET Framework metadata]
- IMetaDataTables::GetBlob method [.NET Framework metadata]
ms.assetid: 94667c1c-6d58-4aa7-b74e-530b11e2a276
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c777396c5020e738c3aade0217bc400aa595dd30
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetblob-method"></a><span data-ttu-id="ce193-102">IMetaDataTables::GetBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="ce193-102">IMetaDataTables::GetBlob Method</span></span>
<span data-ttu-id="ce193-103">Obtiene un puntero para el objeto binario grande (BLOB) en el índice de la columna especificada.</span><span class="sxs-lookup"><span data-stu-id="ce193-103">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce193-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce193-104">Syntax</span></span>  
  
```  
HRESULT GetBlob (  
    [in]  ULONG          ixBlob,  
    [out] ULONG          *pcbData,  
    [out] const void     **ppData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce193-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ce193-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="ce193-106">[in] La dirección de memoria del que se obtienen `ppData`.</span><span class="sxs-lookup"><span data-stu-id="ce193-106">[in] The memory address from which to get `ppData`.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="ce193-107">[out] Un puntero al tamaño, en bytes, de `ppData`.</span><span class="sxs-lookup"><span data-stu-id="ce193-107">[out] A pointer to the size, in bytes, of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="ce193-108">[out] Recupera un puntero a un puntero a los datos binarios.</span><span class="sxs-lookup"><span data-stu-id="ce193-108">[out] A pointer to a pointer to the binary data retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce193-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ce193-109">Requirements</span></span>  
 <span data-ttu-id="ce193-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce193-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce193-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ce193-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ce193-112">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ce193-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ce193-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce193-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce193-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce193-114">See Also</span></span>  
 [<span data-ttu-id="ce193-115">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ce193-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="ce193-116">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ce193-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)