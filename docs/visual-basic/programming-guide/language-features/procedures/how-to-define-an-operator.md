---
title: 'Cómo: Definir un operador (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- operator procedures [Visual Basic], about operator procedures
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: d4b0e253-092a-4e6e-9fe2-01f562140a29
ms.openlocfilehash: c759ebf38ab0727aeada218d288b5ac01e3ecd03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-define-an-operator-visual-basic"></a>Cómo: Definir un operador (Visual Basic)
Si ha definido una clase o estructura, puede definir el comportamiento de un operador estándar (como `*`, `<>`, o `And`) cuando uno o ambos de los operandos es del tipo de la clase o estructura.  
  
 Definir el operador estándar como un procedimiento de operador dentro de la clase o estructura. Todos los procedimientos de operador deben ser `Public` `Shared`.  
  
 Definir un operador en una clase o estructura también se denomina *sobrecarga* el operador.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define la `+` operador para una estructura denominada `height`. La estructura utiliza altos que se miden en pies y pulgadas. Una *pulgadas* es 2,54 centímetros y uno *foot* es de 12 pulgadas. Para garantizar que los valores normalizados (pulgadas < 12.0), el constructor realiza *módulo* 12 aritméticos. El `+` operador utiliza el constructor para generar valores normalizados.  
  
 [!code-vb[VbVbcnProcedures#25](./codesnippet/VisualBasic/how-to-define-an-operator_1.vb)]  
  
 Puede probar la estructura `height` con el código siguiente.  
  
 [!code-vb[VbVbcnProcedures#26](./codesnippet/VisualBasic/how-to-define-an-operator_2.vb)]  
  
 Para obtener más información y ejemplos, vea [Operator Overloading in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703) (Sobrecarga de operadores en Visual Basic 2005).  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos de operadores](./operator-procedures.md)  
 [Definir un operador de conversión](./how-to-define-a-conversion-operator.md)  
 [Llamar a un procedimiento de operador](./how-to-call-an-operator-procedure.md)  
 [Utilizar una clase que define operadores](./how-to-use-a-class-that-defines-operators.md)  
 [Operator (instrucción)](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Structure (instrucción)](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Declarar una estructura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Mod (operador)](../../../../visual-basic/language-reference/operators/mod-operator.md)
