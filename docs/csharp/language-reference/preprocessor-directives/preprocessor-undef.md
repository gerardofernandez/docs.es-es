---
title: '#undef (Referencia de C#)'
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: 3957d58f61e51fab01618f5e1146be9cd0da58fd
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44269307"
---
# <a name="undef-c-reference"></a>#undef (Referencia de C#)
`#undef` le permite anular la definición de un símbolo, de tal forma que, si se usa como la expresión en una directiva [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), la expresión se evaluará como `false`.  
  
 Un símbolo se puede definir con la directiva [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) o la opción del compilador [-define](../../../csharp/language-reference/compiler-options/define-compiler-option.md). La directiva `#undef` debe aparecer en el archivo antes de que use cualquier instrucción que tampoco sea una directiva.  
  
## <a name="example"></a>Ejemplo  

```csharp
// preprocessor_undef.cs  
// compile with: /d:DEBUG  
#undef DEBUG  
using System;  
class MyClass
{  
    static void Main()
    {  
#if DEBUG  
        Console.WriteLine("DEBUG is defined");  
#else  
        Console.WriteLine("DEBUG is not defined");  
#endif  
    }  
}  
```

**DEBUG está sin definirse**

## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Directivas de preprocesador de C#](../../../csharp/language-reference/preprocessor-directives/index.md)
