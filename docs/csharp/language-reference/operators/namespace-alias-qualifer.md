---
title: ':: (operador) (Referencia de C#)'
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 077d5835b372897cbe797385271effc5d00bf6e3
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43525661"
---
# <a name="-operator-c-reference"></a>:: (operador) (Referencia de C#)
El calificador de alias de espacio de nombres (`::`) se usa para buscar identificadores. Siempre se coloca entre dos identificadores, como en este ejemplo:  
  
 [!code-csharp[csRefOperators#27](../../../csharp/language-reference/operators/codesnippet/CSharp/namespace-alias-qualifer_1.cs)]  

El operador `::` también puede utilizarse con una *directiva de alias using*:

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a>Comentarios  
 El calificador de alias de espacio de nombres puede ser `global`. Este invoca una búsqueda del espacio de nombres global, en lugar de un espacio de nombres con alias.  
  
## <a name="for-more-information"></a>Para obtener más información  
 Para obtener un ejemplo de cómo usar el operador `::`, vea la siguiente sección:  
  
-   [Cómo: Utilizar el alias del espacio de nombres global](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Operadores de C#](../../../csharp/language-reference/operators/index.md)  
- [Palabras clave del espacio de nombres](../../../csharp/language-reference/keywords/namespace-keywords.md)  
- [. !](../../../csharp/language-reference/operators/member-access-operator.md)  
- [extern alias](../../../csharp/language-reference/keywords/extern-alias.md)
