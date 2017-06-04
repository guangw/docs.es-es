---
title: "C&#243;mo: Habilitar operaciones de arrastrar y colocar con el control RichTextBox de formularios Windows Forms | Microsoft Docs"
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
  - "ejemplos [formularios Windows Forms], cuadros de texto"
  - "arrastrar y colocar, control RichTextBox"
  - "cuadros de texto, operaciones de arrastrar y colocar"
  - "RichTextBox (control) [formularios Windows Forms], operaciones de arrastrar y colocar"
ms.assetid: ca167d1c-2014-4cf0-96a0-20598470be3b
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Habilitar operaciones de arrastrar y colocar con el control RichTextBox de formularios Windows Forms
Las operaciones de arrastrar y colocar con el control <xref:System.Windows.Forms.RichTextBox> de formularios Windows Forms se realizan mediante el control de los eventos <xref:System.Windows.Forms.RichTextBox.DragEnter> y <xref:System.Windows.Forms.RichTextBox.DragDrop>. Por lo tanto, las operaciones de arrastrar y colocar son extremadamente sencillas con el control <xref:System.Windows.Forms.RichTextBox>.  
  
### Para habilitar las operaciones de arrastre en un control RichTextBox  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.RichTextBox.AllowDrop%2A> del control <xref:System.Windows.Forms.RichTextBox> en `true`.  
  
2.  Escriba código en el controlador de eventos del evento <xref:System.Windows.Forms.RichTextBox.DragEnter>. Use una declaración `if` para asegurarse de que los datos que se arrastran son de un tipo aceptable \(en este caso, texto\). La propiedad <xref:System.Windows.Forms.DragEventArgs.Effect%2A?displayProperty=fullName> se puede establecer en cualquier valor de la enumeración <xref:System.Windows.Forms.DragDropEffects>.  
  
    ```vb  
    Private Sub RichTextBox1_DragEnter(ByVal sender As Object, _   
       ByVal e As System.Windows.Forms.DragEventArgs) _   
       Handles RichTextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
          e.Effect = DragDropEffects.Copy  
       Else  
          e.Effect = DragDropEffects.None  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void richTextBox1_DragEnter(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))   
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void richTextBox1_DragEnter(System::Object ^  sender,  
          System::Windows::Forms::DragEventArgs ^  e)  
       {  
          if (e->Data->GetDataPresent(DataFormats::Text))  
             e->Effect = DragDropEffects::Copy;  
          else  
             e->Effect = DragDropEffects::None;  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] y [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.richTextBox1.DragEnter += new  
        System.Windows.Forms.DragEventHandler  
        (this.richTextBox1_DragEnter);  
    ```  
  
    ```cpp  
    this->richTextBox1->DragEnter += gcnew  
       System::Windows::Forms::DragEventHandler  
       (this, &Form1::richTextBox1_DragEnter);  
    ```  
  
3.  Escriba código para controlar el evento <xref:System.Windows.Forms.RichTextBox.DragDrop>. Utilice el método <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=fullName> para recuperar los datos que se están arrastrando.  
  
     En el ejemplo siguiente, el código establece la propiedad <xref:System.Windows.Forms.RichTextBox.Text%2A> del control <xref:System.Windows.Forms.RichTextBox> igual a los datos que se están arrastrando. Si ya hay texto en el control <xref:System.Windows.Forms.RichTextBox>, el texto arrastrado se inserta en el punto de inserción.  
  
    ```vb  
    Private Sub RichTextBox1_DragDrop(ByVal sender As Object, _   
       ByVal e As System.Windows.Forms.DragEventArgs) _   
       Handles RichTextBox1.DragDrop  
       Dim i As Int16   
       Dim s As String  
  
       ' Get start position to drop the text.  
       i = RichTextBox1.SelectionStart  
       s = RichTextBox1.Text.Substring(i)  
       RichTextBox1.Text = RichTextBox1.Text.Substring(0, i)  
  
       ' Drop the text on to the RichTextBox.  
       RichTextBox1.Text = RichTextBox1.Text + _  
          e.Data.GetData(DataFormats.Text).ToString()  
       RichTextBox1.Text = RichTextBox1.Text + s  
    End Sub  
  
    ```  
  
    ```csharp  
    private void richTextBox1_DragDrop(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       int i;  
       String s;  
  
       // Get start position to drop the text.  
       i = richTextBox1.SelectionStart;  
       s = richTextBox1.Text.Substring(i);  
       richTextBox1.Text = richTextBox1.Text.Substring(0,i);  
  
       // Drop the text on to the RichTextBox.  
       richTextBox1.Text = richTextBox1.Text +   
          e.Data.GetData(DataFormats.Text).ToString();  
       richTextBox1.Text = richTextBox1.Text + s;  
    }  
  
    ```  
  
    ```cpp  
    private:  
       System::Void richTextBox1_DragDrop(System::Object ^  sender,  
          System::Windows::Forms::DragEventArgs ^  e)  
       {  
          int i;  
          String ^s;  
  
       // Get start position to drop the text.  
       i = richTextBox1->SelectionStart;  
       s = richTextBox1->Text->Substring(i);  
       richTextBox1->Text = richTextBox1->Text->Substring(0,i);  
  
       // Drop the text on to the RichTextBox.  
       String ^str = String::Concat(richTextBox1->Text, e->Data  
       ->GetData(DataFormats->Text)->ToString());   
       richTextBox1->Text = String::Concat(str, s);  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] y [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.richTextBox1.DragDrop += new  
        System.Windows.Forms.DragEventHandler  
        (this.richTextBox1_DragDrop);  
  
    ```  
  
    ```cpp  
    this->richTextBox1->DragDrop += gcnew   
       System::Windows::Forms::DragEventHandler  
       (this, &Form1::richTextBox1_DragDrop);  
    ```  
  
### Para probar la funcionalidad de arrastrar y colocar en la aplicación  
  
1.  Guarde y compile la aplicación. Mientras se esté ejecutando, ejecute WordPad.  
  
     WordPad es un editor de texto instalado por Windows que permite operaciones de arrastrar y colocar. Para acceder a este, haga clic en el botón **Inicio**, seleccione **Ejecutar**, escriba `WordPad` en el cuadro de texto del cuadro de diálogo **Ejecutar** y, después, haga clic en **Aceptar**.  
  
2.  Una vez abierto WordPad, escriba una cadena de texto en esta aplicación. Use el mouse para seleccionar el texto y, después, arrastre el texto seleccionado al control <xref:System.Windows.Forms.RichTextBox> de la aplicación Windows.  
  
     Observe que, cuando el mouse señala el control <xref:System.Windows.Forms.RichTextBox> \(y, por consiguiente, genera el evento <xref:System.Windows.Forms.RichTextBox.DragEnter>\), el cursor cambia y puede colocar el texto seleccionado en el control <xref:System.Windows.Forms.RichTextBox>.  
  
     Al soltar el botón del mouse, se quita el texto seleccionado \(es decir, se genera el evento <xref:System.Windows.Forms.RichTextBox.DragDrop>\) y se inserta en el control <xref:System.Windows.Forms.RichTextBox>.  
  
## Vea también  
 <xref:System.Windows.Forms.RichTextBox>   
 [How to: Perform Drag\-and\-Drop Operations Between Applications](../../../../docs/framework/winforms/advanced/how-to-perform-drag-and-drop-operations-between-applications.md)   
 [RichTextBox \(Control\)](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)