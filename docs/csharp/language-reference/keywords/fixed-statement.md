---
title: fixed (Instrucción, Referencia de C#)
ms.date: 05/10/2018
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
ms.openlocfilehash: 021fc3bd63922394bd70495bd4335b068fc51cdd
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44272441"
---
# <a name="fixed-statement-c-reference"></a>fixed (Instrucción, Referencia de C#)

La instrucción `fixed` evita que el recolector de elementos no utilizados reubique una variable móvil. La instrucción `fixed` solo se permite en un contexto de [unsafe](unsafe.md). `fixed` también puede usarse para crear [búferes de tamaño fijo](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).

La instrucción `fixed` establece un puntero a una variable administrada y "ancla" esa variable durante su ejecución. Los punteros a variables administradas móviles solo son útiles en un contexto `fixed`. Sin un contexto `fixed`, la recolección de elementos no utilizados podría reubicar las variables de forma impredecible. El compilador de C# solo permite asignar un puntero a una variable administrada en una instrucción `fixed`.

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#1)]

Puede inicializar un puntero mediante una matriz, una cadena, un búfer de tamaño fijo o la dirección de una variable. En el ejemplo siguiente se muestra el uso de direcciones, matrices y cadenas de variables. Para obtener más información sobre los búferes de tamaño fijo, consulte [Fixed Size Buffers](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md) (Búferes de tamaño fijo).

[!code-csharp[Initializing fixed size buffers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#2)]

A partir de C# 7.3, la instrucción `fixed` funciona en tipos adicionales más allá de matrices, cadenas, búferes de tamaño fijo o variables no administradas. Cualquier tipo que implemente un método denominado `GetPinnableReference` se puede anclar. `GetPinnableReference` debe devolver una variable `ref` a un tipo no administrado. Consulte el tema sobre [tipos de puntero](../../programming-guide/unsafe-code-pointers/pointer-types.md) para obtener más información. Los tipos de .NET <xref:System.Span%601?displayProperty=nameWithType> y <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> presentados en .NET Core 2.0 usan este patrón y se pueden anclar. Esto se muestra en el ejemplo siguiente:

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#FixedSpan)]

Si crea tipos que deben participar en este patrón, consulta <xref:System.Span%601.GetPinnableReference?displayProperty=nameWithType> para ver un ejemplo de implementación del patrón.

Es posible inicializar varios punteros en una sola instrucción si todos son del mismo tipo:

```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}
```

Para inicializar punteros de tipos diferentes, simplemente anide instrucciones `fixed`, como se muestra en el ejemplo siguiente.

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#3)]

Después de ejecutar el código de la instrucción, las variables ancladas se desanclan y quedan sujetas a la recolección de elementos no utilizados. Por lo tanto, no debe apuntar a esas variables fuera de la instrucción `fixed`. Las variables declaradas en la instrucción `fixed` se limitan a dicha instrucción, lo que simplifica esta tarea:

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
   ...
}
// ps and pd are no longer in scope here.
```

Los punteros inicializados en instrucciones `fixed` son variables de solo lectura. Si quiere modificar el valor del puntero, debe declarar una segunda variable de puntero y modificarla. La variable declarada en la instrucción `fixed` no se puede modificar:

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
    byte* pSourceCopy = ps;
    pSourceCopy++; // point to the next element.
    ps++; // invalid: cannot modify ps, as it is declared in the fixed statement.
}
```


En el modo no seguro, puede asignar memoria en la pila, en la que no está sujeta a la recolección de elementos no utilizados y, por tanto, no necesita anclarse. Para obtener más información, consulte [stackalloc](stackalloc.md).

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#4)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)  
- [Guía de programación de C#](../../programming-guide/index.md)  
- [Palabras clave de C#](index.md)  
- [unsafe](unsafe.md)  
- [Búferes de tamaño fijo](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
