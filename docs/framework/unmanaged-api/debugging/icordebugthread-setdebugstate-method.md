---
title: "ICorDebugThread::SetDebugState (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.SetDebugState
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::SetDebugState
helpviewer_keywords:
- ICorDebugThread::SetDebugState method [.NET Framework debugging]
- SetDebugState method [.NET Framework debugging]
ms.assetid: 6382bdf6-d488-4952-b653-cb09b6e1c6c2
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 01f84c7126a4017a8d3b199f94eb497fae8e1a49
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadsetdebugstate-method"></a><span data-ttu-id="62546-102">ICorDebugThread::SetDebugState (Método)</span><span class="sxs-lookup"><span data-stu-id="62546-102">ICorDebugThread::SetDebugState Method</span></span>
<span data-ttu-id="62546-103">Establece marcas que describen el estado de depuración de esta instancia de ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="62546-103">Sets flags that describe the debugging state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62546-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62546-104">Syntax</span></span>  
  
```  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62546-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="62546-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="62546-106">[in] Una combinación bit a bit de valores de enumeración CorDebugThreadState que especifican el estado de depuración de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="62546-106">[in] A bitwise combination of CorDebugThreadState enumeration values that specify the debugging state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62546-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="62546-107">Remarks</span></span>  
 <span data-ttu-id="62546-108">`SetDebugState`establece el estado de depuración actual del subproceso.</span><span class="sxs-lookup"><span data-stu-id="62546-108">`SetDebugState` sets the current debug state of the thread.</span></span> <span data-ttu-id="62546-109">(El "estado de depuración actual" representa el estado de depuración si el proceso puede continuar, no el estado actual real). El valor normal para esto es THREAD_RUNNING.</span><span class="sxs-lookup"><span data-stu-id="62546-109">(The "current debug state" represents the debug state if the process were to be continued, not the actual current state.) The normal value for this is THREAD_RUNNING.</span></span> <span data-ttu-id="62546-110">Sólo el depurador puede afectar el estado de depuración de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="62546-110">Only the debugger can affect the debug state of a thread.</span></span> <span data-ttu-id="62546-111">Estados de depuración durante las continuaciones, por lo que si desea mantener un subproceso THREAD_SUSPENDed en varias continuaciones, puede establecerlo una vez y después no tienen que preocuparse sobre él.</span><span class="sxs-lookup"><span data-stu-id="62546-111">Debug states do last across continues, so if you want to keep a thread THREAD_SUSPENDed over multiple continues, you can set it once and thereafter not have to worry about it.</span></span> <span data-ttu-id="62546-112">Subprocesos de suspender y reanudar el proceso pueden causar interbloqueos, aunque es poco probable que normalmente.</span><span class="sxs-lookup"><span data-stu-id="62546-112">Suspending threads and resuming the process can cause deadlocks, though it's usually unlikely.</span></span> <span data-ttu-id="62546-113">Esto es una cualidad intrínseca de subprocesos y procesos y es por diseño.</span><span class="sxs-lookup"><span data-stu-id="62546-113">This is an intrinsic quality of threads and processes and is by-design.</span></span> <span data-ttu-id="62546-114">Un depurador asincrónicamente puede interrumpir y reanudar los subprocesos para romper el interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="62546-114">A debugger can asynchronously break and resume the threads to break the deadlock.</span></span> <span data-ttu-id="62546-115">Si el estado de usuario del subproceso incluye USER_UNSAFE_POINT, a continuación, el subproceso puede bloquear una colección de elementos no utilizados (GC).</span><span class="sxs-lookup"><span data-stu-id="62546-115">If the thread's user state includes USER_UNSAFE_POINT, then the thread may block a garbage collection (GC).</span></span> <span data-ttu-id="62546-116">Esto significa que el subproceso suspendido tiene una probabilidad mucho más alta de producir un interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="62546-116">This means the suspended thread has a much higher chance of causing a deadlock.</span></span> <span data-ttu-id="62546-117">Esto puede no afectar al depurar eventos ya está en cola.</span><span class="sxs-lookup"><span data-stu-id="62546-117">This may not affect debug events already queued.</span></span> <span data-ttu-id="62546-118">Por lo tanto, un depurador debe purgar la cola de eventos completa (mediante una llamada a [ICorDebugController:: HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) antes de suspender o reanudar subprocesos.</span><span class="sxs-lookup"><span data-stu-id="62546-118">Thus a debugger should drain the entire event queue (by calling [ICorDebugController::HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) before suspending or resuming threads.</span></span> <span data-ttu-id="62546-119">Else pueden obtener los eventos en un subproceso que cree que ya ha suspendido.</span><span class="sxs-lookup"><span data-stu-id="62546-119">Else it may get events on a thread that it believes it has already suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62546-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62546-120">Requirements</span></span>  
 <span data-ttu-id="62546-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62546-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62546-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62546-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62546-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62546-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62546-124">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62546-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>