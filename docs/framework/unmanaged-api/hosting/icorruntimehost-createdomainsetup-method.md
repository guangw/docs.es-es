---
title: "ICorRuntimeHost::CreateDomainSetup (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.CreateDomainSetup
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::CreateDomainSetup
helpviewer_keywords:
- CreateDomainSetup method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomainSetup method [.NET Framework hosting]
ms.assetid: c21dab60-fb65-47d9-8a94-7fd47ca53b48
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca09788ea403e2a60d6de0cb6834fdc90261b770
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehostcreatedomainsetup-method"></a><span data-ttu-id="ed8b8-102">ICorRuntimeHost::CreateDomainSetup (Método)</span><span class="sxs-lookup"><span data-stu-id="ed8b8-102">ICorRuntimeHost::CreateDomainSetup Method</span></span>
<span data-ttu-id="ed8b8-103">Obtiene un puntero de interfaz de tipo IAppDomainSetup a un <xref:System.AppDomainSetup?displayProperty=nameWithType> instancia.</span><span class="sxs-lookup"><span data-stu-id="ed8b8-103">Gets an interface pointer of type IAppDomainSetup to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="ed8b8-104">`IAppDomainSetup`Proporciona métodos para configurar aspectos de un dominio de aplicación antes de que se crea.</span><span class="sxs-lookup"><span data-stu-id="ed8b8-104">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed8b8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed8b8-105">Syntax</span></span>  
  
```  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed8b8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ed8b8-106">Parameters</span></span>  
 `pAppDomainSetup`  
 <span data-ttu-id="ed8b8-107">[out] Un puntero de interfaz a un <xref:System.AppDomainSetup?displayProperty=nameWithType> instancia.</span><span class="sxs-lookup"><span data-stu-id="ed8b8-107">[out] An interface pointer to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="ed8b8-108">Este parámetro se escribe como `IUnknown`, por lo que los llamadores generalmente deben llamar a `QueryInterface` en este puntero para obtener un puntero de interfaz de tipo `IAppDomainSetup`.</span><span class="sxs-lookup"><span data-stu-id="ed8b8-108">This parameter is typed as `IUnknown`, so callers should generally call `QueryInterface` on this pointer to obtain an interface pointer of type `IAppDomainSetup`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed8b8-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ed8b8-109">Return Value</span></span>  
  
|<span data-ttu-id="ed8b8-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ed8b8-110">HRESULT</span></span>|<span data-ttu-id="ed8b8-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed8b8-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ed8b8-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ed8b8-112">S_OK</span></span>|<span data-ttu-id="ed8b8-113">La operación fue correcta.</span><span class="sxs-lookup"><span data-stu-id="ed8b8-113">The operation was successful.</span></span>|  
|<span data-ttu-id="ed8b8-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ed8b8-114">S_FALSE</span></span>|<span data-ttu-id="ed8b8-115">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="ed8b8-115">The operation failed to complete.</span></span>|  
|<span data-ttu-id="ed8b8-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ed8b8-116">E_FAIL</span></span>|<span data-ttu-id="ed8b8-117">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="ed8b8-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="ed8b8-118">Si el método devuelve E_FAIL, common language runtime (CLR) ya no es utilizable en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ed8b8-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="ed8b8-119">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ed8b8-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ed8b8-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ed8b8-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ed8b8-121">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ed8b8-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed8b8-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ed8b8-122">Remarks</span></span>  
 <span data-ttu-id="ed8b8-123">El puntero devuelto por este método normalmente se pasa como un parámetro a la [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="ed8b8-123">The pointer returned from this method is typically passed as a parameter to the [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed8b8-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ed8b8-124">Requirements</span></span>  
 <span data-ttu-id="ed8b8-125">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed8b8-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed8b8-126">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ed8b8-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ed8b8-127">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ed8b8-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed8b8-128">**Versión de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="ed8b8-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed8b8-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed8b8-129">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 <xref:System.AppDomainSetup>  
 <xref:System.IAppDomainSetup?displayProperty=nameWithType>  
 [<span data-ttu-id="ed8b8-130">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed8b8-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)