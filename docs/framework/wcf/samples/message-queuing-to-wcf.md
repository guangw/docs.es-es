---
title: "Message Queuing a Windows Communication Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6d718eb0-9f61-4653-8a75-d2dac8fb3520
caps.latest.revision: 34
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 34
---
# Message Queuing a Windows Communication Foundation
Este ejemplo muestra cómo una aplicación de Message Queuing \(MSMQ\) puede enviar un mensaje de MSMQ a un servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].El servicio es una aplicación de consola autohospedada que le permite observar el servicio que recibe los mensajes en cola.  
  
 El contrato de servicio es `IOrderProcessor`, que define un servicio unidireccional que es adecuado para el uso con colas.Un mensaje de MSMQ no tiene un encabezado Acción, por lo que no es posible asignar automáticamente distintos mensajes de MSMQ a los contratos de operación.Además, solo puede haber un contrato de operación.Si desea definir más de un contrato de operación para el servicio, la aplicación debe proporcionar información como qué encabezado en el mensaje de MSMQ \(por ejemplo, la etiqueta o correlationID\) se puede utilizar para decidir qué contrato de operación distribuir.Esto se muestra en [Demux personalizado](../../../../docs/framework/wcf/samples/custom-demux.md).  
  
 El mensaje de MSMQ no contiene información sobre qué encabezados están asignados a los distintos parámetros del contrato de operación.El parámetro es de tipo <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>\(`MsmqMessage<T>`\), que contiene el mensaje de MSMQ subyacente.El tipo "T" en la clase <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>\(`MsmqMessage<T>`\) representa los datos que se serializan en el cuerpo del mensaje de MSMQ.En este ejemplo, el tipo `PurchaseOrder` se serializa en el cuerpo del mensaje de MSMQ.  
  
 El código de ejemplo siguiente muestra el contrato de servicio del servicio de procesamiento de órdenes.  
  
```  
// Define a service contract.  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
[ServiceKnownType(typeof(PurchaseOrder))]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true, Action = "*")]  
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);  
}  
  
```  
  
 El servicio es autohospedado.Al utilizar MSMQ, la cola usada debe crearse de antemano.Esto se puede hacer manualmente o a través de código.En este ejemplo, el servicio comprueba la existencia de la cola y la crea si es necesario.El nombre de la cola se lee del archivo de configuración.  
  
```  
public static void Main()  
{  
    // Get the MSMQ queue name from the application settings in   
    // configuration.  
    string queueName = ConfigurationManager.AppSettings["queueName"];  
    // Create the MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
    …  
}  
  
```  
  
 El servicio crea y abre un <xref:System.ServiceModel.ServiceHost> para `OrderProcessorService`, tal y como se muestra en el código de ejemplo siguiente.  
  
```  
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))  
{  
    serviceHost.Open();  
    Console.WriteLine("The service is ready.");  
    Console.WriteLine("Press <ENTER> to terminate service.");  
    Console.ReadLine();  
    serviceHost.Close();  
}  
  
```  
  
 El nombre de cola de MSMQ se especifica en una sección appSettings del archivo de configuración, tal y como se muestra en la configuración de ejemplo siguiente.  
  
> [!NOTE]
>  El nombre de la cola utiliza un punto \(.\) para el equipo local y separadores con barra diagonal inversa en su ruta de acceso.La dirección de extremo de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] especifica un esquema msmq.formatname y utiliza localhost para el equipo local.La dirección de la cola para las directrices de direccionamiento del nombre de formato de MSMQ sigue el esquema msmq.formatname.  
  
```  
<appSettings>  
    <add key="orderQueueName" value=".\private$\Orders" />  
</appSettings>  
  
```  
  
 La aplicación cliente es una aplicación MSMQ que utiliza el método <xref:System.Messaging.MessageQueue.Send%2A> para enviar un mensaje duradero y un mensaje transaccional a la cola, tal y como se muestra en el código de ejemplo siguiente.  
  
```  
//Connect to the queue.  
MessageQueue orderQueue = new MessageQueue(ConfigurationManager.AppSettings["orderQueueName"]);  
  
// Create the purchase order.  
PurchaseOrder po = new PurchaseOrder();  
po.CustomerId = "somecustomer.com";  
po.PONumber = Guid.NewGuid().ToString();  
  
PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();  
lineItem1.ProductId = "Blue Widget";  
lineItem1.Quantity = 54;  
lineItem1.UnitCost = 29.99F;  
  
PurchaseOrderLineItem lineItem2 = new PurchaseOrderLineItem();  
lineItem2.ProductId = "Red Widget";  
lineItem2.Quantity = 890;  
lineItem2.UnitCost = 45.89F;  
  
po.orderLineItems = new PurchaseOrderLineItem[2];  
po.orderLineItems[0] = lineItem1;  
po.orderLineItems[1] = lineItem2;  
  
// Submit the purchase order.  
Message msg = new Message();  
msg.Body = po;  
//Create a transaction scope.  
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
{  
  
    orderQueue.Send(msg, MessageQueueTransactionType.Automatic);  
    // Complete the transaction.  
    scope.Complete();  
  
}  
Console.WriteLine("Placed the order:{0}", po);  
Console.WriteLine("Press <ENTER> to terminate client.");  
Console.ReadLine();  
  
```  
  
 Al ejecutar el ejemplo, las actividades del servicio y del cliente se muestran en las ventanas de la consola del cliente y del servicio.Puede ver los mensajes recibidos por el servicio desde el cliente.Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.Observe que debido a que se está usando el proceso de poner en cola, el cliente y el servicio no tienen que estar activados y ejecutándose simultáneamente.Por ejemplo, podría ejecutar el cliente, cerrarlo e iniciar el servicio después y recibiría aún sus mensajes.  
  
### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de realizar el procedimiento de [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Si se ejecuta el servicio primero, comprobará que la cola esté presente.Si la cola no está presente, el servicio creará una.Puede ejecutar primero el servicio para crear la cola, o puede crear una a través del administrador de cola de MSMQ.Siga estos pasos para crear una cola en Windows 2008.  
  
    1.  Abra el Administrador del servidor en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
    2.  Expanda la pestaña **Características**.  
  
    3.  Haga clic con el botón secundario en **Cola de mensajes privados** y seleccione **Nuevo**, **Cola privada**.  
  
    4.  Active la casilla **Transaccional**.  
  
    5.  Escriba `ServiceModelSamplesTransacted` como nombre de la nueva cola.  
  
3.  Para compilar el código de la edición .NET de C\# o Visual Basic de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Para ejecutar el ejemplo en una configuración de un solo equipo, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### Para ejecutar el ejemplo en varios equipos  
  
1.  Copie los archivos de programa del servicio de la carpeta \\service\\bin\\, bajo la carpeta específica del lenguaje, al equipo del servicio.  
  
2.  Copie los archivos de programa del cliente de la carpeta \\client\\bin\\, bajo la carpeta específica del lenguaje, al equipo cliente.  
  
3.  En el archivo Client.exe.config, cambie orderQueueName para especificar el nombre de equipo del servicio en lugar de ".".  
  
4.  En el equipo del servicio, inicie Service.exe desde un símbolo del sistema.  
  
5.  En el equipo cliente, inicie Client.exe desde un símbolo del sistema.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\MsmqToWcf`  
  
## Vea también  
 [Colas en WCF](../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)   
 [Cómo: Intercambiar mensajes con extremos de WCF y aplicaciones de Message Queuing](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)   
 [Message Queuing](http://go.microsoft.com/fwlink/?LinkId=94968)