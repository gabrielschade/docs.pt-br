---
title: Processamento de mensagem com problema
ms.date: 03/30/2017
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
ms.openlocfilehash: a7839b60dbad7919a644c196a1c63f6bc46fb5d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33492939"
---
# <a name="out-of-order-message-processing"></a>Processamento de mensagem com problema
Serviços de fluxo de trabalho podem depender de mensagens enviadas em uma ordem específica. Um serviço de fluxo de trabalho contém um ou mais <xref:System.ServiceModel.Activities.Receive> atividades e cada <xref:System.ServiceModel.Activities.Receive> atividade está esperando uma mensagem específica. Sem garantias de entrega de transporte particular, as mensagens enviadas por clientes podem ser atrasadas e portanto entregues em uma ordem não pode esperar que o serviço de fluxo de trabalho. Implementar um serviço de fluxo de trabalho que não exige que as mensagens enviadas em uma determinada ordem normalmente é feita usando uma atividade paralela. Para um protocolo de aplicativo mais complicado, o fluxo de trabalho deve se tornar muito complexo muito rapidamente.  A mensagem fora de ordem de processamento de recurso no Windows Communication Foundation (WCF) permite que você crie um fluxo de trabalho sem toda a complexidade de atividades paralelas aninhadas. Só há suporte para o processamento de mensagens de fora de ordem nos canais que oferecem suporte a <xref:System.ServiceModel.Channels.ReceiveContext> como as ligações de MSMQ do WCF.  
  
## <a name="enabling-out-of-order-message-processing"></a>Habilitando o processamento de mensagens de fora de ordem  
 Processamento de mensagens de fora de ordem é habilitado definindo o <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> propriedade `true` no WorkflowService. O exemplo a seguir mostra como definir o <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> propriedade no código.  
  
```csharp  
// Code: Opt-in to Buffered Receive processing...  
WorkflowService service = new WorkflowService  
{  
    Name="MyService",  
    Body = workflow,  
    AllowBufferedReceive = true  
};  
```  
  
 Você também pode aplicar o `AllowBufferedReceive` atributo para um serviço de fluxo de trabalho em XAML, conforme mostrado no exemplo a seguir.  
  
```xaml  
// Xaml: Opt-in to Buffered Receive processing...  
<WorkflowService AllowBufferedReceive="True">  
   <!—the actual children activities -->  
</Sequence>  
```  
  
## <a name="see-also"></a>Consulte também  
 <xref:System.ServiceModel.Channels.ReceiveContext>  
 [Serviços de fluxo de trabalho](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [Sessões confiáveis e filas](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
