---
title: "C&#243;mo: Enlazar datos al control DataGridView de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "enlace de datos, DataGridView (control)"
  - "enlace de datos, cuadrículas"
  - "DataGridView (control) [Windows Forms], enlace de datos"
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
caps.latest.revision: 30
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 30
---
# C&#243;mo: Enlazar datos al control DataGridView de formularios Windows Forms
El control <xref:System.Windows.Forms.DataGridView> admite el modelo de enlace de datos de Windows Forms estándar, por lo que se enlazará a distintos orígenes de datos.  Sin embargo, en la mayoría de los casos se enlazará a un componente <xref:System.Windows.Forms.BindingSource> que administrará los detalles de la interacción con el origen de datos.  El componente <xref:System.Windows.Forms.BindingSource> puede representar cualquier origen de datos de Windows Forms y proporciona gran flexibilidad a la hora de elegir o modificar la ubicación de los datos.  Para obtener más información acerca de los orígenes de datos admitidos por el control <xref:System.Windows.Forms.DataGridView>, consulte [Información general del control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md).  
  
 Visual Studio es altamente compatible con esta tarea.  Consulte también [Cómo: Enlazar datos al control DataGridView de Windows Forms mediante el Diseñador](http://msdn.microsoft.com/library/33w255ac%20\(v=vs.110\)).  
  
## Procedimiento  
  
#### Para conectar un control DataGridView a datos  
  
1.  Implemente un método que controle los detalles de recuperación de datos desde una base de datos.  En el ejemplo de código siguiente se implementa un método `GetData` que inicializa un componente <xref:System.Data.SqlClient.SqlDataAdapter> y lo usa para rellenar una <xref:System.Data.DataTable>.  Después, la <xref:System.Data.DataTable> se enlaza al componente <xref:System.Windows.Forms.BindingSource>.  Asegúrese de establecer la variable `connectionString` en un valor que sea adecuado para la base de datos.  Necesitará acceso a un servidor que tenga instalada la base de datos de ejemplo SQL Server Northwind.  
  
     [!code-cpp[System.Windows.Forms.DataGridViewBoundEditable#20](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/cpp/datagridviewboundeditable.cpp#20)]
     [!code-csharp[System.Windows.Forms.DataGridViewBoundEditable#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewBoundEditable#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb#20)]  
  
2.  En el controlador de eventos <xref:System.Windows.Forms.Form.Load> del formulario, enlace el control <xref:System.Windows.Forms.DataGridView> al componente <xref:System.Windows.Forms.BindingSource> y llame al método `GetData` para recuperar los datos de la base de datos.  
  
     [!code-cpp[System.Windows.Forms.DataGridViewBoundEditable#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/cpp/datagridviewboundeditable.cpp#10)]
     [!code-csharp[System.Windows.Forms.DataGridViewBoundEditable#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewBoundEditable#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb#10)]  
  
## Ejemplo  
 El siguiente ejemplo de código completo proporciona botones para volver a cargar los datos de la base de datos y enviar los cambios a la base de datos.  
  
 [!code-cpp[System.Windows.Forms.DataGridViewBoundEditable#00](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/cpp/datagridviewboundeditable.cpp#00)]
 [!code-csharp[System.Windows.Forms.DataGridViewBoundEditable#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewBoundEditable#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb#00)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Windows.Forms, System.Data y System.XML.  
  
 Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228%20\(v=vs.110\)).  
  
## Seguridad de .NET Framework  
 Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación.  El uso de la autenticación de Windows \(también conocida como seguridad integrada\) es un modo más seguro de controlar el acceso a una base de datos.  Para obtener más información, consulte [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.BindingSource>   
 [Mostrar datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md)