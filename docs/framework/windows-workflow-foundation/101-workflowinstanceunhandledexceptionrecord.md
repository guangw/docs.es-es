---
title: 101 - WorkflowInstanceUnhandledExceptionRecord
ms.date: 03/30/2017
ms.assetid: ab7d50a0-5347-4390-8445-1def4dfdff6a
ms.openlocfilehash: af7f471e135ed7ec782f7d9a5c7cee3de09e7187
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="101---workflowinstanceunhandledexceptionrecord"></a>101 - WorkflowInstanceUnhandledExceptionRecord
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|101|  
|Palabras clave|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|Nivel|Error|  
|Canal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descripción  
 El participante de seguimiento de ETW emite este evento cuando una instancia de flujo de trabajo emite WorkflowInstanceUnhandledExceptionRecord.  
  
## <a name="message"></a>Mensaje  
 TrackRecord = WorkflowInstanceUnhandledExceptionRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, SourceName = %5, SourceId = %6, SourceInstanceId = %7, SourceTypeName=%8, Exception=%9, Annotations= %10, ProfileName = %11  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|El id. de instancia del flujo de trabajo.|  
|RecordNumber|xs:long|El número de secuencia del registro emitido.|  
|EventTime|xs:dateTime|La hora en UTC cuando se emitió el evento.|  
|ActivityDefinitionId|xs:string|El nombre de la actividad raíz del flujo de trabajo.|  
|SourceName|xs:string|El nombre de la actividad de origen con errores que dio como resultado unhandledException.|  
|SourceId|xs:string|El id. de la actividad de origen con errores.|  
|SourceInstanceId|xs:string|El id. de instancia de la actividad de origen con errores.|  
|SourceTypeName|xs:string|El nombre del tipo de actividad de origen con errores que dio como resultado unhandledException.|  
|Excepción|xs:string|La excepción de información sobre la excepción no controlada.|  
|Anotaciones|xs:string|Las anotaciones que se agregaron a este evento.  Los valores se almacenan en un elemento xml con el formato \<elementos >\< nombre de elemento = "annotationName" Type = "> annotationValue\</artículo > \< /artículos >.  Si se especifica ninguna anotación, a continuación, la cadena contiene \<elementos / >. El tamaño del evento ETW está limitado por el tamaño de búfer de ETW o la carga útil máxima para un evento ETW. Si el tamaño del evento supera los límites de ETW, el evento se trunca quitando las anotaciones y reemplazando el valor de anotación con \<elementos >...  \< /artículos >.|  
|ProfileName|xs:string|El nombre o el perfil de seguimiento que dio como resultado que se emitiera este evento.|  
|HostReference|xs:string|En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.  Su formato se define como ' ruta de acceso Virtual de sitio Web de nombre aplicación&#124;ruta de acceso Virtual del servicio&#124;NombreServicio ' ejemplo: ' sitio Web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
