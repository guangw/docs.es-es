---
title: "Interfaces para depuración"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
caps.latest.revision: "32"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: de2469d15eef40b9ef283d67aeca429d9d96a7ef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="debugging-interfaces"></a><span data-ttu-id="6c8da-102">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="6c8da-102">Debugging Interfaces</span></span>
<span data-ttu-id="6c8da-103">En esta sección se describen las interfaces no administradas que controlan la depuración de un programa que se ejecuta en Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="6c8da-103">This section describes the unmanaged interfaces that handle the debugging of a program that is executing in the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6c8da-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6c8da-104">In This Section</span></span>  
 [<span data-ttu-id="6c8da-105">ICLRDataEnumMemoryRegions (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-105">ICLRDataEnumMemoryRegions Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)  
 <span data-ttu-id="6c8da-106">Proporciona un método para enumerar las regiones de memoria especificadas por los llamadores.</span><span class="sxs-lookup"><span data-stu-id="6c8da-106">Provides a method to enumerate regions of memory that are specified by callers.</span></span>  
  
 [<span data-ttu-id="6c8da-107">ICLRDataEnumMemoryRegionsCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-107">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)  
 <span data-ttu-id="6c8da-108">Proporciona un método de devolución de llamada para que `EnumMemoryRegions` notifique al depurador el resultado de un intento de enumerar un área de memoria concreta.</span><span class="sxs-lookup"><span data-stu-id="6c8da-108">Provides a callback method for `EnumMemoryRegions` to report to the debugger, the result of an attempt to enumerate a specified region of memory.</span></span>  
  
 [<span data-ttu-id="6c8da-109">ICLRDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-109">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)  
 <span data-ttu-id="6c8da-110">Proporciona métodos para la interacción con un proceso de CLR de destino.</span><span class="sxs-lookup"><span data-stu-id="6c8da-110">Provides methods for interaction with a target CLR process.</span></span>  
  
 [<span data-ttu-id="6c8da-111">ICLRDataTarget2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-111">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 <span data-ttu-id="6c8da-112">Subclase de `ICLRDataTarget` que se utiliza la capa de servicios de acceso a datos para manipular las áreas de la memoria virtual en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="6c8da-112">A subclass of `ICLRDataTarget` that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
 [<span data-ttu-id="6c8da-113">ICLRDataTarget3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-113">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 <span data-ttu-id="6c8da-114">Una subclase de [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) que proporciona acceso a información de excepción.</span><span class="sxs-lookup"><span data-stu-id="6c8da-114">A subclass of [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
 [<span data-ttu-id="6c8da-115">ICLRDebugging (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-115">ICLRDebugging Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md)  
 <span data-ttu-id="6c8da-116">Proporciona métodos que controlan la carga y descarga de módulos para depuración.</span><span class="sxs-lookup"><span data-stu-id="6c8da-116">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
 [<span data-ttu-id="6c8da-117">ICLRDebuggingLibraryProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-117">ICLRDebuggingLibraryProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md)  
 <span data-ttu-id="6c8da-118">Incluye el [ProvideLibrary (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) método, que obtiene un proveedor de bibliotecas de interfaz de devolución de llamada que permite a common language bibliotecas de depuración específicas de la versión en tiempo de ejecución buscar y cargar a petición.</span><span class="sxs-lookup"><span data-stu-id="6c8da-118">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
 [<span data-ttu-id="6c8da-119">ICLRMetadataLocator (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-119">ICLRMetadataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)  
 <span data-ttu-id="6c8da-120">Interfaz utilizada por la capa de servicios de acceso a datos para buscar los metadatos de los ensamblados en un proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="6c8da-120">Interface used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
 [<span data-ttu-id="6c8da-121">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-121">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 <span data-ttu-id="6c8da-122">Proporciona métodos que permiten a los desarrolladores depurar las aplicaciones en el entorno de CLR.</span><span class="sxs-lookup"><span data-stu-id="6c8da-122">Provides methods that allow developers to debug applications in the CLR environment.</span></span>  
  
 [<span data-ttu-id="6c8da-123">ICorDebugAppDomain Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-123">ICorDebugAppDomain Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md)  
 <span data-ttu-id="6c8da-124">Proporciona métodos para depurar dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6c8da-124">Provides methods for debugging application domains.</span></span>  
  
 [<span data-ttu-id="6c8da-125">ICorDebugAppDomain2 Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-125">ICorDebugAppDomain2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-interface.md)  
 <span data-ttu-id="6c8da-126">Proporciona métodos para trabajar con matrices, punteros, punteros a función y tipos ByRef.</span><span class="sxs-lookup"><span data-stu-id="6c8da-126">Provides methods to work with arrays, pointers, function pointers, and ByRef types.</span></span> <span data-ttu-id="6c8da-127">Esta interfaz es una extensión de la interfaz `ICorDebugAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="6c8da-127">This interface is an extension of the `ICorDebugAppDomain` interface.</span></span>  
  
 [<span data-ttu-id="6c8da-128">ICorDebugAppDomain3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-128">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)  
 <span data-ttu-id="6c8da-129">Proporciona métodos para trabajar con tipos [!INCLUDE[wrt](../../../../includes/wrt-md.md)] en un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6c8da-129">Provides methods to work with the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain.</span></span> <span data-ttu-id="6c8da-130">Esta interfaz es una extensión de las interfaces `ICorDebugAppDomain` e `ICorDebugAppDomain2`.</span><span class="sxs-lookup"><span data-stu-id="6c8da-130">This interface is an extension of the `ICorDebugAppDomain` and `ICorDebugAppDomain2` interfaces.</span></span>  
  
 [<span data-ttu-id="6c8da-131">ICorDebugAppDomain4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-131">ICorDebugAppDomain4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 <span data-ttu-id="6c8da-132">Extiende lógicamente la [ICorDebugAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md) interfaz para obtener un objeto administrado desde un contenedor CCW.</span><span class="sxs-lookup"><span data-stu-id="6c8da-132">Logically extends the [ICorDebugAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md) interface to get a managed object from a COM callable wrapper.</span></span>  
  
 [<span data-ttu-id="6c8da-133">ICorDebugAppDomainEnum Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-133">ICorDebugAppDomainEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md)  
 <span data-ttu-id="6c8da-134">Proporciona un método que devuelve un número especificado de valores de `ICorDebugAppDomain` que comienzan en la siguiente posición de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="6c8da-134">Provides a method that returns a specified number of `ICorDebugAppDomain` values starting at the next location in the enumeration.</span></span>  
  
 [<span data-ttu-id="6c8da-135">ICorDebugArrayValue Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-135">ICorDebugArrayValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-interface.md)  
 <span data-ttu-id="6c8da-136">Subclase de `ICorDebugHeapValue` que representa una matriz unidimensional o multidimensional.</span><span class="sxs-lookup"><span data-stu-id="6c8da-136">A subclass of `ICorDebugHeapValue` that represents a single-dimensional or multi-dimensional array.</span></span>  
  
 [<span data-ttu-id="6c8da-137">ICorDebugAssembly Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-137">ICorDebugAssembly Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md)  
 <span data-ttu-id="6c8da-138">Representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6c8da-138">Represents an assembly.</span></span>  
  
 [<span data-ttu-id="6c8da-139">ICorDebugAssembly2 Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-139">ICorDebugAssembly2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly2-interface.md)  
 <span data-ttu-id="6c8da-140">Representa un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6c8da-140">Represents an assembly.</span></span> <span data-ttu-id="6c8da-141">Esta interfaz es una extensión de la interfaz `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="6c8da-141">This interface is an extension of the `ICorDebugAssembly` interface.</span></span>  
  
 [<span data-ttu-id="6c8da-142">Interfaz ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="6c8da-142">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 <span data-ttu-id="6c8da-143">Extiende lógicamente la [ICorDebugAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md) interfaz para proporcionar compatibilidad con los ensamblados de contenedor y sus contenidos.</span><span class="sxs-lookup"><span data-stu-id="6c8da-143">Logically extends the [ICorDebugAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md) interface to provide support for container assemblies and their contained assemblies.</span></span> <span data-ttu-id="6c8da-144">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="6c8da-144">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="6c8da-145">ICorDebugAssemblyEnum Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-145">ICorDebugAssemblyEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-interface.md)  
 <span data-ttu-id="6c8da-146">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugAssembly`.</span><span class="sxs-lookup"><span data-stu-id="6c8da-146">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugAssembly` arrays.</span></span>  
  
 [<span data-ttu-id="6c8da-147">ICorDebugBlockingObjectEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-147">ICorDebugBlockingObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
 <span data-ttu-id="6c8da-148">Proporciona un enumerador para una lista de [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) estructuras.</span><span class="sxs-lookup"><span data-stu-id="6c8da-148">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
 [<span data-ttu-id="6c8da-149">ICorDebugBoxValue Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-149">ICorDebugBoxValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-interface.md)  
 <span data-ttu-id="6c8da-150">Subclase de `ICorDebugHeapValue` que representa un objeto de clase de valor al que se ha aplicado la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="6c8da-150">A subclass of `ICorDebugHeapValue` that represents a boxed value class object.</span></span>  
  
 [<span data-ttu-id="6c8da-151">ICorDebugBreakpoint Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-151">ICorDebugBreakpoint Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-interface.md)  
 <span data-ttu-id="6c8da-152">Representa un punto de interrupción en una función o un punto de inspección en un valor.</span><span class="sxs-lookup"><span data-stu-id="6c8da-152">Represents a breakpoint in a function or a watch point on a value.</span></span>  
  
 [<span data-ttu-id="6c8da-153">ICorDebugBreakpointEnum Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-153">ICorDebugBreakpointEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-interface.md)  
 <span data-ttu-id="6c8da-154">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="6c8da-154">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugBreakpoint` arrays.</span></span>  
  
 [<span data-ttu-id="6c8da-155">ICorDebugChain Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-155">ICorDebugChain Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md)  
 <span data-ttu-id="6c8da-156">Representa un segmento de una pila de llamadas física o lógica.</span><span class="sxs-lookup"><span data-stu-id="6c8da-156">Represents a segment of a physical or logical call stack.</span></span>  
  
 [<span data-ttu-id="6c8da-157">ICorDebugChainEnum Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-157">ICorDebugChainEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-interface.md)  
 <span data-ttu-id="6c8da-158">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugChain`.</span><span class="sxs-lookup"><span data-stu-id="6c8da-158">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugChain` arrays.</span></span>  
  
 [<span data-ttu-id="6c8da-159">ICorDebugClass Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-159">ICorDebugClass Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)  
 <span data-ttu-id="6c8da-160">Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="6c8da-160">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="6c8da-161">Si el tipo es genérico, `ICorDebugClass` representa el tipo genérico sin instancias.</span><span class="sxs-lookup"><span data-stu-id="6c8da-161">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
 [<span data-ttu-id="6c8da-162">ICorDebugClass2 Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-162">ICorDebugClass2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-interface.md)  
 <span data-ttu-id="6c8da-163">Representa una clase genérica o una clase con un parámetro de método de tipo <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="6c8da-163">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="6c8da-164">Esta interfaz extiende `ICorDebugClass`.</span><span class="sxs-lookup"><span data-stu-id="6c8da-164">This interface extends `ICorDebugClass`.</span></span>  
  
 [<span data-ttu-id="6c8da-165">ICorDebugCode Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-165">ICorDebugCode Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)  
 <span data-ttu-id="6c8da-166">Representa un segmento de código de lenguaje intermedio de Microsoft (MSIL) o código nativo.</span><span class="sxs-lookup"><span data-stu-id="6c8da-166">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
 [<span data-ttu-id="6c8da-167">ICorDebugCode2 Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-167">ICorDebugCode2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md)  
 <span data-ttu-id="6c8da-168">Proporciona métodos que amplían las funciones de `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="6c8da-168">Provides methods that extend the capabilities of `ICorDebugCode`.</span></span>  
  
 [<span data-ttu-id="6c8da-169">ICorDebugCode3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-169">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 <span data-ttu-id="6c8da-170">Proporciona un método que extiende [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md) y [ICorDebugCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md) para proporcionar información sobre un valor devuelto administrado.</span><span class="sxs-lookup"><span data-stu-id="6c8da-170">Provides a method that extends [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md) and [ICorDebugCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md) to provide information about a managed return value.</span></span>  
  
 [<span data-ttu-id="6c8da-171">Interfaz ICorDebugCode4</span><span class="sxs-lookup"><span data-stu-id="6c8da-171">ICorDebugCode4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)  
 <span data-ttu-id="6c8da-172">Proporciona un método que permite a un depurador enumerar las variables locales y argumentos en una función.</span><span class="sxs-lookup"><span data-stu-id="6c8da-172">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
 [<span data-ttu-id="6c8da-173">ICorDebugCodeEnum Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-173">ICorDebugCodeEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-interface.md)  
 <span data-ttu-id="6c8da-174">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="6c8da-174">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugCode` arrays.</span></span>  
  
 [<span data-ttu-id="6c8da-175">ICorDebugComObjectValue (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-175">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 <span data-ttu-id="6c8da-176">Proporciona métodos para recuperar objetos de la interfaz en caché.</span><span class="sxs-lookup"><span data-stu-id="6c8da-176">Provides methods to retrieve cached interface objects.</span></span>  
  
 [<span data-ttu-id="6c8da-177">ICorDebugContext Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-177">ICorDebugContext Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontext-interface.md)  
 <span data-ttu-id="6c8da-178">Representa un objeto de contexto.</span><span class="sxs-lookup"><span data-stu-id="6c8da-178">Represents a context object.</span></span> <span data-ttu-id="6c8da-179">Esta interfaz no se ha implementado todavía.</span><span class="sxs-lookup"><span data-stu-id="6c8da-179">This interface has not been implemented yet.</span></span>  
  
 [<span data-ttu-id="6c8da-180">ICorDebugController Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-180">ICorDebugController Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-interface.md)  
 <span data-ttu-id="6c8da-181">Representa un ámbito, <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, en el que se puede controlar el contexto de ejecución de código.</span><span class="sxs-lookup"><span data-stu-id="6c8da-181">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
 [<span data-ttu-id="6c8da-182">ICorDebugDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-182">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 <span data-ttu-id="6c8da-183">Proporciona una interfaz de devolución de llamada que brinda acceso a un proceso de destino determinado.</span><span class="sxs-lookup"><span data-stu-id="6c8da-183">Provides a callback interface that provides access to a particular target process.</span></span>  
  
 [<span data-ttu-id="6c8da-184">Interfaz ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="6c8da-184">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 <span data-ttu-id="6c8da-185">Extiende lógicamente la [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="6c8da-185">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="6c8da-186">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="6c8da-186">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="6c8da-187">ICorDebugDataTarget3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-187">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)  
 <span data-ttu-id="6c8da-188">Extiende lógicamente la [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaz para proporcionar información sobre los módulos cargados.</span><span class="sxs-lookup"><span data-stu-id="6c8da-188">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span> <span data-ttu-id="6c8da-189">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="6c8da-189">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="6c8da-190">Interfaz ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="6c8da-190">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 <span data-ttu-id="6c8da-191">Define la interfaz base de la que derivan todos los eventos de depuración `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="6c8da-191">Defines the base interface from which all `ICorDebug` debug events derive.</span></span> <span data-ttu-id="6c8da-192">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="6c8da-192">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="6c8da-193">ICorDebugEditAndContinueErrorInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-193">ICorDebugEditAndContinueErrorInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinueerrorinfo-interface.md)  
 <span data-ttu-id="6c8da-194">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="6c8da-194">Obsolete.</span></span> <span data-ttu-id="6c8da-195">No utilice esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="6c8da-195">Do not use this interface.</span></span>  
  
 [<span data-ttu-id="6c8da-196">ICorDebugEditAndContinueSnapshot Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-196">ICorDebugEditAndContinueSnapshot Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinuesnapshot-interface.md)  
 <span data-ttu-id="6c8da-197">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="6c8da-197">Obsolete.</span></span> <span data-ttu-id="6c8da-198">No utilice esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="6c8da-198">Do not use this interface.</span></span>  
  
 [<span data-ttu-id="6c8da-199">ICorDebugEnum Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-199">ICorDebugEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)  
 <span data-ttu-id="6c8da-200">Actúa como la interfaz base abstracta para la depuración de enumeradores.</span><span class="sxs-lookup"><span data-stu-id="6c8da-200">Serves as the abstract base interface for debugging enumerators.</span></span>  
  
 [<span data-ttu-id="6c8da-201">ICorDebugErrorInfoEnum Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-201">ICorDebugErrorInfoEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugerrorinfoenum-interface.md)  
 <span data-ttu-id="6c8da-202">Obsoleto.</span><span class="sxs-lookup"><span data-stu-id="6c8da-202">Obsolete.</span></span> <span data-ttu-id="6c8da-203">No utilice esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="6c8da-203">Do not use this interface.</span></span>  
  
 [<span data-ttu-id="6c8da-204">ICorDebugEval Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-204">ICorDebugEval Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-interface.md)  
 <span data-ttu-id="6c8da-205">Proporciona métodos que permiten al depurador ejecutar código en el contexto del código que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="6c8da-205">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
 [<span data-ttu-id="6c8da-206">ICorDebugEval2 Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-206">ICorDebugEval2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-interface.md)  
 <span data-ttu-id="6c8da-207">Extiende `ICorDebugEval` para proporcionar compatibilidad con los tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="6c8da-207">Extends `ICorDebugEval` to provide support for generic types.</span></span>  
  
 [<span data-ttu-id="6c8da-208">Interfaz ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="6c8da-208">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 <span data-ttu-id="6c8da-209">Extiende la [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interfaz para admitir eventos de excepción.</span><span class="sxs-lookup"><span data-stu-id="6c8da-209">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support exception events.</span></span> <span data-ttu-id="6c8da-210">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="6c8da-210">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="6c8da-211">ICorDebugExceptionObjectCallStackEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-211">ICorDebugExceptionObjectCallStackEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
 <span data-ttu-id="6c8da-212">Proporciona un enumerador para la información de la pila de llamadas que está incrustada en un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="6c8da-212">Provides an enumerator for call stack information that is embedded in an exception object.</span></span>  
  
 [<span data-ttu-id="6c8da-213">ICorDebugExceptionObjectValue (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-213">ICorDebugExceptionObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)  
 <span data-ttu-id="6c8da-214">Extiende la [ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md) interfaz para proporcionar información de seguimiento de pila de un objeto de excepción administrada.</span><span class="sxs-lookup"><span data-stu-id="6c8da-214">Extends the [ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md) interface to provide stack trace information from a managed exception object.</span></span>  
  
 [<span data-ttu-id="6c8da-215">ICorDebugFrame Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-215">ICorDebugFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md)  
 <span data-ttu-id="6c8da-216">Representa un marco en la pila actual.</span><span class="sxs-lookup"><span data-stu-id="6c8da-216">Represents a frame on the current stack.</span></span>  
  
 [<span data-ttu-id="6c8da-217">ICorDebugFrameEnum Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-217">ICorDebugFrameEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-interface.md)  
 <span data-ttu-id="6c8da-218">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="6c8da-218">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugFrame` arrays.</span></span>  
  
 [<span data-ttu-id="6c8da-219">ICorDebugFunction Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-219">ICorDebugFunction Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md)  
 <span data-ttu-id="6c8da-220">Representa una función o un método administrado.</span><span class="sxs-lookup"><span data-stu-id="6c8da-220">Represents a managed function or method.</span></span>  
  
 [<span data-ttu-id="6c8da-221">ICorDebugFunction2 Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-221">ICorDebugFunction2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-interface.md)  
 <span data-ttu-id="6c8da-222">Extiende `ICorDebugFunction` de manera lógica para ofrecer compatibilidad con la depuración paso a paso de "Sólo mi código".</span><span class="sxs-lookup"><span data-stu-id="6c8da-222">Logically extends `ICorDebugFunction` to provide support for Just My Code step-through debugging.</span></span>  
  
 [<span data-ttu-id="6c8da-223">ICorDebugFunction3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-223">ICorDebugFunction3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-interface.md)  
 <span data-ttu-id="6c8da-224">Extiende lógicamente la [ICorDebugFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md) interfaz para proporcionar acceso al código desde una solicitud ReJIT.</span><span class="sxs-lookup"><span data-stu-id="6c8da-224">Logically extends the [ICorDebugFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md) interface to provide access to code from a ReJIT request.</span></span>  
  
 [<span data-ttu-id="6c8da-225">ICorDebugFunctionBreakpoint Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-225">ICorDebugFunctionBreakpoint Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-interface.md)  
 <span data-ttu-id="6c8da-226">Amplía `ICorDebugBreakpoint` para admitir los puntos de interrupción dentro de las funciones.</span><span class="sxs-lookup"><span data-stu-id="6c8da-226">Extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
 [<span data-ttu-id="6c8da-227">ICorDebugGCReferenceEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-227">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
 <span data-ttu-id="6c8da-228">Proporciona un enumerador para los objetos que se recolectarán como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="6c8da-228">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
 [<span data-ttu-id="6c8da-229">ICorDebugGenericValue Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-229">ICorDebugGenericValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-interface.md)  
 <span data-ttu-id="6c8da-230">Subclase de `ICorDebugValue` que se aplica a todos los valores.</span><span class="sxs-lookup"><span data-stu-id="6c8da-230">A subclass of `ICorDebugValue` that applies to all values.</span></span> <span data-ttu-id="6c8da-231">Esta interfaz proporciona métodos Get y Set para el valor.</span><span class="sxs-lookup"><span data-stu-id="6c8da-231">This interface provides Get and Set methods for the value.</span></span>  
  
 [<span data-ttu-id="6c8da-232">ICorDebugGuidToTypeEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-232">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
 <span data-ttu-id="6c8da-233">Proporciona un enumerador para un objeto que asigna GUID y sus objetos `ICorDebugType` correspondientes.</span><span class="sxs-lookup"><span data-stu-id="6c8da-233">Provides an enumerator for an object that maps GUIDs and their corresponding `ICorDebugType` objects.</span></span>  
  
 [<span data-ttu-id="6c8da-234">ICorDebugHandleValue Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-234">ICorDebugHandleValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-interface.md)  
 <span data-ttu-id="6c8da-235">Subclase de `ICorDebugReferenceValue` que representa un valor de referencia para el cual el depurador ha creado un identificador para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="6c8da-235">A subclass of `ICorDebugReferenceValue` that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
 [<span data-ttu-id="6c8da-236">ICorDebugHeapEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-236">ICorDebugHeapEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
 <span data-ttu-id="6c8da-237">Proporciona un enumerador para los objetos del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="6c8da-237">Provides an enumerator for objects on the managed heap.</span></span>  
  
 [<span data-ttu-id="6c8da-238">ICorDebugHeapSegmentEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-238">ICorDebugHeapSegmentEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
 <span data-ttu-id="6c8da-239">Proporciona un enumerador para las regiones de memoria del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="6c8da-239">Provides an enumerator for the memory regions of the managed heap.</span></span>  
  
 [<span data-ttu-id="6c8da-240">ICorDebugHeapValue Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-240">ICorDebugHeapValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-interface.md)  
 <span data-ttu-id="6c8da-241">Subclase de `ICorDebugValue` que representa un objeto que ha sido recopilado por el recolector de elementos no utilizados de CLR.</span><span class="sxs-lookup"><span data-stu-id="6c8da-241">A subclass of `ICorDebugValue` that represents an object that has been collected by the CLR garbage collector.</span></span>  
  
 [<span data-ttu-id="6c8da-242">ICorDebugHeapValue2 Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-242">ICorDebugHeapValue2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue2-interface1.md)  
 <span data-ttu-id="6c8da-243">Extensión de `ICorDebugHeapValue` que proporciona compatibilidad con los identificadores del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6c8da-243">An extension of `ICorDebugHeapValue` that provides support for runtime handles.</span></span>  
  
 [<span data-ttu-id="6c8da-244">ICorDebugHeapValue3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-244">ICorDebugHeapValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md)  
 <span data-ttu-id="6c8da-245">Expone las propiedades de bloqueo de monitor de objetos.</span><span class="sxs-lookup"><span data-stu-id="6c8da-245">Exposes the monitor lock properties of objects.</span></span>  
  
 [<span data-ttu-id="6c8da-246">ICorDebugILCode (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-246">ICorDebugILCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)  
 <span data-ttu-id="6c8da-247">Representa un segmento de código de lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="6c8da-247">Represents a segment of intermediate language (IL) code.</span></span>  
  
 [<span data-ttu-id="6c8da-248">ICorDebugILCode2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-248">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 <span data-ttu-id="6c8da-249">Extiende lógicamente la [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interfaz para proporcionar métodos que devuelven el token de firma de variable local de una función e instrumentada un lenguaje intermedio del generador de perfiles (IL) que asignan los desplazamientos al IL del método original desplazamientos.</span><span class="sxs-lookup"><span data-stu-id="6c8da-249">Logically extends the [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
 [<span data-ttu-id="6c8da-250">ICorDebugILFrame Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-250">ICorDebugILFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-interface.md)  
 <span data-ttu-id="6c8da-251">Representa un marco de pila de código de MSIL.</span><span class="sxs-lookup"><span data-stu-id="6c8da-251">Represents a stack frame of MSIL code.</span></span>  
  
 [<span data-ttu-id="6c8da-252">ICorDebugILFrame2 Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-252">ICorDebugILFrame2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-interface.md)  
 <span data-ttu-id="6c8da-253">Extensión lógica de `ICorDebugILFrame`.</span><span class="sxs-lookup"><span data-stu-id="6c8da-253">A logical extension of `ICorDebugILFrame`.</span></span>  
  
 [<span data-ttu-id="6c8da-254">ICorDebugILFrame3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-254">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)  
 <span data-ttu-id="6c8da-255">Proporciona un método que encapsula el valor devuelto de una función.</span><span class="sxs-lookup"><span data-stu-id="6c8da-255">Provides a method that encapsulates the return value of a function.</span></span>  
  
 [<span data-ttu-id="6c8da-256">ICorDebugILFrame4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-256">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 <span data-ttu-id="6c8da-257">Proporciona métodos que permiten acceder a las variables locales y al código en un marco de pila de código de lenguaje intermedio (IL).</span><span class="sxs-lookup"><span data-stu-id="6c8da-257">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="6c8da-258">Un parámetro especifica si el depurador tiene acceso a las variables y al código agregados en la instrumentación ReJIT del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="6c8da-258">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
 [<span data-ttu-id="6c8da-259">Interfaz ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="6c8da-259">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 <span data-ttu-id="6c8da-260">Representa la información de símbolos de depuración para un campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="6c8da-260">Represents the debug symbol information for an instance field.</span></span> <span data-ttu-id="6c8da-261">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="6c8da-261">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="6c8da-262">ICorDebugInternalFrame Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-262">ICorDebugInternalFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-interface.md)  
 <span data-ttu-id="6c8da-263">Identifica los tipos de marco del depurador.</span><span class="sxs-lookup"><span data-stu-id="6c8da-263">Identifies frame types for the debugger.</span></span>  
  
 [<span data-ttu-id="6c8da-264">ICorDebugInternalFrame2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-264">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 <span data-ttu-id="6c8da-265">Proporciona información sobre los marcos internos, incluyendo la dirección de pila y la posición con respecto a [ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md) objetos.</span><span class="sxs-lookup"><span data-stu-id="6c8da-265">Provides information about internal frames, including stack address and position in relation to [ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md) objects.</span></span>  
  
 [<span data-ttu-id="6c8da-266">ICorDebugLoadedModule (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-266">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 <span data-ttu-id="6c8da-267">Proporciona información acerca de un módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="6c8da-267">Provides information about a loaded module.</span></span> <span data-ttu-id="6c8da-268">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="6c8da-268">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="6c8da-269">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-269">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)  
 <span data-ttu-id="6c8da-270">Proporciona métodos que permiten procesar las devoluciones de llamada del depurador.</span><span class="sxs-lookup"><span data-stu-id="6c8da-270">Provides methods to process debugger callbacks.</span></span>  
  
 [<span data-ttu-id="6c8da-271">ICorDebugManagedCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-271">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 <span data-ttu-id="6c8da-272">Proporciona métodos para admitir el control de excepciones del depurador y asistentes para depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="6c8da-272">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="6c8da-273">`ICorDebugManagedCallback2` es una extensión lógica de `ICorDebugManagedCallback`.</span><span class="sxs-lookup"><span data-stu-id="6c8da-273">`ICorDebugManagedCallback2` is a logical extension of `ICorDebugManagedCallback`.</span></span>  
  
 [<span data-ttu-id="6c8da-274">ICorDebugManagedCallback3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-274">ICorDebugManagedCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)  
 <span data-ttu-id="6c8da-275">Proporciona un método de devolución de llamada que indica que se ha producido una notificación del depurador personalizada habilitada.</span><span class="sxs-lookup"><span data-stu-id="6c8da-275">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
 [<span data-ttu-id="6c8da-276">ICorDebugMDA (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-276">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 <span data-ttu-id="6c8da-277">Representa un mensaje del asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="6c8da-277">Represents a managed debugging assistant (MDA) message.</span></span>  
  
 [<span data-ttu-id="6c8da-278">ICorDebugMemoryBuffer (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-278">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 <span data-ttu-id="6c8da-279">Representa un búfer en memoria.</span><span class="sxs-lookup"><span data-stu-id="6c8da-279">Represents an in-memory buffer.</span></span> <span data-ttu-id="6c8da-280">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="6c8da-280">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="6c8da-281">ICorDebugMergedAssemblyRecord (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-281">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 <span data-ttu-id="6c8da-282">Proporciona información acerca de un ensamblado combinado.</span><span class="sxs-lookup"><span data-stu-id="6c8da-282">Provides information about a merged assembly.</span></span> <span data-ttu-id="6c8da-283">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="6c8da-283">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="6c8da-284">ICorDebugMetaDataLocator (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-284">ICorDebugMetaDataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-interface.md)  
 <span data-ttu-id="6c8da-285">Proporciona información de metadatos al depurador.</span><span class="sxs-lookup"><span data-stu-id="6c8da-285">Provides metadata information to the debugger.</span></span>  
  
 [<span data-ttu-id="6c8da-286">ICorDebugModule Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-286">ICorDebugModule Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-interface.md)  
 <span data-ttu-id="6c8da-287">Representa un módulo de CLR, que es un archivo ejecutable o una biblioteca de vínculos dinámicos (DLL).</span><span class="sxs-lookup"><span data-stu-id="6c8da-287">Represents a CLR module, which is either an executable or a dynamic-link library (DLL).</span></span>  
  
 [<span data-ttu-id="6c8da-288">ICorDebugModule2 Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-288">ICorDebugModule2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-interface.md)  
 <span data-ttu-id="6c8da-289">Actúa como una extensión lógica de `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="6c8da-289">Serves as a logical extension to `ICorDebugModule`.</span></span>  
  
 [<span data-ttu-id="6c8da-290">ICorDebugModule3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-290">ICorDebugModule3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-interface.md)  
 <span data-ttu-id="6c8da-291">Crea un lector de símbolos para un módulo dinámico.</span><span class="sxs-lookup"><span data-stu-id="6c8da-291">Creates a symbol reader for a dynamic module.</span></span>  
  
 [<span data-ttu-id="6c8da-292">ICorDebugModuleBreakpoint Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-292">ICorDebugModuleBreakpoint Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-interface.md)  
 <span data-ttu-id="6c8da-293">Extiende `ICorDebugBreakpoint` para proporcionar acceso a módulos específicos.</span><span class="sxs-lookup"><span data-stu-id="6c8da-293">Extends `ICorDebugBreakpoint` to provide access to specific modules.</span></span>  
  
 [<span data-ttu-id="6c8da-294">ICorDebugModuleDebugEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-294">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
 <span data-ttu-id="6c8da-295">Extiende la [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interfaz para admitir eventos de nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="6c8da-295">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span> <span data-ttu-id="6c8da-296">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="6c8da-296">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="6c8da-297">ICorDebugModuleEnum Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-297">ICorDebugModuleEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-interface.md)  
 <span data-ttu-id="6c8da-298">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="6c8da-298">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugModule` arrays.</span></span>  
  
 [<span data-ttu-id="6c8da-299">ICorDebugMutableDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-299">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 <span data-ttu-id="6c8da-300">Extiende la [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaz para admitir destinos de datos mutables.</span><span class="sxs-lookup"><span data-stu-id="6c8da-300">Extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
 [<span data-ttu-id="6c8da-301">ICorDebugNativeFrame Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-301">ICorDebugNativeFrame Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-interface.md)  
 <span data-ttu-id="6c8da-302">Implementación especializada de `ICorDebugFrame` que se utiliza para los marcos nativos.</span><span class="sxs-lookup"><span data-stu-id="6c8da-302">A specialized implementation of `ICorDebugFrame` used for native frames.</span></span>  
  
 [<span data-ttu-id="6c8da-303">ICorDebugNativeFrame2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-303">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 <span data-ttu-id="6c8da-304">Proporciona métodos que comprueban las relaciones entre marcos primarios y secundarios.</span><span class="sxs-lookup"><span data-stu-id="6c8da-304">Provides methods that test for child and parent frame relationships.</span></span>  
  
 [<span data-ttu-id="6c8da-305">ICorDebugObjectEnum Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-305">ICorDebugObjectEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-interface.md)  
 <span data-ttu-id="6c8da-306">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de objetos según sus direcciones virtuales relativas (RVA).</span><span class="sxs-lookup"><span data-stu-id="6c8da-306">Implements `ICorDebugEnum` methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
 [<span data-ttu-id="6c8da-307">ICorDebugObjectValue Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-307">ICorDebugObjectValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md)  
 <span data-ttu-id="6c8da-308">Subclase de `ICorDebugValue` que representa un valor que contiene un objeto.</span><span class="sxs-lookup"><span data-stu-id="6c8da-308">A subclass of `ICorDebugValue` that represents a value that contains an object.</span></span>  
  
 [<span data-ttu-id="6c8da-309">ICorDebugObjectValue2 Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-309">ICorDebugObjectValue2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue2-interface.md)  
 <span data-ttu-id="6c8da-310">Extiende `ICorDebugObjectValue` para ofrecer compatibilidad con la herencia y los reemplazos.</span><span class="sxs-lookup"><span data-stu-id="6c8da-310">Extends `ICorDebugObjectValue` to support inheritance and overrides.</span></span>  
  
 [<span data-ttu-id="6c8da-311">ICorDebugProcess Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-311">ICorDebugProcess Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md)  
 <span data-ttu-id="6c8da-312">Representa un proceso que ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="6c8da-312">Represents a process that is executing managed code.</span></span>  
  
 [<span data-ttu-id="6c8da-313">ICorDebugProcess2 Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-313">ICorDebugProcess2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-interface1.md)  
 <span data-ttu-id="6c8da-314">Extensión lógica de `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="6c8da-314">A logical extension of `ICorDebugProcess`.</span></span>  
  
 [<span data-ttu-id="6c8da-315">ICorDebugProcess3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-315">ICorDebugProcess3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 <span data-ttu-id="6c8da-316">Controla las notificaciones del depurador personalizadas.</span><span class="sxs-lookup"><span data-stu-id="6c8da-316">Controls custom debugger notifications.</span></span>  
  
 [<span data-ttu-id="6c8da-317">ICorDebugProcess5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-317">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 <span data-ttu-id="6c8da-318">Extiende la [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) local de la interfaz para admitir el acceso al montón administrado, para proporcionar información sobre la recolección de los objetos administrados y para determinar si un depurador carga imágenes desde la aplicación caché de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="6c8da-318">Extends the [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application's local native image cache.</span></span>  
  
 [<span data-ttu-id="6c8da-319">Interfaz ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="6c8da-319">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 <span data-ttu-id="6c8da-320">Extiende lógicamente la [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interfaz para habilitar características como la descodificación de eventos de depuración administrados que están codificados en eventos de depuración de excepción nativos o la división de módulos virtuales.</span><span class="sxs-lookup"><span data-stu-id="6c8da-320">Logically extends the [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span> <span data-ttu-id="6c8da-321">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="6c8da-321">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="6c8da-322">ICorDebugProcess7 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-322">ICorDebugProcess7 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)  
 <span data-ttu-id="6c8da-323">Proporciona un método que configura el depurador para controlar las actualizaciones en memoria de los metadatos en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="6c8da-323">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
 [<span data-ttu-id="6c8da-324">ICorDebugProcess8 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-324">ICorDebugProcess8 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)  
 <span data-ttu-id="6c8da-325">Extiende lógicamente la [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interfaz para habilitar o deshabilitar ciertos tipos de [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) las devoluciones de llamada de excepción.</span><span class="sxs-lookup"><span data-stu-id="6c8da-325">Logically extends the [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interface to enable or disable certain types of [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
 [<span data-ttu-id="6c8da-326">ICorDebugProcessEnum Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-326">ICorDebugProcessEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-interface.md)  
 <span data-ttu-id="6c8da-327">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="6c8da-327">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugProcess` arrays.</span></span>  
  
 [<span data-ttu-id="6c8da-328">ICorDebugReferenceValue Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-328">ICorDebugReferenceValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-interface.md)  
 <span data-ttu-id="6c8da-329">Subclase de `ICorDebugValue` que admite tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="6c8da-329">A subclass of `ICorDebugValue` that supports reference types.</span></span>  
  
 [<span data-ttu-id="6c8da-330">ICorDebugRegisterSet (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-330">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 <span data-ttu-id="6c8da-331">Representa el conjunto de registros disponibles en el equipo que está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="6c8da-331">Represents the set of registers available on the machine that is currently executing code.</span></span>  
  
 [<span data-ttu-id="6c8da-332">ICorDebugRegisterSet2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-332">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 <span data-ttu-id="6c8da-333">Extiende la funcionalidad de `ICorDebugRegisterSet` para plataformas hardware que tienen más de 64 registros.</span><span class="sxs-lookup"><span data-stu-id="6c8da-333">Extends the capabilities of `ICorDebugRegisterSet` for hardware platforms that have more than 64 registers.</span></span>  
  
 [<span data-ttu-id="6c8da-334">ICorDebugRemote (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-334">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 <span data-ttu-id="6c8da-335">Proporciona la capacidad de iniciar o de adjuntar un depurador administrado a un proceso remoto de destino.</span><span class="sxs-lookup"><span data-stu-id="6c8da-335">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
 [<span data-ttu-id="6c8da-336">ICorDebugRemoteTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-336">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 <span data-ttu-id="6c8da-337">Proporciona métodos que permiten depurar aplicaciones basadas en Silverlight en el entorno de CLR.</span><span class="sxs-lookup"><span data-stu-id="6c8da-337">Provides methods that enable you to debug Silverlight-based applications in the CLR environment.</span></span>  
  
 [<span data-ttu-id="6c8da-338">ICorDebugRuntimeUnwindableFrame (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-338">ICorDebugRuntimeUnwindableFrame Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugruntimeunwindableframe-interface.md)  
 <span data-ttu-id="6c8da-339">Proporciona compatibilidad para métodos no administrados que necesitan que Common Language Runtime (CLR) desenrede un marco.</span><span class="sxs-lookup"><span data-stu-id="6c8da-339">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
 [<span data-ttu-id="6c8da-340">ICorDebugStackWalk (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-340">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)  
 <span data-ttu-id="6c8da-341">Proporciona métodos para obtener los métodos administrados, o marcos, de la pila de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="6c8da-341">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
 [<span data-ttu-id="6c8da-342">ICorDebugStaticFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-342">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 <span data-ttu-id="6c8da-343">Representa la información de símbolos de depuración para un campo estático.</span><span class="sxs-lookup"><span data-stu-id="6c8da-343">Represents the debug symbol information for a static field.</span></span> <span data-ttu-id="6c8da-344">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="6c8da-344">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="6c8da-345">ICorDebugStepper Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-345">ICorDebugStepper Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-interface.md)  
 <span data-ttu-id="6c8da-346">Representa un paso en la ejecución del código realizado por un depurador, actúa como identificador entre la emisión y la finalización de un comando, y proporciona un modo de cancelar un paso.</span><span class="sxs-lookup"><span data-stu-id="6c8da-346">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
 [<span data-ttu-id="6c8da-347">ICorDebugStepper2 Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-347">ICorDebugStepper2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper2-interface1.md)  
 <span data-ttu-id="6c8da-348">Proporciona compatibilidad con la depuración de "Sólo mi código" (JMC).</span><span class="sxs-lookup"><span data-stu-id="6c8da-348">Provides support for Just My Code (JMC) debugging.</span></span>  
  
 [<span data-ttu-id="6c8da-349">ICorDebugStepperEnum Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-349">ICorDebugStepperEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-interface.md)  
 <span data-ttu-id="6c8da-350">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugStepper`.</span><span class="sxs-lookup"><span data-stu-id="6c8da-350">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugStepper` arrays.</span></span>  
  
 [<span data-ttu-id="6c8da-351">ICorDebugStringValue Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-351">ICorDebugStringValue Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-interface.md)  
 <span data-ttu-id="6c8da-352">Subclase de `ICorDebugHeapValue` que se aplica a los valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="6c8da-352">A subclass of `ICorDebugHeapValue` that applies to string values.</span></span>  
  
 [<span data-ttu-id="6c8da-353">Interfaz ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="6c8da-353">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 <span data-ttu-id="6c8da-354">Proporciona métodos que pueden usarse para recuperar información de símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="6c8da-354">Provides methods that can be used to retrieve debug symbol information.</span></span> <span data-ttu-id="6c8da-355">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="6c8da-355">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="6c8da-356">ICorDebugSymbolProvider2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-356">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)  
 <span data-ttu-id="6c8da-357">Extiende lógicamente la [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interfaz para recuperar información de símbolos de depuración adicional.</span><span class="sxs-lookup"><span data-stu-id="6c8da-357">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span> <span data-ttu-id="6c8da-358">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="6c8da-358">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="6c8da-359">ICorDebugThread Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-359">ICorDebugThread Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-interface.md)  
 <span data-ttu-id="6c8da-360">Representa un subproceso de un proceso.</span><span class="sxs-lookup"><span data-stu-id="6c8da-360">Represents a thread in a process.</span></span> <span data-ttu-id="6c8da-361">El período de duración de una instancia de `ICorDebugThread` es el mismo que el del subproceso que representa.</span><span class="sxs-lookup"><span data-stu-id="6c8da-361">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
 [<span data-ttu-id="6c8da-362">ICorDebugThread2 Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-362">ICorDebugThread2 Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interface.md)  
 <span data-ttu-id="6c8da-363">Actúa como una extensión lógica de `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="6c8da-363">Serves as a logical extension to `ICorDebugThread`.</span></span>  
  
 [<span data-ttu-id="6c8da-364">ICorDebugThread3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-364">ICorDebugThread3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md)  
 <span data-ttu-id="6c8da-365">Proporciona el punto de entrada a la [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) y las interfaces correspondientes.</span><span class="sxs-lookup"><span data-stu-id="6c8da-365">Provides the entry point to the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
 [<span data-ttu-id="6c8da-366">ICorDebugThread4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-366">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 <span data-ttu-id="6c8da-367">Proporciona información de bloqueo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="6c8da-367">Provides thread blocking information.</span></span>  
  
 [<span data-ttu-id="6c8da-368">ICorDebugThreadEnum Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-368">ICorDebugThreadEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-interface1.md)  
 <span data-ttu-id="6c8da-369">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="6c8da-369">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugThread` arrays.</span></span>  
  
 [<span data-ttu-id="6c8da-370">ICorDebugType Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-370">ICorDebugType Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md)  
 <span data-ttu-id="6c8da-371">Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="6c8da-371">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="6c8da-372">Si el tipo es genérico, `ICorDebugType` representa el tipo genérico con instancias.</span><span class="sxs-lookup"><span data-stu-id="6c8da-372">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
 [<span data-ttu-id="6c8da-373">Interfaz ICorDebugType2</span><span class="sxs-lookup"><span data-stu-id="6c8da-373">ICorDebugType2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)  
 <span data-ttu-id="6c8da-374">Extiende la [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) interfaz para recuperar el identificador de tipo de un tipo base o un tipo complejo (definido por el usuario).</span><span class="sxs-lookup"><span data-stu-id="6c8da-374">Extends the [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
 [<span data-ttu-id="6c8da-375">ICorDebugTypeEnum Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6c8da-375">ICorDebugTypeEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtypeenum-interface.md)  
 <span data-ttu-id="6c8da-376">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="6c8da-376">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugType` arrays.</span></span>  
  
 [<span data-ttu-id="6c8da-377">ICorDebugUnmanagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-377">ICorDebugUnmanagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)  
 <span data-ttu-id="6c8da-378">Proporciona notificación de eventos nativos no relacionados directamente con CLR.</span><span class="sxs-lookup"><span data-stu-id="6c8da-378">Provides notification of native events that are not directly related to the CLR.</span></span>  
  
 <span data-ttu-id="6c8da-379">"ICorDebugValue"</span><span class="sxs-lookup"><span data-stu-id="6c8da-379">"ICorDebugValue"</span></span>  
 <span data-ttu-id="6c8da-380">Representa un valor de escritura o lectura en el proceso que se va a depurar.</span><span class="sxs-lookup"><span data-stu-id="6c8da-380">Represents a read or write value in the process being debugged.</span></span>  
  
 <span data-ttu-id="6c8da-381">"ICorDebugValue2"</span><span class="sxs-lookup"><span data-stu-id="6c8da-381">"ICorDebugValue2"</span></span>  
 <span data-ttu-id="6c8da-382">Extiende `ICorDebugValue` para proporcionar compatibilidad con `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="6c8da-382">Extends `ICorDebugValue` to provide support for `ICorDebugType`.</span></span>  
  
 [<span data-ttu-id="6c8da-383">ICorDebugValue3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-383">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 <span data-ttu-id="6c8da-384">Extiende las interfaces "ICorDebugValue" y "ICorDebugValue2" para proporcionar compatibilidad con matrices mayores de 2 GB.</span><span class="sxs-lookup"><span data-stu-id="6c8da-384">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
 <span data-ttu-id="6c8da-385">"ICorDebugValueBreakpoint"</span><span class="sxs-lookup"><span data-stu-id="6c8da-385">"ICorDebugValueBreakpoint"</span></span>  
 <span data-ttu-id="6c8da-386">Extiende `ICorDebugBreakpoint` para proporcionar acceso a valores concretos.</span><span class="sxs-lookup"><span data-stu-id="6c8da-386">Extends `ICorDebugBreakpoint` to provide access to specific values.</span></span>  
  
 <span data-ttu-id="6c8da-387">"ICorDebugValueEnum"</span><span class="sxs-lookup"><span data-stu-id="6c8da-387">"ICorDebugValueEnum"</span></span>  
 <span data-ttu-id="6c8da-388">Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="6c8da-388">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugValue` arrays.</span></span>  
  
 [<span data-ttu-id="6c8da-389">Interfaz ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="6c8da-389">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 <span data-ttu-id="6c8da-390">Representa una variable local o un argumento de una función.</span><span class="sxs-lookup"><span data-stu-id="6c8da-390">Represents a local variable or argument of a function.</span></span>  
  
 [<span data-ttu-id="6c8da-391">Interfaz ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="6c8da-391">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
 <span data-ttu-id="6c8da-392">Proporciona un enumerador para las variables locales y argumentos en una función.</span><span class="sxs-lookup"><span data-stu-id="6c8da-392">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
 [<span data-ttu-id="6c8da-393">ICorDebugVariableSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-393">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 <span data-ttu-id="6c8da-394">Recupera la información de símbolos de depuración para una variable.</span><span class="sxs-lookup"><span data-stu-id="6c8da-394">Retrieves the debug symbol information for a variable.</span></span> <span data-ttu-id="6c8da-395">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="6c8da-395">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="6c8da-396">ICorDebugVirtualUnwinder (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-396">ICorDebugVirtualUnwinder Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-interface.md)  
 <span data-ttu-id="6c8da-397">Proporciona métodos que ayudan al desenredo de la pila.</span><span class="sxs-lookup"><span data-stu-id="6c8da-397">Provides methods to help in stack unwinding.</span></span> <span data-ttu-id="6c8da-398">**Disponible solo en .NET Native.**</span><span class="sxs-lookup"><span data-stu-id="6c8da-398">**Available on .NET Native only.**</span></span>  
  
 [<span data-ttu-id="6c8da-399">ICorPublish (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-399">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)  
 <span data-ttu-id="6c8da-400">Actúa como interfaz general para los procesos de publicación.</span><span class="sxs-lookup"><span data-stu-id="6c8da-400">Serves as the general interface for the publishing processes.</span></span>  
  
 [<span data-ttu-id="6c8da-401">ICorPublishAppDomain (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-401">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)  
 <span data-ttu-id="6c8da-402">Representa y proporciona información sobre un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="6c8da-402">Represents and provides information about an application domain.</span></span>  
  
 [<span data-ttu-id="6c8da-403">ICorPublishAppDomainEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-403">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
 <span data-ttu-id="6c8da-404">Proporciona métodos que atraviesan una colección de objetos `ICorPublishAppDomain` que actualmente existen dentro de un proceso.</span><span class="sxs-lookup"><span data-stu-id="6c8da-404">Provides methods that traverse a collection of `ICorPublishAppDomain` objects that currently exist within a process.</span></span>  
  
 [<span data-ttu-id="6c8da-405">ICorPublishEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-405">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)  
 <span data-ttu-id="6c8da-406">Actúa como la base abstracta para los enumeradores de publicación.</span><span class="sxs-lookup"><span data-stu-id="6c8da-406">Serves as the abstract base for publishing enumerators.</span></span>  
  
 [<span data-ttu-id="6c8da-407">ICorPublishProcess (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-407">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)  
 <span data-ttu-id="6c8da-408">Proporciona métodos que tienen acceso a información de un proceso.</span><span class="sxs-lookup"><span data-stu-id="6c8da-408">Provides methods that access information about a process.</span></span>  
  
 [<span data-ttu-id="6c8da-409">ICorPublishProcessEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c8da-409">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
 <span data-ttu-id="6c8da-410">Proporciona métodos que atraviesan una colección de objetos `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="6c8da-410">Provides methods that traverse a collection of `ICorPublishProcess` objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6c8da-411">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="6c8da-411">Related Sections</span></span>  
 [<span data-ttu-id="6c8da-412">Coclases para la depuración</span><span class="sxs-lookup"><span data-stu-id="6c8da-412">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [<span data-ttu-id="6c8da-413">Funciones estáticas globales para la depuración</span><span class="sxs-lookup"><span data-stu-id="6c8da-413">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [<span data-ttu-id="6c8da-414">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="6c8da-414">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [<span data-ttu-id="6c8da-415">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="6c8da-415">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)