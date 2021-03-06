---
title: Ejemplo de actividad compensable
ms.date: 03/30/2017
ms.assetid: 58f4898c-b2b8-44a4-9a73-3bef4da6d5ba
ms.openlocfilehash: 8008eaaca062723cab1efabfb1b25018353c73b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compensable-activity-sample"></a>Ejemplo de actividad compensable
En este ejemplo se muestra cómo utilizar la actividad `CompensableActivity` para definir el trabajo que se va a realizar para una acción determinada durante la ejecución normal y el trabajo que es necesario realizar para compensar dicha acción, si es necesario en un momento posterior.  La primera parte del ejemplo muestra cómo unidades de trabajo de compensación se pueden definir en Windows Workflow Foundation (WF) utilizando un `CompensableActivity` actividad y cómo se ejecutan en una ejecución correcta.  La segunda parte del ejemplo muestra cómo las mismas unidades de trabajo compensable se ocupan automáticamente de la compensación cuando se produce un evento inesperado y se cancela la instancia de flujo de trabajo.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Con Visual Studio 2010, abra CompensableActivity.sln.  
  
2.  Compile la solución presionando CTRL+MAYÚS+B.  
  
3.  Ejecute la aplicación presionando F5.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\BasicCompensableActivity`