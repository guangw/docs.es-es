---
title: Narrowing (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
ms.openlocfilehash: 54a18d0cc10e42829b48b0ef75bb77ab0d47b45f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="narrowing-visual-basic"></a>Narrowing (Visual Basic)
Indica que un operador de conversión (`CType`) convierte una clase o estructura a un tipo que no pueda mantener algunos de los valores posibles de la clase o estructura original.  
  
## <a name="converting-with-the-narrowing-keyword"></a>Convertir con la palabra clave Narrowing  
 El procedimiento de conversión debe especificar `Public Shared` además `Narrowing`.  
  
 Conversiones de restricción no siempre sea correcta en tiempo de ejecución y pueden producir errores o provocar la pérdida de datos. Algunos ejemplos son `Long` a `Integer`, `String` a `Date`y un tipo base para un tipo derivado. Esta última conversión es de restricción porque el tipo base no puede contener a todos los miembros del tipo derivado y, por tanto, no es una instancia del tipo derivado.  
  
 Si `Option Strict` es `On`, el código usado debe usar `CType` para todas las conversiones de restricción.  
  
 El `Narrowing` palabra clave se puede usar en este contexto:  
  
 [Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## <a name="see-also"></a>Vea también  
 [Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)  
 [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [Función CType](../../../visual-basic/language-reference/functions/ctype-function.md)  
 [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)
