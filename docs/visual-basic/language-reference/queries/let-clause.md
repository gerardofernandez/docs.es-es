---
title: Let (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: 34c0fd239d9e08dab4a107cb8447941e7ab3ecbe
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516768"
---
# <a name="let-clause-visual-basic"></a>Let (Cláusula, Visual Basic)
Calcula un valor y lo asigna a una nueva variable dentro de la consulta.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`variable`|Requerido. Un alias que se puede usar para hacer referencia a los resultados de la expresión proporcionada.|  
|`expression`|Requerido. Una expresión que se evalúa y se asigna a la variable especificada.|  
  
## <a name="remarks"></a>Comentarios  
 El `Let` cláusula permite calcular valores para cada resultado de la consulta y hacer referencia a ellos mediante un alias. El alias puede usarse en otras cláusulas, como la `Where` cláusula. El `Let` cláusula le permite crear una instrucción de consulta que es más fácil de leer porque se puede especificar un alias para una cláusula de expresión incluida en la consulta y sustituye el alias cada vez que se utiliza la cláusula de expresión.  
  
 Puede incluir cualquier número de `variable` y `expression` asignaciones en el `Let` cláusula. Separe cada asignación con una coma (,).  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de código utiliza el `Let` cláusula para calcular un 10 por ciento de descuento en productos.  
  
 [!code-vb[VbSimpleQuerySamples#16](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/let-clause_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Consultas](../../../visual-basic/language-reference/queries/index.md)  
 [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Where (cláusula)](../../../visual-basic/language-reference/queries/where-clause.md)
