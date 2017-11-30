---
title: "ICorDebugMergedAssemblyRecord::GetVersion (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 68fa2b1b7502f13876c6e613f012a0c78ab7c5d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="54f95-102">ICorDebugMergedAssemblyRecord::GetVersion (método)</span><span class="sxs-lookup"><span data-stu-id="54f95-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="54f95-103">Obtiene información de la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="54f95-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54f95-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54f95-104">Syntax</span></span>  
  
```  
HRESULT GetVersion(  
   [out] USHORT *pMajor,   
   [out] USHORT *pMinor,   
   [out] USHORT *pBuild,   
   [out] USHORT *pRevision  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="54f95-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="54f95-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="54f95-106">[out] Puntero al número de revisión principal.</span><span class="sxs-lookup"><span data-stu-id="54f95-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="54f95-107">[out] Puntero al número de revisión secundaria.</span><span class="sxs-lookup"><span data-stu-id="54f95-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="54f95-108">[out] Puntero al número de revisión de compilación.</span><span class="sxs-lookup"><span data-stu-id="54f95-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="54f95-109">[out] Puntero al número de revisión.</span><span class="sxs-lookup"><span data-stu-id="54f95-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54f95-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="54f95-110">Remarks</span></span>  
 <span data-ttu-id="54f95-111">Para obtener información sobre los números de versión del ensamblado, consulte el tema de la clase <xref:System.Version>.</span><span class="sxs-lookup"><span data-stu-id="54f95-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54f95-112">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="54f95-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54f95-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54f95-113">Requirements</span></span>  
 <span data-ttu-id="54f95-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54f95-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54f95-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54f95-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54f95-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54f95-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54f95-117">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54f95-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54f95-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="54f95-118">See Also</span></span>  
 [<span data-ttu-id="54f95-119">ICorDebugMergedAssemblyRecord (interfaz)</span><span class="sxs-lookup"><span data-stu-id="54f95-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="54f95-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="54f95-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)