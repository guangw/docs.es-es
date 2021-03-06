---
title: 'Cómo: Girar un objeto'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rotating objects [WPF]
- rotating objects [WPF]
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
ms.openlocfilehash: 7eb562d81bdd8c9187672b31ed08ed6ac27da41c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-rotate-an-object"></a>Cómo: Girar un objeto
Este ejemplo muestra cómo girar un objeto. El ejemplo crea primero un <xref:System.Windows.Media.RotateTransform> y, a continuación, especifica su <xref:System.Windows.Media.RotateTransform.Angle%2A> en grados.  
  
 En el ejemplo siguiente se gira un <xref:System.Windows.Shapes.Polyline> 45 grados sobre su esquina superior izquierda del objeto.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 El <xref:System.Windows.Media.RotateTransform.CenterX%2A> y <xref:System.Windows.Media.RotateTransform.CenterY%2A> propiedades de la <xref:System.Windows.Media.RotateTransform> especificar el punto sobre el que se gira el objeto. Este punto central se expresa en el espacio de coordenadas del elemento que se transforma. De forma predeterminada, la rotación se aplica a (0,0), que es la esquina superior izquierda del objeto que transformar.  
  
 En el ejemplo siguiente se gira un <xref:System.Windows.Shapes.Polyline> objeto hacia la derecha 45 grados alrededor del punto (25,50).  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 La ilustración siguiente muestra los resultados de aplicar un <xref:System.Windows.Media.Transform> a los dos objetos.  
  
 ![Rotaciones de 45 grados con diferentes puntos centrales](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
Dos objetos que se giran 45 grados desde distintos centros de giro  
  
 El <xref:System.Windows.Shapes.Polyline> en los ejemplos anteriores es un <xref:System.Windows.UIElement>. Al aplicar un <xref:System.Windows.Media.Transform> a la <xref:System.Windows.UIElement.RenderTransform%2A> propiedad de un <xref:System.Windows.UIElement>, puede usar el <xref:System.Windows.UIElement.RenderTransformOrigin%2A> propiedad para especificar un origen para cada <xref:System.Windows.Media.Transform> que se aplican al elemento. Dado que el <xref:System.Windows.UIElement.RenderTransformOrigin%2A> propiedad usa coordenadas relativas, puede aplicar una transformación al centro del elemento incluso si no conoce su tamaño. Para obtener más información y para obtener un ejemplo, vea [especificar el origen de una transformación utilizando valores relativos](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).  
  
 Para ver el ejemplo completo, consulte [Ejemplo de transformaciones 2D](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.Transform>  
 [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
