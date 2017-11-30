---
title: "ICorProfilerCallback3::ProfilerAttachComplete (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback3.ProfilerAttachComplete Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback3::ProfilerAttachComplete
helpviewer_keywords:
- ProfilerAttachComplete method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerAttachComplete method [.NET Framework profiling]
ms.assetid: 257d6076-06e0-4d93-bb33-651fbb2b92d7
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0bf1e535c6270660797554c38a0b031df82f0925
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback3profilerattachcomplete-method"></a><span data-ttu-id="4a7d2-102">ICorProfilerCallback3::ProfilerAttachComplete (Método)</span><span class="sxs-lookup"><span data-stu-id="4a7d2-102">ICorProfilerCallback3::ProfilerAttachComplete Method</span></span>
<span data-ttu-id="4a7d2-103">Llamado por common language runtime (CLR) para indicar que el generador de perfiles puede llamar ahora a la [ICorProfilerInfo3:: EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) y [ICorProfilerInfo3:: EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md) métodos de puesta al día.</span><span class="sxs-lookup"><span data-stu-id="4a7d2-103">Called by the common language runtime (CLR) to indicate that the profiler can now call the [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) and [ICorProfilerInfo3::EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md) catch-up methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a7d2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4a7d2-104">Syntax</span></span>  
  
```  
HRESULT ProfilerAttachComplete ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="4a7d2-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4a7d2-105">Remarks</span></span>  
 <span data-ttu-id="4a7d2-106">El `ProfilerAttachComplete` devolución de llamada se emite después de la [ICorProfilerCallback3:: InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) se llama al método.</span><span class="sxs-lookup"><span data-stu-id="4a7d2-106">The `ProfilerAttachComplete` callback is issued after the [ICorProfilerCallback3::InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) method is called.</span></span> <span data-ttu-id="4a7d2-107">Indica que:</span><span class="sxs-lookup"><span data-stu-id="4a7d2-107">It indicates the following:</span></span>  
  
-   <span data-ttu-id="4a7d2-108">Las devoluciones de llamada que solicitó el generador de perfiles en `InitializeForAttach` se han activado.</span><span class="sxs-lookup"><span data-stu-id="4a7d2-108">The callbacks that were requested by the profiler in `InitializeForAttach` have been activated.</span></span>  
  
-   <span data-ttu-id="4a7d2-109">El generador de perfiles ya puede poner al día los identificadores asociados sin preocuparse sobre las notificaciones que faltan.</span><span class="sxs-lookup"><span data-stu-id="4a7d2-109">The profiler can now perform catch-up on the associated IDs without being concerned about missing notifications.</span></span>  
  
 <span data-ttu-id="4a7d2-110">CLR pasa por alto el valor devuelto por esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="4a7d2-110">The CLR ignores the return value from this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a7d2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4a7d2-111">Requirements</span></span>  
 <span data-ttu-id="4a7d2-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a7d2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a7d2-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4a7d2-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4a7d2-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a7d2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a7d2-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a7d2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a7d2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a7d2-116">See Also</span></span>  
 [<span data-ttu-id="4a7d2-117">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4a7d2-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="4a7d2-118">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4a7d2-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="4a7d2-119">Interfaces de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="4a7d2-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="4a7d2-120">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="4a7d2-120">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)