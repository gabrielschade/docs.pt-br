---
title: Participantes de persistência
ms.date: 03/30/2017
ms.assetid: f84d2d5d-1c1b-4f19-be45-65b552d3e9e3
ms.openlocfilehash: f2875ead24e4c072d267a8bb6cddddc7f9b96d86
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33519803"
---
# <a name="persistence-participants"></a>Participantes de persistência
Um participante de persistência pode participar em uma operação de persistência (salvar) ou carregamento disparada por um aplicativo host. O [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] fornecido com duas classes abstratas, **PersistenceParticipant** e **PersistenceIOParticipant**, que você pode usar para criar um participante de persistência. Um participante de persistência deriva de uma dessas classes, implementa-se os métodos de interesse, e então adiciona uma instância da classe à coleção de <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A> em <xref:System.ServiceModel.Activities.WorkflowServiceHost> . O aplicativo host pode procurar essas extensões de fluxo de trabalho para manter uma instância de fluxo de trabalho e chama métodos apropriados nos participantes de persistência em momentos apropriadas.  
  
 A lista a seguir descreve as tarefas executadas pelo subsistema de persistência em diferentes estágios da operação persistir (salvar). Os participantes de persistência são usados em terceira e quartas etapas. Se o participante é um participante de e/s (um participante de persistência que também participa de operações de e/s), o participante também é usado no estágio de sexta.  
  
1.  Obtém os valores internos, incluindo o estado de fluxo de trabalho, indexadores, variáveis mapeados, e carimbo de data/hora.  
  
2.  Coleta todos os participantes de persistência que foram adicionados à coleção de extensão associada com a instância de fluxo de trabalho.  
  
3.  Chama o método de <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> implementado por todos os participantes de persistência.  
  
4.  Chama o método de <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> implementado por todos os participantes de persistência.  
  
5.  Persistir ou salvar o fluxo de trabalho no armazenamento de persistência.  
  
6.  Invoca o <xref:System.Activities.Persistence.PersistenceIOParticipant.BeginOnSave%2A> método em todos os participantes de persistência e/s. Se o participante não é um participante de e/s, essa tarefa será ignorada. Se o episódio de persistência é transacional, a transação é fornecida na propriedade de Transaction.Current.  
  
7.  Aguarda que todos os participantes de persistência terminem. Se todos os participantes são bem-sucedidas em manter dados de instância, confirmações a transação.  
  
 Um participante de persistência deriva o **PersistenceParticipant** de classe e pode implementar o **CollectValues** e **MapValues** métodos. Deriva de um participante de persistência e/s de **PersistenceIOParticipant** de classe e pode implementar o **BeginOnSave** método além de implementar o **CollectValues**e **MapValues** métodos.  
  
 Cada etapa é concluída antes que a fase seguir inicia. Por exemplo, os valores são coletados de **todos os** participantes de persistência na primeira etapa. Todos os valores coletados na primeira etapa são fornecidos na todos os participantes de persistência na segunda etapa mapeando. Em todos os valores coletados e mapeados no primeiro e na segunda etapas são fornecidos para o provedor de persistência na terceira etapa, e assim por diante.  
  
 A lista a seguir descreve as tarefas executadas pelo subsistema de persistência em diferentes estágios da operação de carregamento. Os participantes de persistência são usados na quarta fase. Os participantes de e/s de persistência (participantes de persistência que também participarem de operações de e/s) também são usados no estágio de terceiro.  
  
1.  Coleta todos os participantes de persistência que foram adicionados à coleção de extensão associada com a instância de fluxo de trabalho.  
  
2.  Carrega o fluxo de trabalho do armazenamento de persistência.  
  
3.  Invoca o <xref:System.Activities.Persistence.PersistenceIOParticipant.BeginOnLoad%2A> em todos os participantes de persistência e/s e esperas para todos os participantes de persistência concluir. Se o episódio de persistência é transacional, a transação é fornecida em Transaction.Current.  
  
4.  Carrega a instância de fluxo de trabalho na memória com base nos dados recuperados do armazenamento de persistência.  
  
5.  Chama o <xref:System.Activities.Persistence.PersistenceParticipant.PublishValues%2A> em cada participante de persistência.  
  
 Um participante de persistência deriva o **PersistenceParticipant** de classe e pode implementar o **PublishValues** método. Deriva de um participante de persistência e/s de **PersistenceIOParticipant** de classe e pode implementar o **BeginOnLoad** método além de implementar o **PublishValues**método.  
  
 Ao carregar uma instância de fluxo de trabalho o provedor de persistência cria um bloqueio nessa instância. Isso impede que a instância é carregada por mais de um host em um cenário com vários nós. Se você tentar carregar uma instância de fluxo de trabalho que foi bloqueada, você verá uma exceção semelhante à seguinte: A exceção "System.ServiceModel.Persistence.InstanceLockException: A operação solicitada não pôde ser concluída porque o bloqueio para a instância ' 00000000-0000-0000-0000-000000000000' não pôde ser adquirido ". Esse erro é causado quando ocorre um destes procedimentos:  
  
-   Em um cenário com vários nós a instância é carregada por outro host.  Há algumas maneiras diferentes para resolver esses tipos de conflitos: encaminhar o processamento para o nó que possui o bloqueio e a nova tentativa, ou forçar a carga que fará com que o outro host é possível de salvar seu trabalho.  
  
-   Em um cenário de único nó e no host falhou.  Quando o host inicia anterior novamente (um processo reciclar ou criando uma nova factory do provedor de persistência) o novo host tenta carregar uma instância que é bloqueada ainda pelo host antigo porque o bloqueio ainda não expirou.  
  
-   Em um cenário de único nó e na instância em questão foi anuladas em algum ponto e uma nova instância do provedor de persistência é criada que tenha uma identificação diferente do host  
  
 O valor de tempo limite de bloqueio tem um valor padrão de 5 minutos, você pode especificar um valor de tempo limite diferente ao chamar <xref:System.ServiceModel.Persistence.PersistenceProvider.Load%2A>.  
  
## <a name="in-this-section"></a>Nesta seção  
  
-   [Como criar um participante personalizado da persistência](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-persistence-participant.md)  
  
## <a name="see-also"></a>Consulte também  
 [Extensibilidade de repositório](../../../docs/framework/windows-workflow-foundation/store-extensibility.md)
