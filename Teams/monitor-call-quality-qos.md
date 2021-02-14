---
title: Monitorar e melhorar a qualidade da chamada para o Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Use as configurações de QoS (Qualidade de Serviço) e, em seguida, Análise de Chamada e Painel de Qualidade de Chamada no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 107bbf867c410a556e02d76eb991cf5f04730efa
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46587631"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Monitorar e melhorar a qualidade da chamada para o Microsoft Teams

Este artigo apresenta três ferramentas principais que você pode usar para monitorar, solucionar problemas, gerenciar e melhorar a qualidade da chamada no Microsoft Teams. 

- **Painel de Qualidade de Chamada (CQD)**: para analisar tendências ou problemas em toda a organização, melhore o desempenho

- **Análise de chamada:** para analisar a qualidade da chamada e da reunião para usuários individuais

- **QoS (Qualidade de Serviço)**: para priorizar o tráfego de rede importante



## <a name="monitor-and-troubleshoot-call-quality"></a>Monitorar e solucionar problemas de qualidade da chamada
Você usará a análise  de  chamadas por usuário e o Painel de Qualidade da Chamada para encontrar e solucionar problemas de qualidade de chamada que ocorrem durante a operação em andamento. Isso permite que você melhore o desempenho em toda a rede. Essas duas ferramentas estão no Centro de administração do Teams.

 - **A análise de** chamadas mostra informações detalhadas sobre dispositivos, redes e conectividade relacionadas  ***a*** chamadas e reuniões específicas para cada usuário no Teams. Os agentes de administração e de serviços de ajuda do Teams usarão essas informações para solucionar problemas de conexão e qualidade da chamada em uma chamada específica. Para saber mais, leia [Configurar a análise de chamada e](set-up-call-analytics.md) usar a Análise de Chamada para solucionar problemas de baixa qualidade de [chamada.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
 
 - **O CQD (Painel** de Qualidade de Chamada) oferece ***uma*** visão de qualidade de chamada em toda a rede em toda a sua organização. Use as informações do CQD para ajudá-lo a identificar e corrigir problemas. Primeiro, [configurar o CQD.](turning-on-and-using-call-quality-dashboard.md) Em seguida, [leia Gerenciar a qualidade da chamada e da reunião no Teams.](quality-of-experience-review-guide.md)

 A análise de chamada e o CQD são executados em paralelo e podem ser usados de forma independente ou em conjunto. Por exemplo, se um especialista de suporte de comunicações determinar que ele precisa de mais ajuda para solucionar o problema de chamada de um usuário, ele encaminha a chamada para um engenheiro de suporte de comunicações, que tem acesso a informações adicionais sobre a chamada. Por sua vez, o engenheiro de suporte de comunicações alerta um engenheiro de rede sobre um possível problema relacionado ao site que eles observaram na análise de chamada. O engenheiro de rede verifica o CQD para ver se um problema geral relacionado ao site pode ser uma causa do problema de chamada do usuário.


## <a name="prioritize-important-network-traffic-using-qos"></a>Priorizar tráfego de rede importante usando QoS
À medida que os usuários começam a usar o Teams para chamadas e reuniões, eles podem ver a voz de um chamador se separando ou cortando e cortando uma chamada ou reunião. O vídeo compartilhado pode congelar ou pixelar ou falhar completamente. Isso ocorre devido aos pacotes IP que representam o tráfego de voz e vídeo, encontrando congestionamento de rede e saindo da sequência ou não. Se isso acontecer (ou para impedir que isso aconteça em primeiro lugar), use **qoS (Qualidade de Serviço).** 

Com a QoS, você prioriza o tráfego de rede sensível ao atraso (por exemplo, fluxos de voz ou vídeo), permitindo que ele "corte na linha" na frente do tráfego menos sensível (como baixar um novo aplicativo, em que um segundo extra para baixar não é um problema). A QoS identifica e marca todos os pacotes em fluxos em tempo real usando Objetos de Política de Grupo do Windows e um recurso de roteamento chamado Listas de Controle de Acesso baseado em porta, que instrui sua rede a dar voz, vídeo e compartilhamento de tela à sua própria largura de banda de rede dedicada.

O ideal é implementar o QoS em sua rede interna enquanto se prepara para implementar o Teams, mas você pode fazê-lo a qualquer momento. Se você for pequeno o suficiente, talvez não precise de QoS.

Quando estiver pronto, leia [Implementar Qualidade de Serviço (QoS) no Microsoft Teams.](QoS-in-Teams.md)

Para usar qoS para gerenciar o tráfego da reunião, leia Definir como você deseja lidar com o tráfego de mídia em tempo [real para reuniões do Teams.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)


## <a name="related-topics"></a>Tópicos Relacionados

[Configurar a análise de chamada](set-up-call-analytics.md)

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Configurar o CQD](turning-on-and-using-call-quality-dashboard.md)

[Gerenciar a qualidade da chamada e da reunião no Teams](quality-of-experience-review-guide.md)

[Solução de problemas do Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

