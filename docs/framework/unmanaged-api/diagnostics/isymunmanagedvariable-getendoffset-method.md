---
title: "ISymUnmanagedVariable::GetEndOffset (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetEndOffset
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedVariable::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: e5d777c5-d450-4c0f-999c-b3953ee22cfb
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b7a2dac8425cd852c6c17ee1674710f6798d3b1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedvariablegetendoffset-method"></a><span data-ttu-id="ff621-102">ISymUnmanagedVariable::GetEndOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="ff621-102">ISymUnmanagedVariable::GetEndOffset Method</span></span>
<span data-ttu-id="ff621-103">Obtiene el desplazamiento final de esta variable dentro de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="ff621-103">Gets the end offset of this variable within its parent.</span></span> <span data-ttu-id="ff621-104">Si se trata de una variable local dentro de un ámbito, el desplazamiento final se encontrará dentro de los desplazamientos definidos para el ámbito.</span><span class="sxs-lookup"><span data-stu-id="ff621-104">If this is a local variable within a scope, the end offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff621-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff621-105">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff621-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ff621-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="ff621-107">[out] Un puntero a un `ULONG32` que recibe el desplazamiento final.</span><span class="sxs-lookup"><span data-stu-id="ff621-107">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff621-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ff621-108">Return Value</span></span>  
 <span data-ttu-id="ff621-109">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="ff621-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff621-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ff621-110">Requirements</span></span>  
 <span data-ttu-id="ff621-111">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ff621-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff621-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff621-112">See Also</span></span>  
 [<span data-ttu-id="ff621-113">ISymUnmanagedVariable (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ff621-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="ff621-114">GetStartOffset (método)</span><span class="sxs-lookup"><span data-stu-id="ff621-114">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)