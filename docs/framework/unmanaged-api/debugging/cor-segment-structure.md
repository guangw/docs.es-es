---
title: COR_SEGMENT (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_SEGMENT
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_SEGMENT
helpviewer_keywords: COR_SEGMENT structure [.NET Framework debugging]
ms.assetid: 93aeecb9-7fef-4545-8daf-f566dfc47084
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fc7a749f92149d7f0f5725aec6d90d72e0582c13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="corsegment-structure"></a><span data-ttu-id="e1480-102">COR_SEGMENT (Estructura)</span><span class="sxs-lookup"><span data-stu-id="e1480-102">COR_SEGMENT Structure</span></span>
<span data-ttu-id="e1480-103">Contiene información sobre una región de memoria en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="e1480-103">Contains information about a region of memory in the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1480-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e1480-104">Syntax</span></span>  
  
```  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;            
    CORDB_ADDRESS end;              
    CorDebugGenerationTypes gen;    
    ULONG heap;                     
} COR_SEGMENT;  
```  
  
## <a name="members"></a><span data-ttu-id="e1480-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="e1480-105">Members</span></span>  
  
|<span data-ttu-id="e1480-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="e1480-106">Member</span></span>|<span data-ttu-id="e1480-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1480-107">Description</span></span>|  
|------------|-----------------|  
|`start`|<span data-ttu-id="e1480-108">La dirección inicial de la región de memoria.</span><span class="sxs-lookup"><span data-stu-id="e1480-108">The starting address of the memory region.</span></span>|  
|`end`|<span data-ttu-id="e1480-109">La dirección final de la región de memoria.</span><span class="sxs-lookup"><span data-stu-id="e1480-109">The ending address of the memory region.</span></span>|  
|`gen`|<span data-ttu-id="e1480-110">A [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) miembro de enumeración que indica la generación de la región de memoria.</span><span class="sxs-lookup"><span data-stu-id="e1480-110">A [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) enumeration member that indicates the generation of the memory region.</span></span>|  
|`heap`|<span data-ttu-id="e1480-111">El número de montón en el que reside la región de memoria.</span><span class="sxs-lookup"><span data-stu-id="e1480-111">The heap number in which the memory region resides.</span></span> <span data-ttu-id="e1480-112">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e1480-112">See the Remarks section for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1480-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e1480-113">Remarks</span></span>  
 <span data-ttu-id="e1480-114">El `COR_SEGMENTS` estructura representa una región de memoria en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="e1480-114">The `COR_SEGMENTS` structure represents a region of memory in the managed heap.</span></span>  <span data-ttu-id="e1480-115">`COR_SEGMENTS`los objetos son miembros de la [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) objeto de colección, que se rellena mediante una llamada a la[icordebugprocess5:: Enumerateheapregions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="e1480-115">`COR_SEGMENTS` objects are members of the [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) collection object, which is populated by calling the[ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span>  
  
 <span data-ttu-id="e1480-116">El `heap` campo es el número de procesador, que se corresponde con el montón que se va a notificar.</span><span class="sxs-lookup"><span data-stu-id="e1480-116">The `heap` field is the processor number, which corresponds to the heap being reported.</span></span> <span data-ttu-id="e1480-117">Para los recolectores de elementos no utilizados de estación de trabajo, su valor siempre es cero, porque las estaciones de trabajo tienen solo un montón de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="e1480-117">For workstation garbage collectors, its value is always zero, because workstations have only one garbage collection heap.</span></span> <span data-ttu-id="e1480-118">Para recolectores de elementos no utilizados de servidor, su valor se corresponde con el procesador que está vinculado del montón.</span><span class="sxs-lookup"><span data-stu-id="e1480-118">For server garbage collectors, its value corresponds to the processor the heap is attached to.</span></span> <span data-ttu-id="e1480-119">Tenga en cuenta que puede haber más o menos recolección montones de procesadores reales debido a los detalles de implementación del recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="e1480-119">Note that there may be more or fewer garbage collection heaps than there are actual processors due to the implementation details of the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1480-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e1480-120">Requirements</span></span>  
 <span data-ttu-id="e1480-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1480-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1480-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1480-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1480-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1480-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1480-124">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1480-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1480-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1480-125">See Also</span></span>  
 [<span data-ttu-id="e1480-126">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="e1480-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="e1480-127">Depuración</span><span class="sxs-lookup"><span data-stu-id="e1480-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)