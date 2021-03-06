---
title: Implementando aplicativos resilientes
description: Arquitetura de microsserviços do .NET para aplicativos .NET em contêineres | Implementando aplicativos resilientes
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: ddb0f54b15735b9192d2088495947588f59829a0
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106045"
---
# <a name="implementing-resilient-applications"></a>Implementando aplicativos resilientes

*Seus aplicativos de microsserviços e baseados em nuvem devem compreender as falhas parciais que certamente poderão ocorrerão. Você precisa projetar seu aplicativo para que ele seja resiliente a essas falhas parciais.*

A resiliência é a capacidade de recuperar de falhas e continuar a funcionar. Não se trata de evitar falhas, mas de aceitar o fato de que as falhas acontecerão e de responder a elas de uma maneira que evite o tempo de inatividade ou a perda de dados. A meta de resiliência é retornar o aplicativo para um estado totalmente funcional após uma falha.

Já é um grande desafio criar e implantar um aplicativo baseado em microsserviços. E você ainda precisa manter o aplicativo em execução em um ambiente em que algum tipo de falha certamente ocorrerá. Portanto, seu aplicativo precisa ser resiliente. Ele deve ser projetado para lidar com falhas parciais, como interrupções da rede ou falhas de nós ou de VMs na nuvem. Até mesmo os microsserviços (contêineres) que estão sendo movidos para outro nó em um cluster podem causar falhas curtas intermitentes no aplicativo.

Os diversos componentes individuais do aplicativo também precisam incorporar recursos de monitoramento de integridade. Seguindo as diretrizes neste capítulo, você poderá criar um aplicativo que pode funcionar perfeitamente apesar do tempo de inatividade temporário ou das interrupções normais que ocorrem em implantações complexas e baseadas em nuvem.


>[!div class="step-by-step"]
[Anterior](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
[Próximo](handle-partial-failure.md)
