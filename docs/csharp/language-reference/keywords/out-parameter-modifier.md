---
title: Modificador del parámetro out (Referencia de C#)
ms.date: 03/06/2018
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.openlocfilehash: bc31ae202ccbfee467dc0f6fa2cf515c751825ed
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44201314"
---
# <a name="out-parameter-modifier-c-reference"></a>Modificador del parámetro out (Referencia de C#)
La palabra clave `out` hace que los argumentos se pasen por referencia. Esto es como la palabra clave [ref](ref.md), salvo que `ref` requiere que se inicialice la variable antes de pasarla. También es como la palabra clave [in](in-parameter-modifier.md), salvo que `in` no permite que el método llamado modifique el valor del argumento. Para usar un parámetro `out`, tanto la definición de método como el método de llamada deben utilizar explícitamente la palabra clave `out`. Por ejemplo:  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#1)]  

> [!NOTE] 
> La palabra clave `out` también puede usarse con un parámetro de tipo genérico para especificar que el parámetro de tipo es covariante. Para obtener más información sobre el uso de la palabra clave `out` en este contexto, vea [Out (Modificador genérico)](out-generic-modifier.md).
  
Las variables que se han pasado como argumentos `out` no tienen que inicializarse antes de pasarse en una llamada al método. En cambio, se necesita el método que se ha llamado para asignar un valor antes de que el método se devuelva.  
  
Aunque las palabras clave `in`, `ref` y `out` causan un comportamiento diferente en tiempo de ejecución, no se consideran parte de la signatura del método en tiempo de compilación. Por lo tanto, los métodos no pueden sobrecargarse si la única diferencia es que un método toma un argumento `ref` o `in` y el otro toma un argumento `out`. Por ejemplo, el código siguiente, no se compilará:  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
En cambio, la sobrecarga es legal si un método toma un argumento `ref`, `in` o `out` y el otro no tiene ninguno de estos modificadores, como se muestra aquí:  
  
[!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#2)]  

El compilador elige la mejor sobrecarga haciendo coincidir los modificadores de parámetro del sitio de llamada con los usados en la llamada de método.
 
Las propiedades no son variables y, por tanto, no pueden pasarse como parámetros `out`.
  
Las palabras clave `in`, `ref` y `out` no pueden usarse para estos tipos de métodos:  
  
-   Métodos asincrónicos, que se definen mediante el uso del modificador [async](../../../csharp/language-reference/keywords/async.md).  
  
-   Métodos de iterador, que incluyen una instrucción [yield return](../../../csharp/language-reference/keywords/yield.md) o `yield break`.  

## <a name="declaring-out-arguments"></a>Declarar argumentos `out`   

 Declarar un método con argumentos `out` resulta útil cuando quiere que devuelva varios valores. En el ejemplo siguiente, se utiliza `out` para devolver tres variables con una única llamada al método. Tenga en cuenta que el tercer argumento se asigna a null. Esto permite que los métodos devuelvan valores opcionalmente.  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#3)]  

 El [patrón Try](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) implica la devolución de `bool` para indicar si una operación se ha realizado correcta o incorrectamente, y la devolución del valor que ha generado la operación en un argumento `out`. Varios métodos de análisis, como el método [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)), usan este patrón.
   
## <a name="calling-a-method-with-an-out-argument"></a>Llamar a un método con un argumento `out`

En C# 6 y versiones anteriores, debe declarar una variable en una instrucción independiente antes de pasarla como un argumento `out`. En el ejemplo siguiente se declara una variable denominada `number` antes de que se pase al método [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)), que intenta convertir una cadena en un número.

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#4)]  

A partir de C# 7.0, puede declarar la variable `out` en la lista de argumentos de la llamada al método, en lugar de en una declaración de variable independiente. Esto genera un código legible más compacto y, además, evita que asigne un valor a la variable antes de la llamada al método de manera involuntaria. El ejemplo siguiente es como el ejemplo anterior, excepto que define la variable `number` en la llamada al método [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)).

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#5)]  
   
En el ejemplo anterior, la variable `number` está fuertemente tipada como `int`. También puede declarar una variable local con tipo implícito como se muestra en el siguiente ejemplo.

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#6)]  
   
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
- [Parámetros de métodos](../../../csharp/language-reference/keywords/method-parameters.md)
