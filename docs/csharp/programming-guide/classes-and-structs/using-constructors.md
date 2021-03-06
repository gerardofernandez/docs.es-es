---
title: Utilizar constructores (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], about constructors
ms.assetid: 464253b2-fd5d-469a-836d-df0fdf2a43f7
ms.openlocfilehash: b19676b2549bbb54af7fb1d72ff0e98352c61383
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43529025"
---
# <a name="using-constructors-c-programming-guide"></a>Utilizar constructores (Guía de programación de C#)
Cuando se crea una [class](../../../csharp/language-reference/keywords/class.md) o un [struct](../../../csharp/language-reference/keywords/struct.md), se llama a su constructor. Los constructores tienen el mismo nombre que la class o el struct y suelen inicializar los miembros de datos del nuevo objeto.  
  
 En el ejemplo siguiente, una clase denominada `Taxi` se define mediante un constructor simple. Luego, se crea una instancia de la clase con el operador [new](../../../csharp/language-reference/keywords/new.md). El constructor `Taxi` se invoca con el operador `new` inmediatamente después de asignar memoria para el nuevo objeto.  
  
 [!code-csharp[csProgGuideObjects#53](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_1.cs)]  
  
 Un constructor que no toma ningún parámetro se denomina *constructor predeterminado*. Los constructores predeterminados se invocan cada vez que se crea una instancia de un objeto mediante el operador `new` y no se especifica ningún argumento en `new`. Para obtener más información, vea [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md) (Constructores de instancias [Guía de programación de C#]).  
  
 A menos que la clase sea [static](../../../csharp/language-reference/keywords/static.md), las clases sin constructores tienen un constructor público predeterminado por el compilador de C# con el fin de habilitar la creación de instancias de clase. Para más información, vea [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
 Puede impedir que se cree una instancia de una clase convirtiendo el constructor en privado, de la manera siguiente:  
  
 [!code-csharp[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_2.cs)]  
  
 Para obtener más información, vea [Private Constructors](../../../csharp/programming-guide/classes-and-structs/private-constructors.md) (Constructores privados [Guía de programación de C#]).  
  
 Los constructores de tipos [struct](../../../csharp/language-reference/keywords/struct.md) son similares a los constructores de clases, pero `structs` no puede contener un constructor predeterminado explícito porque el compilador proporciona uno automáticamente. Este constructor inicializa cada campo del `struct` en los valores predeterminados. Para obtener más información, vea [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md) (Tabla de valores predeterminados [Referencia de C#]). Pero este constructor predeterminado solo se invoca si las instancias de `struct` se crean con `new`. Por ejemplo, este código usa el constructor predeterminado para <xref:System.Int32>, por lo que se tiene la certeza de que el entero se inicializa:  
  
```csharp  
int i = new int();  
Console.WriteLine(i);  
```  
  
 Si bien, el siguiente código genera un error del compilador porque no usa `new` y porque intenta usar un objeto que no se ha inicializado:  
  
```  
int i;  
Console.WriteLine(i);  
```  
  
 También puede inicializar o asignar los objetos basados en `structs` (incluidos todos los tipos numéricos integrados) y luego usarlos como en el ejemplo siguiente:  
  
```  
int a = 44;  // Initialize the value type...  
int b;  
b = 33;      // Or assign it before using it.  
Console.WriteLine("{0}, {1}", a, b);  
```  
  
 Por lo que no es necesario llamar al constructor predeterminado para un tipo de valor.  
  
 Tanto las clases como los `structs` pueden definir constructores que toman parámetros. Los constructores que toman parámetros deben llamarse mediante una instrucción `new` o [base](../../../csharp/language-reference/keywords/base.md). Las clases y `structs` también pueden definir varios constructores y no es necesario definir un constructor predeterminado. Por ejemplo:  
  
 [!code-csharp[csProgGuideObjects#54](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_3.cs)]  
  
 Esta clase se puede crear mediante cualquiera de las siguientes instrucciones:  
  
 [!code-csharp[csProgGuideObjects#55](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_4.cs)]  
  
 Un constructor puede usar la palabra clave `base` para llamar al constructor de una clase base. Por ejemplo:  
  
 [!code-csharp[csProgGuideObjects#56](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_5.cs)]  
  
 En este ejemplo, se llama al constructor de la clase base antes de ejecutar el bloque del constructor. La palabra clave `base` puede usarse con o sin parámetros. Los parámetros del constructor se pueden usar como parámetros en `base` o como parte de una expresión. Para obtener más información, vea [base](../../../csharp/language-reference/keywords/base.md).  
  
 En una clase derivada, si un constructor de clase base no se llama explícitamente con la palabra clave `base`, se llama implícitamente al constructor predeterminado, si hay alguno. Esto significa que las siguientes declaraciones del constructor son en efecto iguales:  
  
 [!code-csharp[csProgGuideObjects#58](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_6.cs)]  
  
 [!code-csharp[csProgGuideObjects#57](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_7.cs)]  
  
 Si una clase base no proporciona un constructor predeterminado, la clase derivada debe realizar una llamada explícita a un constructor base mediante `base`.  
  
 Un constructor puede invocar otro constructor en el mismo objeto mediante la palabra clave [this](../../../csharp/language-reference/keywords/this.md). Igual que `base`, `this` puede usarse con o sin parámetros. Además, los parámetros del constructor están disponibles como parámetros en `this` o como parte de una expresión. Por ejemplo, el segundo constructor del ejemplo anterior se puede reescribir con `this`:  
  
 [!code-csharp[csProgGuideObjects#59](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_8.cs)]  
  
 El uso de la palabra clave `this` en el ejemplo anterior llama a este constructor:  
  
 [!code-csharp[csProgGuideObjects#60](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_9.cs)]  
  
 Los constructores se pueden marcar como [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md) o [private protected](../../../csharp/language-reference/keywords/private-protected.md). Estos modificadores de acceso definen cómo los usuarios de la clase pueden construir la clase. Para obtener más información, consulte [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Un constructor puede declararse estático mediante la palabra clave [static](../../../csharp/language-reference/keywords/static.md). Los constructores estáticos se llaman automáticamente, inmediatamente antes de acceder a los campos estáticos y, por lo general, se usan para inicializar miembros de clase estática. Para obtener más información, vea [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md) (Constructores estáticos [Guía de programación de C#]).  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
- [Finalizadores](../../../csharp/programming-guide/classes-and-structs/destructors.md)
