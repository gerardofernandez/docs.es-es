---
title: Delegados y expresiones lambda
description: Obtenga información sobre cómo los delegados definen un tipo, que especifica una firma de método determinada, que se puede llamar directamente o pasar a otro método y llamar.
author: richlander
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: fe2e4b4c-6483-4106-a4b4-a33e2e306591
ms.openlocfilehash: f8184b87fc62f378fe72138733f87de924da60f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33574570"
---
# <a name="delegates-and-lambdas"></a>Delegados y expresiones lambda

Los delegados definen un tipo, que especifica una firma de método concreta. Se puede asignar un método (estático o de instancia) que satisfaga esta firma a una variable de ese tipo y luego llamarlo directamente (con los argumentos adecuados) o pasarlo como argumento a otro método y después llamarlo. El siguiente ejemplo muestra el uso de delegados.

```csharp
public class Program
{

  public delegate string Reverse(string s);

  static string ReverseString(string s)
  {
      return new string(s.Reverse().ToArray());
  }

  static void Main(string[] args)
  {
      Reverse rev = ReverseString;

      Console.WriteLine(rev("a string"));
  }
}
```

*   En la línea 4 se crea un tipo delegado de una firma determinada, en este caso un método que toma un parámetro de cadena y luego devuelve un parámetro de cadena.
*   En la línea 6 se define la implementación del delegado al proporcionar un método que tiene exactamente la misma firma.
*   En la línea 13 se asigna el método a un tipo que se ajusta al delegado `Reverse`.
*   Por último, en la línea 15 se invoca al delegado al pasar una cadena que se va a invertir.

Para simplificar el proceso de desarrollo, .NET incluye un conjunto de tipos delegados que los programadores pueden volver a usar para no tener que crear nuevos tipos. Estos son `Func<>`, `Action<>` y `Predicate<>`, y se pueden usar en varias ubicaciones de las API de .NET sin necesidad de definir nuevos tipos delegados. Por supuesto, hay algunas diferencias entre los tres, como verá en sus firmas, que principalmente tienen que ver con la forma en que deberían emplearse:

*   `Action<>` se usa cuando es necesario realizar una acción mediante los argumentos del delegado.
*   `Func<>` se usa normalmente cuando se tiene una transformación a mano; es decir, cuando se necesita transformar los argumentos del delegado en un resultado diferente. Las proyecciones son un buen ejemplo de esto.
*   `Predicate<>` se usa cuando es necesario determinar si el argumento cumple la condición del delegado. También puede escribirse como `Func<T, bool>`.

Ahora podemos tomar el ejemplo anterior y volver a escribirlo mediante el delegado `Func<>` en lugar de un tipo personalizado. El programa seguirá ejecutándose de la misma forma.

```csharp
public class Program
{

  static string ReverseString(string s)
  {
      return new string(s.Reverse().ToArray());
  }

  static void Main(string[] args)
  {
      Func<string, string> rev = ReverseString;

      Console.WriteLine(rev("a string"));
  }
}
```

En este ejemplo sencillo, tener un método definido fuera del método Main() parece un poco superfluo. Es por ello que .NET Framework 2.0 presentó el concepto de **delegados anónimos**. Con ellos es posible crear delegados "insertados" sin tener que especificar ningún otro tipo o método. Simplemente se inserta la definición del delegado allí donde se necesita.

Para que vea un ejemplo, se va a activar y a usar el delegado anónimo para filtrar una lista de números pares e imprimirlos en la consola.

```csharp
public class Program
{

  public static void Main(string[] args)
  {
    List<int> list = new List<int>();

    for (int i = 1; i <= 100; i++)
    {
        list.Add(i);
    }

    List<int> result = list.FindAll(
      delegate(int no)
      {
          return (no%2 == 0);
      }
    );

    foreach (var item in result)
    {
        Console.WriteLine(item);
    }
  }
}
```

Observe las líneas resaltadas. Como puede ver, el cuerpo del delegado es simplemente un conjunto de expresiones, como cualquier otro delegado. Pero en lugar de ser una definición independiente, se ha introducido _ad hoc_ en la llamada al método `FindAll()` del tipo `List<T>`.

Pero incluso con este enfoque, sigue habiendo mucho código del que es posible deshacerse. Aquí es donde entran en juego las **expresiones lambda**.

Las expresiones lambda, o las "lambda" para abreviar, se presentaron en C# 3.0 como uno de los bloques de creación fundamentales de Language Integrated Query (LINQ). Constituyen una sintaxis más cómoda para el uso de delegados. Declaran una firma y un cuerpo de método, pero no tienen una identidad formal propia, a menos que se asignen a un delegado. A diferencia de los delegados, se pueden asignar directamente como lado izquierdo del registro de eventos o en distintas cláusulas y métodos de Linq.

Puesto que una expresión lambda es solo otra forma de especificar un delegado, debería ser posible volver a escribir el ejemplo anterior para usar una expresión lambda en lugar de un delegado anónimo.

```csharp
public class Program
{

  public static void Main(string[] args)
  {
    List<int> list = new List<int>();

    for (int i = 1; i <= 100; i++)
    {
        list.Add(i);
    }

    List<int> result = list.FindAll(i => i % 2 == 0);

    foreach (var item in result)
    {
        Console.WriteLine(item);
    }
  }
}
```

Si echa un vistazo a las líneas resaltadas, puede ver el aspecto de una expresión lambda. Una vez más, se trata solo de una sintaxis **muy** cómoda para usar delegados, así que lo que sucede en segundo plano es similar a lo que ocurre con el delegado anónimo.

De nuevo, las expresiones lambda son solo delegados, lo que significa que se pueden usar como controlador de eventos sin problemas, como se muestra en el siguiente fragmento de código.

```csharp
public MainWindow()
{
    InitializeComponent();

    Loaded += (o, e) =>
    {
        this.Title = "Loaded";
    };
}
```

## <a name="further-reading-and-resources"></a>Más información y recursos

*   [Delegados](../../docs/csharp/programming-guide/delegates/index.md)
*   [Funciones anónimas](../../docs/csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)
*   [Expresiones lambda](../../docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
