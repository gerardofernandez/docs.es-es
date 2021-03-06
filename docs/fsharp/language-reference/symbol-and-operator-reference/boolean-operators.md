---
title: Operadores booleanos (F#)
description: 'Obtenga información sobre los operadores booleanos que están disponibles en el lenguaje de programación F #.'
ms.date: 05/16/2016
ms.openlocfilehash: faa181090efa7c4064a30b42d83afa4888e98b82
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2018
ms.locfileid: "44364358"
---
# <a name="boolean-operators"></a>Operadores booleanos

En este tema se describe la compatibilidad con los operadores booleanos en el lenguaje F #.

## <a name="summary-of-boolean-operators"></a>Resumen de operadores booleanos

En la tabla siguiente se resume los operadores booleanos que están disponibles en el lenguaje F #. Es el único tipo admitido por estos operadores el `bool` tipo.

|Operador|Descripción|
|--------|-----------|
|`not`|Negación booleana|
|<code>&#124;&#124;</code>|OR booleano|
|`&&`|AND Boolean|

Realizan el booleano operadores AND y OR *la evaluación de cortocircuito*, es decir, evalúa la expresión a la derecha del operador solo cuando sea necesario determinar el resultado global de la expresión. La segunda expresión de la `&&` operador se evalúa solo si la primera expresión se evalúa como `true`; la segunda expresión de la `||` operador se evalúa solo si la primera expresión se evalúa como `false`.

## <a name="see-also"></a>Vea también

- [Operadores bit a bit](bitwise-operators.md)
- [Operadores aritméticos](arithmetic-operators.md)
- [Referencia de símbolos y operadores](index.md)
