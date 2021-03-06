---
title: Registros, imagens e contêineres do Docker
description: Containerized Docker Application Lifecycle with Microsoft Platform and Tools (Ciclo de vida de aplicativo do Docker em contêineres com a plataforma e as ferramentas da Microsoft)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: ff5a1f3e4b09ac9f7ea600d3f127523b96fcce55
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106357"
---
# <a name="docker-containers-images-and-registries"></a>Registros, imagens e contêineres do Docker

Ao usar o Docker, você cria um aplicativo ou serviço e pacote ele e suas dependências em uma imagem de contêiner. Uma imagem é uma representação estática do aplicativo ou do serviço e de sua configuração e dependências.

Para executar o aplicativo ou serviço, a imagem do aplicativo é instanciada para criar um contêiner, que serão executados no host do Docker. Inicialmente, os contêineres são testados em um ambiente de desenvolvimento ou em um computador.

Você pode armazenar imagens em um registro, que atua como uma biblioteca de imagens. Ao implantar o orchestrators de produção, é necessário um registro. O Docker mantém um Registro público por meio do [Hub do Docker](https://hub.docker.com/); outros fornecedores fornecem os Registros para diferentes coleções de imagens. Como alternativa, as empresas podem ter um Registro privado local para suas próprias imagens do Docker.

Figura 1-4 mostra como imagens e registros no Docker se relacionam com outros componentes. Ela também mostra as várias ofertas de Registro dos fornecedores.

![](./media/image4.png)

Figura 1-4: taxonomia Docker termos e conceitos

Ao colocar imagens em um registro, você pode armazenar bits de aplicativo estático e imutável, incluindo todas as suas dependências, em um nível de estrutura. Você pode versão e implantar imagens em vários ambientes e, portanto, fornecem uma unidade de implantação consistente.

Registros de imagem privada, hospedado no local ou na nuvem, são recomendados para as seguintes situações:

-   Suas imagens não devem ser compartilhadas publicamente devido à confidencialidade.

-   Você deseja ter latência de rede mínima entre suas imagens e o ambiente de implantação escolhido. Por exemplo, se seu ambiente de produção é o Azure, você provavelmente desejará armazenar as imagens no registro de contêiner do Azure para que a latência de rede será mínima. De maneira semelhante, se seu ambiente de produção for local, tenha um Registro Confiável do Docker local disponível na mesma rede local.

>[!div class="step-by-step"]
[Anterior](docker-terminology.md)
[Próximo](Docker-application-lifecycle/index.md)
