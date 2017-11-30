---
title: "ICLRDomainManager::SetPropertiesForDefaultAppDomain (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDomainManager.SetPropertiesForDefaultAppDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDomainManager::SetPropertiesForDefaultAppDomain
helpviewer_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
- SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 43e61c4b-c435-45ec-9ef6-c68403aa4200
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fabf42c16dc41e29ca3d14e00e76797fa8f2a9e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a><span data-ttu-id="af248-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="af248-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain Method</span></span>
<span data-ttu-id="af248-103">Establece las propiedades que se usarán para inicializar el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="af248-103">Sets properties that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af248-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af248-104">Syntax</span></span>  
  
```  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="af248-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="af248-105">Parameters</span></span>  
 `nProperties`  
 <span data-ttu-id="af248-106">[in] El número de entradas en `pwszPropertyNames` y `pwszPropertyValues`.</span><span class="sxs-lookup"><span data-stu-id="af248-106">[in] The number of entries in `pwszPropertyNames` and `pwszPropertyValues`.</span></span>  
  
 `pwszPropertyNames`  
 <span data-ttu-id="af248-107">[in] Una matriz de nombres de propiedad, o null si no hay ninguna propiedad.</span><span class="sxs-lookup"><span data-stu-id="af248-107">[in] An array of property names, or null if there are no properties.</span></span> <span data-ttu-id="af248-108">Actualmente, el nombre de propiedad solo es reconocido por este método es "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span><span class="sxs-lookup"><span data-stu-id="af248-108">Currently, the only property name that is recognized by this method is "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span></span>  
  
 `pwszPropertyValues`  
 <span data-ttu-id="af248-109">[in] Una matriz de valores de propiedad, o null si no hay ninguna propiedad.</span><span class="sxs-lookup"><span data-stu-id="af248-109">[in] An array of property values, or null if there are no properties.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af248-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="af248-110">Return Value</span></span>  
 <span data-ttu-id="af248-111">Este método devuelve los siguientes HRESULT específicos así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="af248-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="af248-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="af248-112">HRESULT</span></span>|<span data-ttu-id="af248-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="af248-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="af248-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="af248-114">S_OK</span></span>|<span data-ttu-id="af248-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="af248-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="af248-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span><span class="sxs-lookup"><span data-stu-id="af248-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span></span>|<span data-ttu-id="af248-117">`pwszPropertyNames`incluye un nombre de propiedad que no se reconoce por este método.</span><span class="sxs-lookup"><span data-stu-id="af248-117">`pwszPropertyNames` includes a property name that is not recognized by this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af248-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="af248-118">Remarks</span></span>  
 <span data-ttu-id="af248-119">El valor de propiedad de "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" es una lista de ensamblados que tienen el atributo conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> atributo (APTCA) con el <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> marca, que se van ha hacer visibles para los llamadores de confianza parcial en la aplicación predeterminada dominio.</span><span class="sxs-lookup"><span data-stu-id="af248-119">The property value for "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" is a list of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute with the <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> flag, which are to be made visible to partially trusted callers in the default application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af248-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="af248-120">Requirements</span></span>  
 <span data-ttu-id="af248-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af248-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af248-122">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="af248-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="af248-123">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="af248-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="af248-124">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af248-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af248-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="af248-125">See Also</span></span>  
 [<span data-ttu-id="af248-126">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="af248-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [<span data-ttu-id="af248-127">ICLRDomainManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="af248-127">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)