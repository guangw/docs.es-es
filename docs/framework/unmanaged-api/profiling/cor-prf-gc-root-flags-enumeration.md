---
title: "COR_PRF_GC_ROOT_FLAGS (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_GC_ROOT_FLAGS
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_GC_ROOT_FLAGS
helpviewer_keywords: COR_PRF_GC_ROOT_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 4611ee6f-0f05-4d84-91e1-e83d5e7dd7e4
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f340f9ad83d28b00054a0997bf4b60c750192bef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corprfgcrootflags-enumeration"></a><span data-ttu-id="d1f23-102">COR_PRF_GC_ROOT_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d1f23-102">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>
<span data-ttu-id="d1f23-103">Indica una propiedad de una raíz de la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d1f23-103">Indicates a property of a garbage collection root.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1f23-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1f23-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_ROOT_PINNING = 0x1,  
    COR_PRF_GC_ROOT_WEAKREF = 0x2,  
    COR_PRF_GC_ROOT_INTERIOR = 0x4,  
    COR_PRF_GC_ROOT_REFCOUNTED = 0x8,  
} COR_PRF_GC_ROOT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="d1f23-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="d1f23-105">Members</span></span>  
  
|<span data-ttu-id="d1f23-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="d1f23-106">Member</span></span>|<span data-ttu-id="d1f23-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1f23-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_PINNING`|<span data-ttu-id="d1f23-108">La raíz impide que una recolección de elementos al mover el objeto.</span><span class="sxs-lookup"><span data-stu-id="d1f23-108">The root prevents a garbage collection from moving the object.</span></span>|  
|`COR_PRF_GC_ROOT_WEAKREF`|<span data-ttu-id="d1f23-109">La raíz no impide la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="d1f23-109">The root does not prevent garbage collection.</span></span>|  
|`COR_PRF_GC_ROOT_INTERIOR`|<span data-ttu-id="d1f23-110">La raíz hace referencia a un campo de objeto en lugar de al propio objeto.</span><span class="sxs-lookup"><span data-stu-id="d1f23-110">The root refers to a field of the object rather than the object itself.</span></span>|  
|`COR_PRF_GC_ROOT_REFCOUNTED`|<span data-ttu-id="d1f23-111">La raíz impide la recolección de elementos si el recuento de referencias del objeto es un valor determinado.</span><span class="sxs-lookup"><span data-stu-id="d1f23-111">The root prevents garbage collection if the reference count of the object is a certain value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1f23-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d1f23-112">Remarks</span></span>  
 <span data-ttu-id="d1f23-113">`COR_PRF_GC_ROOT_FLAGS`es una máscara de bits que proporciona información adicional sobre raíces especiales.</span><span class="sxs-lookup"><span data-stu-id="d1f23-113">`COR_PRF_GC_ROOT_FLAGS` is a bitmask that provides additional information about special roots.</span></span> <span data-ttu-id="d1f23-114">Sin embargo, no todas las raíces son especiales.</span><span class="sxs-lookup"><span data-stu-id="d1f23-114">However, not all roots are special.</span></span> <span data-ttu-id="d1f23-115">Por ejemplo, algunas raíces no son referencias débiles, punteros interiores, anclados o recuento de referencias.</span><span class="sxs-lookup"><span data-stu-id="d1f23-115">For example, some roots are not weak references, interior pointers, pinned, or reference-counted.</span></span> <span data-ttu-id="d1f23-116">Para esas raíces, no hay ningún indicador para transmitir.</span><span class="sxs-lookup"><span data-stu-id="d1f23-116">For such roots, there are no flags to convey.</span></span> <span data-ttu-id="d1f23-117">Por lo tanto, los métodos que utilizan esta enumeración, como el [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) método send 0 para la máscara de bits de marcas, que indica que todas las marcas están desactivadas.</span><span class="sxs-lookup"><span data-stu-id="d1f23-117">Therefore, methods that use this enumeration, such as the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method, send 0 for the flags bitmask, indicating that all flags are turned off.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1f23-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d1f23-118">Requirements</span></span>  
 <span data-ttu-id="d1f23-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1f23-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1f23-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d1f23-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d1f23-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1f23-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1f23-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1f23-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1f23-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1f23-123">See Also</span></span>  
 [<span data-ttu-id="d1f23-124">Enumeraciones de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d1f23-124">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)