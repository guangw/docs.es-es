---
title: "ICLRStrongName::GetHashFromAssemblyFile (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.GetHashFromAssemblyFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::GetHashFromAssemblyFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFile method [.NET Framework hosting]
- GetHashFromAssemblyFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 0b67ea03-d474-4605-acaa-57455790250c
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9a205f4225269f959efec9576bea047fb51ea946
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="ccee8-102">ICLRStrongName::GetHashFromAssemblyFile (Método)</span><span class="sxs-lookup"><span data-stu-id="ccee8-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="ccee8-103">Obtiene un valor hash del archivo de ensamblado especificado, utilizando el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="ccee8-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccee8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ccee8-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ccee8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ccee8-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="ccee8-106">[in] La ruta de acceso al archivo que se aplica un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="ccee8-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="ccee8-107">[entrada, salida] Una constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="ccee8-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="ccee8-108">Utilice un cero para el algoritmo hash predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ccee8-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="ccee8-109">[out] El búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="ccee8-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="ccee8-110">[in] El tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="ccee8-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="ccee8-111">[out] La devuelve el tamaño, en bytes, de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="ccee8-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ccee8-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ccee8-112">Return Value</span></span>  
 <span data-ttu-id="ccee8-113">`S_OK`Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (vea [valores HRESULT comunes](http://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).</span><span class="sxs-lookup"><span data-stu-id="ccee8-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccee8-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ccee8-114">Requirements</span></span>  
 <span data-ttu-id="ccee8-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccee8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccee8-116">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ccee8-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ccee8-117">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ccee8-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ccee8-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccee8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccee8-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ccee8-119">See Also</span></span>  
 [<span data-ttu-id="ccee8-120">GetHashFromAssemblyFileW (método)</span><span class="sxs-lookup"><span data-stu-id="ccee8-120">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)  
 [<span data-ttu-id="ccee8-121">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ccee8-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)