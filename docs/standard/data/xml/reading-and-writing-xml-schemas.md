---
title: Lectura y escritura de esquemas XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: b5757c4a-ea59-467e-ac62-be2bfe24eb77
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 241ff40448c3dca2846f9e420dc7df41427dc79d
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44266896"
---
# <a name="reading-and-writing-xml-schemas"></a>Lectura y escritura de esquemas XML
La API del Modelo de objetos de esquema (SOM) se puede utilizar para leer y escribir esquemas del lenguaje de definición de esquemas XML (XSD) desde archivos u otros orígenes y compilar esquemas XML en memoria, utilizando las clases del espacio de nombres <xref:System.Xml.Schema?displayProperty=nameWithType> que se asignan a las estructuras definidas en la recomendación de esquemas XML del W3C (World Wide Web Consortium).  
  
## <a name="reading-and-writing-xml-schemas"></a>Lectura y escritura de esquemas XML  
 La clase <xref:System.Xml.Schema.XmlSchema> incluye los métodos <xref:System.Xml.Schema.XmlSchema.Read%2A> y <xref:System.Xml.Schema.XmlSchema.Write%2A> para leer y escribir esquemas XML. El método <xref:System.Xml.Schema.XmlSchema.Read%2A> devuelve un objeto <xref:System.Xml.Schema.XmlSchema> que representa el esquema XML y toma un parámetro <xref:System.Xml.Schema.ValidationEventHandler> opcional para controlar los errores y advertencias de validación que se encuentran al leer un esquema XML.  
  
 El método <xref:System.Xml.Schema.XmlSchema.Write%2A> escribe esquemas XML para los objetos <xref:System.IO.Stream>, <xref:System.IO.TextWriter> y <xref:System.Xml.XmlWriter> y puede tomar un objeto <xref:System.Xml.XmlNamespaceManager> opcional como parámetro. Se utiliza un <xref:System.Xml.XmlNamespaceManager> para controlar los espacios de nombres que se encuentran en un esquema XML. Para más información sobre la clase <xref:System.Xml.XmlNamespaceManager>, vea [Administrar espacios de nombres en un documento XML](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md).  
  
 El siguiente código de ejemplo ilustra la lectura y escritura de esquemas XML desde un archivo y en él. El código de ejemplo toma el archivo `example.xsd`, lo lee en un objeto <xref:System.Xml.Schema.XmlSchema> utilizando el método `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> y, a continuación, escribe el archivo en la consola y en un archivo `new.xsd` nuevo. El código de ejemplo también proporciona un <xref:System.Xml.Schema.ValidationEventHandler> como parámetro al método `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> para controlar cualquier error o advertencia de validación de esquemas que se encuentre al leer el esquema XML. Si no se especifica el <xref:System.Xml.Schema.ValidationEventHandler> (`null`), no se notifica ningún error ni advertencia.  
  
 [!code-cpp[XmlSchemaReadWriteExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaReadWriteExample/CPP/XmlSchemaReadWriteExample.cpp#1)]
 [!code-csharp[XmlSchemaReadWriteExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaReadWriteExample/CS/XmlSchemaReadWriteExample.cs#1)]
 [!code-vb[XmlSchemaReadWriteExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaReadWriteExample/VB/XmlSchemaReadWriteExample.vb#1)]  
  
 En el ejemplo se toma como entrada `example.xsd`.  
  
```xml  
<?xml version="1.0"?>  
<xs:schema id="play" targetNamespace="http://tempuri.org/play.xsd" elementFormDefault="qualified" xmlns="http://tempuri.org/play.xsd" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:element name='myShoeSize'>  
        <xs:complexType>  
            <xs:simpleContent>  
                <xs:extension base='xs:decimal'>  
                    <xs:attribute name='sizing' type='xs:string' />  
                </xs:extension>  
            </xs:simpleContent>  
        </xs:complexType>  
    </xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a>Vea también

- [Información general sobre el Modelo de objetos de esquema XML](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)  
- [Compilación de esquemas XML](../../../../docs/standard/data/xml/building-xml-schemas.md)  
- [Recorrido de esquemas XML](../../../../docs/standard/data/xml/traversing-xml-schemas.md)  
- [Edición de esquemas XML](../../../../docs/standard/data/xml/editing-xml-schemas.md)  
- [Inclusión o importación de esquemas XML](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)  
- [XmlSchemaSet para compilación de esquemas](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
- [Conjunto de información posterior a la compilación de esquemas](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)  
- [Administrar espacios de nombres en un documento XML](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md)
