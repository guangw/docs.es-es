---
title: "Ejemplo de configuraci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 75515b4a-8d70-44c8-99e0-7423df41380e
caps.latest.revision: 21
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 21
---
# Ejemplo de configuraci&#243;n
En este ejemplo se muestra el uso de un archivo de configuración para hacer que un servicio se pueda detectar.  
  
> [!NOTE]
>  En este ejemplo se implementa la detección en la configuración.Para obtener un ejemplo que implementa la detección en el código, vea [Básico](../../../../docs/framework/wcf/samples/basic-sample.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Discovery\Configuration`  
  
## Configuración del servicio  
 El archivo de configuración de este ejemplo muestra dos características:  
  
-   Hacer que el servicio se pueda detectar a través de un <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> estándar.  
  
-   Ajustar la información relacionada con la detección para el extremo de la aplicación del servicio y ajustar algunos de los valores relacionados con la detección en el extremo estándar.  
  
 Para habilitar la detección, se deben realizar algunas modificaciones en el archivo de configuración de la aplicación para el servicio:  
  
-   Un extremo de detección se debe agregar al elemento `<service>`.Se trata de un extremo <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> estándar.Este es un extremo del sistema que el tiempo de ejecución asocia al servicio de detección.El servicio de descarga realiza escuchas de los mensajes en este extremo.  
  
-   Se agrega un comportamiento `<serviceDiscovery>` a la sección `<serviceBehaviors>`.Esto permite detectar el servicio en tiempo de ejecución runtime y utiliza el extremo de la detección mencionado previamente para realizar escuchas de `Probe` de detección y mensajes `Resolve`.Con estas dos incorporaciones, el servicio se puede detectar en el extremo de detección especificado.  
  
 El siguiente fragmento de código muestra un servicio con un extremo de la aplicación y un extremo de detección definidos:  
  
```vb  
<services>  
        <service name="Microsoft.Samples.Discovery.CalculatorService"  
                 behaviorConfiguration="calculatorServiceBehavior">  
          <endpoint address=""  
                    binding="wsHttpBinding"  
                    contract="Microsoft.Samples.Discovery.ICalculatorService"  
                    behaviorConfiguration="endpointBehaviorConfiguration" />  
          <endpoint name="udpDiscovery"   
                    kind="udpDiscoveryEndpoint"   
                endpointConfiguration="adhocDiscoveryEndpointConfiguration"/>        </service>  
      </services>  
  
```  
  
 Para beneficiarse de los anuncios, tendrá que agregar un extremo de anuncio.Para ello, modifique el archivo de configuración según se muestra en el código siguiente.  
  
```  
  
<serviceDiscovery>  
            <announcementEndpoints>  
              <endpoint kind="udpAnnouncementEndpoint"/>  
            </announcementEndpoints>  
          </serviceDiscovery>  
  
```  
  
 Al agregar un extremo de anuncio al comportamiento del servicio de detección, se crea un cliente de anuncio predeterminado para el servicio.Esto garantiza que el servicio enviará un anuncio en línea y sin conexión cuando el servicio se abra y se cierre respectivamente.  
  
 Este archivo de configuración supera esos pasos sencillos al modificar comportamientos adicionales.Es posible controlar la información relacionada con la detección utilizando extremos concretos.Es decir, un usuario puede controlar si se puede detectar un extremo y también puede marcar ese extremo con metadatos XML personalizados y la propiedad <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Scopes%2A>.Para ello, el usuario debe agregar una propiedad `behaviorConfiguration` al extremo de la aplicación.En este caso, la siguiente propiedad se agrega al extremo de la aplicación.  
  
```  
behaviorConfiguration="endpointBehaviorConfiguration"  
```  
  
 Ahora, a través del elemento de configuración de comportamiento, puede controlar los atributos relacionados con la detección.En este caso, se agregan dos ámbitos al extremo de la aplicación.  
  
```xml  
<endpointBehaviors>  
          <behavior name="endpointBehaviorConfiguration">  
            <endpointDiscovery>  
              <scopes>  
                <add scope="http://www.example.com/calculator"/>  
                <add scope="ldap:///ou=engineering,o=examplecom,c=us"/>  
              </scopes>  
            </endpointDiscovery>  
  
          </behavior>            
        </endpointBehaviors>  
  
```  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] los ámbitos, vea [Búsqueda de detección y FindCriteria](../../../../docs/framework/wcf/feature-details/discovery-find-and-findcriteria.md).  
  
 También puede controlar detalles concretos del extremo de la detección.Esto se hace a través de <xref:System.ServiceModel.Configuration.StandardEndpointsSection>.En este ejemplo, se modifica la versión del protocolo utilizada además de agregar un atributo `maxResponseDelay` en el siguiente ejemplo de código.  
  
```  
<standardEndpoints>  
   <udpDiscoveryEndpoint>  
      <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11" maxResponseDelay="00:00:00.600" />    
   </udpDiscoveryEndpoint>  
</standardEndpoints>  
  
```  
  
 Lo siguiente es el archivo de configuración completo usado en este ejemplo:  
  
```  
<configuration>  
    <system.serviceModel>  
  
      <services>  
        <service name="Microsoft.Samples.Discovery.CalculatorService"  
                 behaviorConfiguration="calculatorServiceBehavior">  
          <endpoint address=""  
                    binding="wsHttpBinding"  
                    contract="Microsoft.Samples.Discovery.ICalculatorService"  
                    behaviorConfiguration="endpointBehaviorConfiguration" />  
         <!-- Define the discovery endpoint -->            
<endpoint name="udpDiscovery" kind="udpDiscoveryEndpoint" endpointConfiguration="adhocDiscoveryEndpointConfiguration"/>        </service>  
      </services>  
  
      <behaviors>  
  
        <serviceBehaviors>  
          <behavior name="calculatorServiceBehavior">  
  
            <!-- Add an announcement endpoint -->  
            <serviceDiscovery>  
              <announcementEndpoints>  
                <endpoint kind="udpAnnouncementEndpoint"/>  
              </announcementEndpoints>  
            </serviceDiscovery>  
          </behavior>  
        </serviceBehaviors>  
  
        <endpointBehaviors>  
          <behavior name="endpointBehaviorConfiguration">  
            <!-- Add scopes used to identify the service -->  
            <endpointDiscovery>  
              <scopes>  
                <add scope="http://www.example.com/calculator"/>  
                <add scope="ldap:///ou=engineering,o=examplecom,c=us"/>  
              </scopes>  
            </endpointDiscovery>  
  
          </behavior>            
        </endpointBehaviors>  
  
      </behaviors>  
  
      <standardEndpoints>  
        <udpDiscoveryEndpoint>  
         <!-- Configure the UDP discovery endpoint -->  
          <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11" maxResponseDelay="00:00:00.600" />    
        </udpDiscoveryEndpoint>  
      </standardEndpoints>  
  
    </system.serviceModel>  
</configuration>  
  
```  
  
## Configuración del cliente  
 En el archivo de configuración de la aplicación para el cliente, para la detección se usa el `standardEndpoint` de tipo `dynamicEndpoint`, según se muestra en el fragmento de configuración siguiente.  
  
```xml  
<client>  
   <!--  Create an endpoint, make kind="dynamicEndpoint" and use the endpointConfiguration to change settings of DynamicEndpoint -->  
   <endpoint name="calculatorEndpoint"  
             binding="wsHttpBinding"  
             contract="ICalculatorService"  
             kind ="dynamicEndpoint"  
             endpointConfiguration="dynamicEndpointConfiguration">  
   </endpoint>  
</client>  
  
```  
  
 Cuando un cliente utiliza un `dynamicEndpoint`, el tiempo de ejecución realiza la detección automáticamente.Durante la detección se usan varias opciones de configuración, como las definidas en la sección `discoveryClientSettings`, que especifica el tipo de extremo de detección que se usará:  
  
```xml  
<endpoint kind="udpDiscoveryEndpoint" endpointConfiguration="adhocDiscoveryEndpointConfiguration" />  
  
```  
  
 Los criterios de búsqueda que se usan para buscar servicios:  
  
```xml  
<!-- Add Scopes, ScopeMatchBy, Extensions and termination criteria in FindCriteria -->  
<findCriteria scopeMatchBy="http://schemas.microsoft.com/ws/2008/06/discovery/rfc" duration="00:00:10" maxResults="1">  
   <scopes>  
      <add scope="http://www.microsoft.com/building42/floor1"/>  
   </scopes>  
   <!-- These extensions are sent from the client to the service as part of the probe message -->  
   <extensions>  
      <CustomMetadata>This is custom metadata that is sent to the service along with the client's find request.</CustomMetadata>  
   </extensions>  
</findCriteria>  
  
```  
  
 Este ejemplo extiende esta característica y modifica el objeto <xref:System.ServiceModel.Discovery.FindCriteria> utilizado por el cliente, así como algunas propiedades del `updDiscoveryEndpoint` estándar que se usa en la detección.Los <xref:System.ServiceModel.Discovery.FindCriteria> se modifican para utilizar un ámbito y un algoritmo `scopeMatchBy` concreto, así como los criterios de terminación personalizados.Además, el ejemplo también muestra el modo en que un cliente puede enviar elementos XML mediante mensajes `Probe`.Por último, se realizan algunos cambios en <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, como la versión del protocolo utilizado y los valores específicos del UDP, como se muestra en el siguiente archivo de configuración.  
  
```xml  
<udpDiscoveryEndpoint>    
        <!-- Specify the discovery protocol version and UDP transport settings. -->   
        <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11">  
          <transportSettings duplicateMessageHistoryLength="2048"  
                             maxPendingMessageCount="5"  
                             maxReceivedMessageSize="8192"  
                             maxBufferPoolSize="262144"/>  
        </standardEndpoint>        
      </udpDiscoveryEndpoint>  
  
```  
  
 Lo siguiente es el archivo de configuración de cliente completo usado en este ejemplo.  
  
```  
<configuration>  
  <system.serviceModel>  
  
    <client>  
      <!--  Create an endpoint, make kind="dynamicEndpoint" and use the endpointConfiguration to change settings of DynamicEndpoint -->  
      <endpoint name="calculatorEndpoint"  
                binding="wsHttpBinding"  
                contract="ICalculatorService"  
                kind ="dynamicEndpoint"  
                endpointConfiguration="dynamicEndpointConfiguration">  
      </endpoint>  
    </client>  
  
    <standardEndpoints>  
  
      <dynamicEndpoint>        
        <standardEndpoint name="dynamicEndpointConfiguration">  
          <discoveryClientSettings>  
            <!-- Controls where the discovery happens. In this case, Probe message is sent over UdpDiscoveryEndpoint. -->  
            <endpoint kind="udpDiscoveryEndpoint" endpointConfiguration="adhocDiscoveryEndpointConfiguration" />  
  
            <!-- Add Scopes, ScopeMatchBy, Extensions and termination criteria in FindCriteria -->  
            <findCriteria scopeMatchBy="http://schemas.microsoft.com/ws/2008/06/discovery/rfc" duration="00:00:10" maxResults="1">  
              <scopes>  
                <add scope="http://www.microsoft.com/building42/floor1"/>  
              </scopes>  
              <!-- These extensions are sent from the client to the service as part of the probe message -->  
              <extensions>  
                <CustomMetadata>This is custom metadata that is sent to the service along with the client's find request.</CustomMetadata>  
              </extensions>  
            </findCriteria>  
          </discoveryClientSettings>  
        </standardEndpoint>     
      </dynamicEndpoint>  
  
      <udpDiscoveryEndpoint>    
        <!-- Specify the discovery protocol version and UDP transport settings. -->   
        <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11">  
          <transportSettings duplicateMessageHistoryLength="2048"  
                             maxPendingMessageCount="5"  
                             maxReceivedMessageSize="8192"  
                             maxBufferPoolSize="262144"/>  
        </standardEndpoint>        
      </udpDiscoveryEndpoint>  
  
    </standardEndpoints>  
  
  </system.serviceModel>  
  
```  
  
#### Para utilizar este ejemplo  
  
1.  Este ejemplo utiliza los extremos HTTP y para ejecutarlo se deben agregar las ACL de dirección URL apropiadas; vea [Configurar HTTP y HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) para obtener detalles.Al ejecutar el siguiente comando con privilegios elevados, se deberían agregar las ACL adecuadas.Puede que desee sustituir su dominio y nombre de usuario para los siguientes argumentos si el comando no funciona como debería.`netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
2.  Compile la solución.  
  
3.  Ejecute el ejecutable de servicio desde el directorio de compilación.  
  
4.  Ejecute la aplicación cliente.Observe que el cliente puede localizar el servicio.  
  
## Vea también