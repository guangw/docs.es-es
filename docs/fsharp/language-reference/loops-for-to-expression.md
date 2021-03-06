---
title: 'Bucles: expresión for...to (F#)'
description: 'Vea cómo la estructura de F # for.. en expresión se usa para iterar en un bucle en un intervalo de valores de una variable de bucle.'
ms.date: 05/16/2016
ms.openlocfilehash: 841c7d557abc11e0253cb87ab8081cc77671b44b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="loops-forto-expression"></a>Bucles: expresión for...to

El `for...to` expresión se usa para iterar en un bucle en un intervalo de valores de una variable de bucle.


## <a name="syntax"></a>Sintaxis

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a>Comentarios
El tipo del identificador se deduce del tipo de la *iniciar* y *finalizar* expresiones. Tipos de estas expresiones deben ser enteros de 32 bits.

Aunque técnicamente es una expresión, `for...to` más parecido a una instrucción en un lenguaje de programación imperativo tradicional. El tipo de valor devuelto para la *cuerpo-expression* debe ser `unit`. Los ejemplos siguientes muestran varios usos de la `for...to` expresión.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

La salida del código anterior es la siguiente.

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)

[Bucles: expresión `for...in`](loops-for-in-expression.md)

[Bucles: expresión `while...do`](loops-while-do-expression.md)
