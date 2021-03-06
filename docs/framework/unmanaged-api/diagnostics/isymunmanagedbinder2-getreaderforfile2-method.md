---
title: ISymUnmanagedBinder2::GetReaderForFile2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2.GetReaderForFile2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2
helpviewer_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2 method [.NET Framework debugging]
- GetReaderForFile2 method [.NET Framework debugging]
ms.assetid: dd92dcaf-403c-464d-a254-21594985dddd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cea8a322fab6ef76873e668c622ac63e3a3f2862
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428230"
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a>ISymUnmanagedBinder2::GetReaderForFile2 (Método)
A partir de una interfaz de metadatos y un nombre de archivo, devuelve el valor correcto <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interfaz que se va a leer los símbolos de depuración asociados al módulo.  
  
 Este método proporciona una búsqueda más extensa para el archivo de programa (PDB) de la base de datos que la [ISymUnmanagedBinder:: GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) método.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `importer`  
 [in] Un puntero a la interfaz de importación de metadatos.  
  
 `fileName`  
 [in] Un puntero al nombre de archivo.  
  
 `searchPath`  
 [in] Un puntero a la ruta de acceso de búsqueda.  
  
 `searchPolicy`  
 [in] Un valor de la [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeración que especifica la directiva que se utilizará al realizar una búsqueda de un lector de símbolos.  
  
 `pRetVal`  
 [out] Un puntero que se establece en el valor devuelto <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interfaz.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym.idl, CorSym.h  
  
## <a name="remarks"></a>Comentarios  
 Esta versión del método puede buscar el archivo PDB en áreas distintas situada junto al módulo. La directiva de búsqueda puede controlarse mediante la combinación [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md). Por ejemplo, `AllowReferencePathAccess | AllowSymbolServerAccess` busca el archivo PDB junto al archivo ejecutable y en un servidor de símbolos, pero no consultar el registro o use la ruta de acceso en el archivo ejecutable. Si el `searchPath` se proporciona el parámetro, se buscará en esos directorios.  
  
## <a name="see-also"></a>Vea también  
 [ISymUnmanagedBinder2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [GetReaderForFile (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)
