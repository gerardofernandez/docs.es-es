---
title: Llamar a una propiedad o método mediante un nombre de cadena (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- passing operators [Visual Basic]
- strings [Visual Basic], passing new operators as
- objects [Visual Basic], setting properties
- setting properties, object properties at run time
- method calls [Visual Basic], strings
- methods [Visual Basic], calling with string names
- calling methods [Visual Basic], string names
- properties [Visual Basic], setting at run time
- CallByName function
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
ms.openlocfilehash: 76be426049489bb58e50878822c03fa5cd5cca8e
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2018
ms.locfileid: "42911651"
---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a>Llamar a una propiedad o método mediante un nombre de cadena (Visual Basic)
En la mayoría de los casos, puede detectar las propiedades y métodos de un objeto en tiempo de diseño y escribir código para controlarlos. Sin embargo, en algunos casos es posible que no sabe acerca de los métodos y propiedades de un objeto de antemano, o simplemente desea la flexibilidad de la habilitación de un usuario final especificar las propiedades o ejecutar métodos en tiempo de ejecución.  
  
## <a name="callbyname-function"></a>CallByName (función)  
 Considere, por ejemplo, una aplicación cliente que evalúa las expresiones escritas por el usuario pasando un operador a un componente COM. Supongamos que se agrega continuamente nuevas funciones para el componente que requieren nuevos operadores. Cuando se usan técnicas de acceso a objetos estándar, debe volver a compilar y distribuir la aplicación cliente antes de poder utilizar los operadores nuevos. Para evitar esto, puede usar el `CallByName` función para pasar los operadores nuevos como cadenas, sin modificar la aplicación.  
  
 El `CallByName` función le permite usar una cadena para especificar una propiedad o método en tiempo de ejecución. La firma para el `CallByName` función tiene este aspecto:  
  
 *Resultado* = `CallByName`(*objeto*, *NombreDeProcedimiento*, *CallType*, *argumentos*())  
  
 El primer argumento, *objeto*, toma el nombre del objeto que desea actuar. El *NombreDeProcedimiento* argumento toma una cadena que contiene el nombre del procedimiento que se debe invocar método o propiedad. El *CallType* argumento toma una constante que representa el tipo de procedimiento que debe invocarse: un método (`Microsoft.VisualBasic.CallType.Method`), una lectura de propiedad (`Microsoft.VisualBasic.CallType.Get`), o un conjunto de propiedades (`Microsoft.VisualBasic.CallType.Set`). El *argumentos* argumento, que es opcional, toma una matriz de tipo `Object` que contiene los argumentos para el procedimiento.  
  
 Puede usar `CallByName` con clases en la solución actual, pero se suele utilizar para tener acceso a objetos COM o los objetos de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] ensamblados.  
  
 Supongamos que se agrega una referencia a un ensamblado que contiene una clase denominada `MathClass`, que tiene una función nueva denominada `SquareRoot`, tal y como se muestra en el código siguiente:  
  
 [!code-vb[VbVbalrOOP#53](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_1.vb)]  
  
 La aplicación podría utilizar controles de cuadro de texto al control de qué método se llamará y sus argumentos. Por ejemplo, si `TextBox1` contiene la expresión que se va a evaluar, y `TextBox2` es usa para escribir el nombre de la función, puede utilizar el siguiente código para invocar la `SquareRoot` función en la expresión de `TextBox1`:  
  
 [!code-vb[VbVbalrOOP#54](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_2.vb)]  
  
 Si escribe "64" en `TextBox1`, "SquareRoot" en `TextBox2`y, a continuación, llame a la `CallMath` procedimiento, la raíz cuadrada del número de `TextBox1` se evalúa. El código en el ejemplo se invoca el `SquareRoot` función (que toma una cadena que contiene la expresión que se evalúa como un argumento necesario) y devuelve "8" en `TextBox1` (la raíz cuadrada de 64). Por supuesto, si el usuario escribe una cadena no válida en `TextBox2`si la cadena contiene el nombre de una propiedad en lugar de un método, o si el método tiene un argumento necesario adicional, se produce un error de tiempo de ejecución. Tiene que agregar código de control de errores sólido cuando usas `CallByName` para anticipar estos u otros errores.  
  
> [!NOTE]
>  Mientras el `CallByName` función puede resultar útil en algunos casos, debe sopesar su utilidad frente a las implicaciones de rendimiento: uso de `CallByName` invocar un procedimiento es ligeramente más lenta que una llamada enlazada en tiempo de ejecución. Si invoca una función que se llama varias veces, por ejemplo, dentro de un bucle, `CallByName` puede tener un efecto grave en el rendimiento.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>  
 [Determinación del tipo de objeto](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)
