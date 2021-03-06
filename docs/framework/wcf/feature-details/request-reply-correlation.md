---
title: Correlación entre solicitud y respuesta
ms.date: 03/30/2017
ms.assetid: cf4379bf-2d08-43f3-9584-dfa30ffcb1f6
ms.openlocfilehash: c38854ad42ad4dddce5171482f3ddcfe5bd16b61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="request-reply-correlation"></a>Correlación entre solicitud y respuesta
Correlación de solicitud-respuesta se utiliza con un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> par para implementar una operación bidireccional en un servicio de flujo de trabajo y con un <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> par que invoca una operación bidireccional en otro sitio Web servicio. Al invocar una operación bidireccional en un servicio WCF, el servicio puede ser un tradicional imperativa basada en código de servicio de Windows Communication Foundation (WCF) o puede ser un servicio de flujo de trabajo. Para utilizar la correlación de solicitud-respuesta, debe usarse un enlace bidireccional, como <xref:System.ServiceModel.BasicHttpBinding>. Ya invoque o implemente una operación bidireccional, los pasos de inicialización de la correlación son similares y se cubren en esta sección.  
  
## <a name="using-correlation-in-a-two-way-operation-with-receivesendreply"></a>Utilizar correlación en una operación bidireccional con Receive/SendReply  
 A <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> par se utiliza para implementar una operación bidireccional en un servicio de flujo de trabajo. El tiempo de ejecución usa una correlación de solicitud-respuesta para asegurarse de que la respuesta se envía al autor de la llamada correcto. Cuando un flujo de trabajo se hospeda mediante <xref:System.ServiceModel.Activities.WorkflowServiceHost>, como es el caso de los servicios de flujo de trabajo, es suficiente la inicialización de correlación predeterminada. En este escenario, un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> par se utiliza un flujo de trabajo y se requiere ninguna configuración de correlación concreto.  
  
```csharp  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
### <a name="explicitly-initializing-request-reply-correlation"></a>Inicializar explícitamente una correlación de solicitud-respuesta  
 Si se producen otras operaciones bidireccionales en paralelo, la correlación se debería configurar de forma explícita. Esto puede hacerse mediante la especificación de un <xref:System.ServiceModel.Activities.CorrelationHandle> y <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>, o colocando el <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> dentro de un <xref:System.ServiceModel.Activities.CorrelationScope>. En este ejemplo, correlación de solicitud-respuesta se configura en un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> par.  
  
```csharp  
Variable<CorrelationHandle> RRHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder",  
    CorrelationInitializers =  
    {  
        new RequestReplyCorrelationInitializer  
        {  
            CorrelationHandle = RRHandle  
        }  
    }  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
 En lugar de configurar explícitamente la correlación, se puede usar una actividad <xref:System.ServiceModel.Activities.CorrelationScope>. <xref:System.ServiceModel.Activities.CorrelationScope> proporciona un <xref:System.ServiceModel.Activities.CorrelationHandle> implícito para las actividades de mensajería que contiene. En este ejemplo, un <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> par se encuentra dentro de un <xref:System.ServiceModel.Activities.CorrelationScope>. No se requiere ninguna configuración de correlación explícita.  
  
```csharp  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
CorrelationScope s = new CorrelationScope  
{  
    Body = new Sequence  
    {  
        Activities =   
        {  
            StartOrder,  
            // Activities that create the reply.  
            ReplyToStartOrder  
        }  
    }  
};  
  
// Construct a workflow using the CorrelationScope.  
```  
  
 Si se requieren correlaciones adicionales, se pueden configurar mediante la propiedad <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> de las actividades de mensajería respectivas utilizando los tipos `CorrelationInitializer` deseados.  
  
## <a name="using-correlation-in-a-two-way-operation-with-sendreceivereply"></a>Utilizar correlación en una operación bidireccional con Send/ReceiveReply  
 Mientras el <xref:System.ServiceModel.Activities.Receive> actividad solo puede usarse en un servicio de flujo de trabajo hospedado por <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.ServiceModel.Activities.Send> y <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> par puede utilizarse en cualquier flujo de trabajo que se debe invocar un método en un servicio Web. Si el flujo de trabajo se hospeda utilizando <xref:System.ServiceModel.Activities.WorkflowServiceHost>, se aplica la correlación predeterminada descrita en la sección anterior; si no es así, hay que configurar la correlación utilizando explícitamente las clases <xref:System.ServiceModel.Activities.CorrelationInitializer> y <xref:System.ServiceModel.Activities.CorrelationHandle> deseadas, o utilizando la administración de control implícita de <xref:System.ServiceModel.Activities.CorrelationScope>.  
  
 Cuando se usa **Agregar referencia de servicio** en un servicio con operaciones bidireccionales, se generan las actividades que ajustan un <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> actividad internamente con la correlación de solicitud/respuesta del par explícitamente especificado.
