---
title: CorPEKind (Enumeración)
ms.date: 03/30/2017
api_name:
- CorPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPEKind
helpviewer_keywords:
- CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b5869eb16bd768d58a6f27a83f2d8d51914a8aed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="corpekind-enumeration"></a>CorPEKind (Enumeración)
Contiene valores que describen un archivo ejecutable portable (PE), tal como lo devuelve una llamada a [IMetaDataImport2:: GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`peNot`|Indica que no es un archivo PE.|  
|`peILOnly`|Indica que este archivo PE contiene sólo código administrado.|  
|`pe32BitRequired`|Indica que este archivo PE efectúa llamadas a Win32.|  
|`pe32Plus`|Indica que este archivo PE se ejecuta en una plataforma de 64 bits.|  
|`pe32Unmanaged`|Indica que este archivo PE es código nativo.|  
|pe32BitPreferred|Indica que este archivo PE es independiente de la plataforma y prefiere que se va a cargar en un entorno de 32 bits.|  
  
## <a name="remarks"></a>Comentarios  
 Estos valores pueden utilizarse en combinaciones bit a bit.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr.h  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
