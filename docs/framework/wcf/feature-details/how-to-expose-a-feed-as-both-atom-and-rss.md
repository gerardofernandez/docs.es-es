---
title: 'Cómo: Exponer una fuente como Atom y RSS'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fe374932-67f5-487d-9325-f868812b92e4
ms.openlocfilehash: 4780e43679d461509911a4abda689a0c16112e4a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33493430"
---
# <a name="how-to-expose-a-feed-as-both-atom-and-rss"></a>Cómo: Exponer una fuente como Atom y RSS
Windows Communication Foundation (WCF) le permite crear un servicio que expone una fuente de distribución. En este tema se explica cómo crear un servicio de distribución que exponga una fuente de distribución mediante Atom 1.0 y RSS 2.0. Este servicio expone un extremo que puede devolver cualquiera de los dos formatos de distribución. Para simplificar, el servicio usado en este ejemplo tiene host propio. En un entorno de producción un servicio de este tipo estaría hospedado en IIS o WAS. Para obtener más información acerca de la opciones de hospedaje de WCF diferentes, consulte [hospedaje](../../../../docs/framework/wcf/feature-details/hosting.md).  
  
### <a name="to-create-a-basic-syndication-service"></a>Creación de un servicio de distribución básico  
  
1.  Defina un contrato de servicios utilizando una interfaz marcada con el atributo <xref:System.ServiceModel.Web.WebGetAttribute>. Cada operación que se expone como una fuente de distribución devuelve un objeto <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>. Observe los parámetros de <xref:System.ServiceModel.Web.WebGetAttribute>. `UriTemplate` especifica la dirección URL usada para invocar esta operación de servicio. La cadena para este parámetro contiene literales y una variable entre llaves ({*formato*}). Esta variable corresponde al parámetro `format` de la operación del servicio. Para obtener más información, consulta <xref:System.UriTemplate>. `BodyStyle` afecta a cómo se escriben los mensajes que esta operación de servicio envía y recibe. <xref:System.ServiceModel.Web.WebMessageBodyStyle.Bare> especifica que los datos enviados a y desde esta operación de servicio no están ajustados por los elementos XML definidos por la infraestructura. Para obtener más información, consulta <xref:System.ServiceModel.Web.WebMessageBodyStyle>.  
  
     [!code-csharp[htAtomRss#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#0)]
     [!code-vb[htAtomRss#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#0)]  
  
    > [!NOTE]
    >  Utilice el <xref:System.ServiceModel.ServiceKnownTypeAttribute> para especificar los tipos que devuelven las operaciones de servicio en esta interfaz.  
  
2.  Implemente el contrato de servicios.  
  
     [!code-csharp[htAtomRss#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#1)]
     [!code-vb[htAtomRss#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#1)]  
  
3.  Cree un objeto <xref:System.ServiceModel.Syndication.SyndicationFeed> y agregue un autor, categoría y descripción.  
  
     [!code-csharp[htAtomRss#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#2)]
     [!code-vb[htAtomRss#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#2)]  
  
4.  Cree varios objetos <xref:System.ServiceModel.Syndication.SyndicationItem>.  
  
     [!code-csharp[htAtomRss#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#3)]
     [!code-vb[htAtomRss#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#3)]  
  
5.  Agregue los objetos <xref:System.ServiceModel.Syndication.SyndicationItem> a la fuente.  
  
     [!code-csharp[htAtomRss#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#4)]
     [!code-vb[htAtomRss#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#4)]  
  
6.  Utilice el parámetro format para devolver el formato solicitado.  
  
     [!code-csharp[htAtomRss#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#5)]
     [!code-vb[htAtomRss#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#5)]  
  
### <a name="to-host-the-service"></a>Para hospedar el servicio  
  
1.  Crear un objeto <xref:System.ServiceModel.Web.WebServiceHost>. La clase <xref:System.ServiceModel.Web.WebServiceHost> agrega automáticamente un extremo en la dirección base del servicio, salvo que se especifique uno en el código o en la configuración. En este ejemplo, no se especifica ningún extremo, por lo que se expone el predeterminado.  
  
     [!code-csharp[htAtomRss#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#6)]
     [!code-vb[htAtomRss#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#6)]  
  
2.  Abra el host de servicio, cargue la fuente desde el servicio, muestre la fuente y espere a que el usuario presione Entrar.  
  
     [!code-csharp[htAtomRss#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#8)]
     [!code-vb[htAtomRss#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/program.vb#8)]  
  
### <a name="to-call-getblog-with-an-http-get"></a>Llamar a GetBlog mediante HTTP GET  
  
1.  Abra Internet Explorer, escriba la dirección URL siguiente y presione ENTRAR. http://localhost:8000/BlogService/GetBlog  
  
     La dirección URL contiene la dirección base del servicio (http://localhost:8000/BlogService), la dirección relativa del extremo y la operación de servicio a llamar.  
  
### <a name="to-call-getblog-from-code"></a>Llamar a GetBlog() mediante código  
  
1.  Cree un <xref:System.Xml.XmlReader> con la dirección base y el método al que está llamando.  
  
     [!code-csharp[htAtomRss#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#9)]
     [!code-vb[htAtomRss#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#9)]  
  
2.  Llame al método estático <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29>, pasando el <xref:System.Xml.XmlReader> que acaba de crear.  
  
     [!code-csharp[htAtomRss#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#10)]
     [!code-vb[htAtomRss#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#10)]  
  
     Esto invoca la operación de servicio y rellena una nueva <xref:System.ServiceModel.Syndication.SyndicationFeed> con el formateador devuelto desde la operación del servicio.  
  
3.  Obtenga acceso al objeto de fuente.  
  
     [!code-csharp[htAtomRss#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/snippets.cs#11)]
     [!code-vb[htAtomRss#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htatomrss/vb/snippets.vb#11)]  
  
## <a name="example"></a>Ejemplo  
 A continuación, se muestra una lista de código completa para este ejemplo.  
  
 [!code-csharp[htAtomRss#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/htatomrss/cs/program.cs#12)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Al compilar el código anterior, haga referencia a System.ServiceModel.dll y System.ServiceModel.Web.dll.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.WebHttpBinding>  
 <xref:System.ServiceModel.Web.WebGetAttribute>
