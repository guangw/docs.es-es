---
title: "CREATEREF (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 489828cf-a335-4449-9360-b0d92eec5481
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# CREATEREF (Entity SQL)
Crea referencias a una entidad en un elemento entityset.  
  
## Sintaxis  
  
```  
  
CreateRef(entityset_identifier, row_typed_expression)  
```  
  
## Argumentos  
 `entityset_identifier`  
 Identificador de entityset, no un literal de cadena.  
  
 `row_typed_expression`  
 Expresión escrita por fila que corresponde a las propiedades de clave del tipo de entidad.  
  
## Comentarios  
 `row_typed_expression` debe ser estructuralmente equivalentes al tipo de clave de la entidad. Es decir, debe tener el mismo número y los mismos tipos de campos en el mismo orden que las claves de entidad.  
  
 En el ejemplo siguiente, Orders y BadOrders son ambos elementos entityset de tipo Order y se supone que Id es la propiedad de clave única de Order. El ejemplo muestra cómo se puede generar una referencia a una entidad en BadOrders. Observe que la referencia puede estar pendiente.  Es decir, la referencia puede no identificar realmente una entidad concreta. En esos casos, una operación `DEREF` en esa referencia devuelve un valor NULL.  
  
```  
select CreateRef(LOB.BadOrders, row(o.Id))   
from LOB.Orders as o   
```  
  
## Ejemplo  
 La consulta de Entity SQL siguiente utiliza el operador CREATEREF para crear las referencias a una entidad en un conjunto de entidades. La consulta se basa en el modelo AdventureWorks Sales. Para compilar y ejecutar esta consulta, siga estos pasos:  
  
1.  Siga el procedimiento de [Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#CREATEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#createref)]  
  
## Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)   
 [KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)   
 [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)