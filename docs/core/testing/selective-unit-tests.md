---
title: Ejecución de pruebas unitarias selectivas
description: Muestra cómo usar una expresión de filtro para ejecutar pruebas unitarias selectivas con el comando de prueba de dotnet.
author: smadala
ms.author: mairaw
ms.date: 03/22/2017
ms.openlocfilehash: 428e31014f5d8d487deb7c4b4317ebcef13c294d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517225"
---
# <a name="running-selective-unit-tests"></a>Ejecución de pruebas unitarias selectivas

En los siguientes ejemplos, se utiliza `dotnet test`. Si está usando `vstest.console.exe`, reemplace `--filter ` por `--testcasefilter:`.

## <a name="mstest"></a>MSTest

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;

namespace MSTestNamespace
{
    [TestClass]
    public class UnitTest1
    {
        [TestCategory("CategoryA")]
        [Priority(1)]
        [TestMethod]
        public void TestMethod1()
        {
        }

        [Priority(2)]
        [TestMethod]
        public void TestMethod2()
        {
        }
    }
}
```

| Expresión | Resultado |
| ---------- | ------ |
| `dotnet test --filter Method` | Ejecuta pruebas cuyo `FullyQualifiedName` contenga `Method`. Disponible en `vstest 15.1+`. |
| `dotnet test --filter Name~TestMethod1` | Ejecuta pruebas cuyo nombre contenga `TestMethod1`. |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | Ejecuta pruebas que están en la clase `MSTestNamespace.UnitTest1`.<br>**Nota:** El valor `ClassName` debe tener un espacio de nombres, por lo que `ClassName=UnitTest1` no funcionará. |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | Ejecuta todas las pruebas excepto `MSTestNamespace.UnitTest1.TestMethod1`. |
| `dotnet test --filter TestCategory=CategoryA` | Ejecuta pruebas anotadas con `[TestCategory("CategoryA")]`. |
| `dotnet test --filter Priority=2` | Ejecuta pruebas anotadas con `[Priority(2)]`.<br>

**Usar operadores condicionales | y &amp;**

| Expresión | Resultado |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | Ejecuta pruebas que tienen `UnitTest1` en `FullyQualifiedName` **o** en las que `TestCategory` es `CategoryA`. |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | Ejecuta pruebas que tienen `UnitTest1` en `FullyQualifiedName` **y** en las que `TestCategory` es `CategoryA`. |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | Ejecuta pruebas que tienen `FullyQualifiedName` con `UnitTest1` **y** en las que `TestCategory` es `CategoryA` **o** en las que `Priority` es 1. |

## <a name="xunit"></a>xUnit

```csharp
using Xunit;

namespace XUnitNamespace
{
    public class TestClass1
    {
        [Trait("Category", "CategoryA")]
        [Trait("Priority", "1")]
        [Fact]
        public void Test1()
        {
        }

        [Trait("Priority", "2")]
        [Fact]
        public void Test2()
        {
        }
    }
}
```

| Expresión | Resultado |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | Ejecuta solo una prueba, `XUnitNamespace.TestClass1.Test1`. |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | Ejecuta todas las pruebas excepto `XUnitNamespace.TestClass1.Test1`. |
| `dotnet test --filter DisplayName~TestClass1` | Ejecuta pruebas cuyo nombre para mostrar contenga `TestClass1`. |

En el ejemplo de código, los rasgos definidos con claves `Category` y `Priority` pueden usarse para filtrar.

| Expresión | Resultado |
| ---------- | ------ |
| `dotnet test --filter XUnit` | Ejecuta pruebas cuyo `FullyQualifiedName` contenga `XUnit`.  Disponible en `vstest 15.1+`. |
| `dotnet test --filter Category=CategoryA` | Ejecuta las pruebas que tienen `[Trait("Category", "CategoryA")]`. |

**Usar operadores condicionales | y &amp;**

| Expresión | Resultado |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | Ejecuta pruebas que tienen `TestClass1` en `FullyQualifiedName` **o** en las que `Category` es `CategoryA`. |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | Ejecuta pruebas que tienen `TestClass1` en `FullyQualifiedName` **y** en las que `Category` es `CategoryA`. |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | Ejecuta pruebas que tienen `FullyQualifiedName` con `TestClass1` **y** en las que `Category` es `CategoryA` **o** en las que `Priority` es 1. |

## <a name="nunit"></a>NUnit

```csharp
using NUnit.Framework;

namespace NUnitNamespace
{
    public class UnitTest1
    {
        [Category("CategoryA")]
        [Property("Priority", 1)]
        [Test]
        public void TestMethod1()
        {
        }

        [Property("Priority", 2)]
        [Test]
        public void TestMethod2()
        {
        }
    }
}
```

| Expresión | Resultado |
| ---------- | ------ |
| `dotnet test --filter Method` | Ejecuta pruebas cuyo `FullyQualifiedName` contenga `Method`. Disponible en `vstest 15.1+`. |
| `dotnet test --filter Name~TestMethod1` | Ejecuta pruebas cuyo nombre contenga `TestMethod1`. |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | Ejecuta pruebas que están en la clase `NUnitNamespace.UnitTest1`.<br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | Ejecuta todas las pruebas excepto `NUnitNamespace.UnitTest1.TestMethod1`. |
| `dotnet test --filter TestCategory=CategoryA` | Ejecuta pruebas anotadas con `[Category("CategoryA")]`. |
| `dotnet test --filter Priority=2` | Ejecuta pruebas anotadas con `[Priority(2)]`.<br>

**Usar operadores condicionales | y &amp;**

| Expresión | Resultado |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | Ejecuta pruebas que tienen `UnitTest1` en `FullyQualifiedName` **o** en las que `TestCategory` es `CategoryA`. |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | Ejecuta pruebas que tienen `UnitTest1` en `FullyQualifiedName` **y** en las que `TestCategory` es `CategoryA`. |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | Ejecuta pruebas que tienen `FullyQualifiedName` con `UnitTest1` **y** en las que `TestCategory` es `CategoryA` **o** en las que `Priority` es 1. |
