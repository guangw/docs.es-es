---
title: 'Cómo: Proporcionar un fondo transparente a un control'
ms.date: 03/30/2017
helpviewer_keywords:
- transparent backgrounds [Windows Forms], custom controls
- custom controls [Windows Forms], transparent background
- transparency [Windows Forms], Windows Forms custom controls
ms.assetid: 32433e63-f4e9-4305-9857-6de3edeb944a
ms.openlocfilehash: ad814c9179fd33955fe4df2666f8a47606bfbff0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-give-your-control-a-transparent-background"></a>Cómo: Proporcionar un fondo transparente a un control
En versiones anteriores de .NET Framework, los controles no admitían la opción de establecer fondos transparentes sin establecer primero el método <xref:System.Windows.Forms.Control.SetStyle%2A> en el constructor de formularios. En la versión actual de .NET Framework, el color de fondo de la mayoría de los controles se puede establecer como <xref:System.Drawing.Color.Transparent%2A> en la ventana **Propiedades** durante el tiempo de diseño o como código en el constructor del formulario.  
  
> [!NOTE]
>  Los controles de Windows Forms no admiten una transparencia real. El fondo de un control de Windows Forms transparente lo pinta su control primario.  
  
> [!NOTE]
>  El control <xref:System.Windows.Controls.Button> no admite un color de fondo transparente incluso si la propiedad <xref:System.Windows.Forms.ButtonBase.BackColor%2A> se estableció como <xref:System.Drawing.Color.Transparent%2A>.  
  
### <a name="to-give-your-control-a-transparent-backcolor"></a>Proporcionar un fondo transparente a un control  
  
-   En la ventana Propiedades, elija la propiedad <xref:System.Windows.Forms.ButtonBase.BackColor%2A> y establézcala como <xref:System.Drawing.Color.Transparent%2A>  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.Color.FromArgb%2A>  
 [Desarrollar controles personalizados de Windows Forms con .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [Using Managed Graphics Classes](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md) (Usar clases gráficas administradas)  
 [Dibujar líneas opacas y semitransparentes](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)
