---
title: Ámbito de convoy de transacción
ms.date: 03/30/2017
ms.assetid: 37141708-a29f-4b6a-81fe-f8a11f825061
ms.openlocfilehash: fa1da6df5ad5256665610c9b3c2df7d706cef63c
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2018
ms.locfileid: "44705289"
---
# <a name="transaction-convoy-scope"></a>Ámbito de convoy de transacción
En este ejemplo se muestra cómo crear un patrón de actividad de mensajería de convoy paralelo junto con un objeto <xref:System.ServiceModel.Activities.TransactedReceiveScope> para modelar un protocolo donde varias operaciones pueden suceder en cualquier orden y todas en la misma transacción. Este ejemplo también muestra cómo <xref:System.ServiceModel.Activities.TransactedReceiveScope> crea automáticamente una nueva transacción cuando una no fluye al servidor, de modo que el cliente no utiliza ninguna transacción.  
  
 El ejemplo consta de dos proyectos de flujo de trabajo que representan el cliente y el servidor. El proyecto de cliente ejecuta un flujo de trabajo que comienza enviando a un mensaje que arranca el flujo de trabajo del servidor, que a su vez inicializa una correlación e inicia un ámbito transaccional para el resto de las actividades de mensajería. La actividad <xref:System.Activities.Statements.Sequence> del cliente contiene una pareja de <xref:System.ServiceModel.Activities.Send> y <xref:System.ServiceModel.Activities.ReceiveReply> inicial y una actividad <xref:System.Activities.Statements.Parallel> con tres bifurcaciones. Cada bifurcación envía un mensaje unidireccional al servidor. La propiedad <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> de la actividad <xref:System.Activities.Statements.Parallel> está establecida en `false` para que las tres bifurcaciones se completen.  
  
 El flujo de trabajo del servidor es similar al flujo de trabajo del cliente excepto que las actividades de mensajería se orientan hacia el lado del servidor de la comunicación y se incluyen dentro de una actividad <xref:System.ServiceModel.Activities.TransactedReceiveScope> para que todo el trabajo realizado se ejecute bajo la misma transacción. Cuando el primer mensaje se recibe en el servidor, se crea una transacción y se establece como transacción ambiente para el ámbito del cuerpo de <xref:System.ServiceModel.Activities.TransactedReceiveScope> de modo que cualquier actividad dentro de este ámbito pueda tener acceso a la transacción. Después de esto, todo lo que se recibe se ejecuta en paralelo. Todas las recepciones deben ejecutarse exactamente una vez, según describe la condición de finalización de la actividad paralela. Al final del cuerpo de <xref:System.ServiceModel.Activities.TransactedReceiveScope> existe un punto de persistencia implícito y la operación de persistencia también se ejecuta bajo la misma transacción.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución ParallelConvoySample.sln.  
  
2.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3.  Asegúrese de que ambos proyectos están establecidos para iniciarse.  
  
    1.  En **el Explorador de soluciones**, haga clic en la solución y seleccione **Establecer proyectos de inicio**.  
  
    2.  Seleccione **varios proyectos de inicio** y asegúrese de que la acción para ambos proyectos se establece en **iniciar**.  
  
4.  Para ejecutar la solución, presione CTRL+F5.  
  
     El servidor imprime `Server is running`, que indica que el servidor está listo.  
  
     Presione cualquier tecla en la ventana de la consola del cliente para iniciar el ejemplo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\TransactedConvoyScope`