---
title: Monitorar e melhorar a qualidade das chamada para o Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Use configurações de Qualidade de Serviço (QoS) e, em seguida, Análise de Chamada e Painel de Qualidade de Chamada no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 62e687de154fadffd6ac95bd628fec6f9454cc51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51162687"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Monitorar e melhorar a qualidade das chamada para o Microsoft Teams

Este artigo apresenta três ferramentas principais que você pode usar para monitorar, solucionar problemas, gerenciar e melhorar a qualidade de chamada no Microsoft Teams. 

- **Painel de Qualidade de Chamada (CQD)**: Para analisar tendências ou problemas em toda a organização, aumente melhorias no desempenho

- **Análise de chamada**: para analisar a qualidade de chamada e reunião para usuários individuais

- **Qualidade do Serviço (QoS)**: Para priorizar tráfego de rede importante



## <a name="monitor-and-troubleshoot-call-quality"></a>Monitorar e solucionar problemas de qualidade de chamada
Você usará a análise  de  chamadas por usuário e o Painel de Qualidade de Chamadas para encontrar e solucionar problemas de qualidade de chamada que ocorrem durante a operação em andamento. Isso permite que você conduza melhorias de desempenho em sua rede. Ambas as ferramentas estão no Centro de administração do Teams.

 - **A análise de** chamadas mostra informações detalhadas sobre os dispositivos, redes e conectividade relacionadas a chamadas e reuniões específicas  **_para_** cada usuário no Teams. Os administradores e agentes de ajuda do Teams usarão essas informações para solucionar problemas de qualidade de chamada e conexão em uma chamada específica. Para saber mais, leia [Configurar análise de chamada](set-up-call-analytics.md) e Usar Análise de Chamada para solucionar problemas de qualidade de chamada [ruim.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
 
 - **O Painel de Qualidade de Chamada (CQD)** oferece **_uma_** visão de qualidade de chamada em toda a rede em toda a sua organização. Use informações do CQD para ajudá-lo a identificar e corrigir problemas. Primeiro, [Configurar CQD](turning-on-and-using-call-quality-dashboard.md). Em seguida, [leia Gerenciar qualidade de chamada e reunião no Teams](quality-of-experience-review-guide.md).

 Análise de chamada e CQD são executados em paralelo e podem ser usados independentemente ou juntos. Por exemplo, se um especialista em suporte de comunicações determinar que eles precisam de mais ajuda para solucionar problemas de chamada de um usuário, eles escalonam a chamada para um engenheiro de suporte de comunicações, que tem acesso a informações adicionais sobre a chamada. Por sua vez, o engenheiro de suporte de comunicações alerta um engenheiro de rede para um possível problema relacionado ao site que eles notaram na análise de chamada. O engenheiro de rede verifica o CQD para ver se um problema geral relacionado ao site poderia ser uma causa contribuinte do problema de chamada do usuário.


## <a name="prioritize-important-network-traffic-using-qos"></a>Priorizar tráfego de rede importante usando QoS
À medida que os usuários começam a usar o Teams para chamadas e reuniões, eles podem ter a voz de um chamador quebrando ou cortando e entrando e saindo de uma chamada ou reunião. O vídeo compartilhado pode congelar, pixelar ou falhar completamente. Isso ocorre devido aos pacotes IP que representam o tráfego de voz e vídeo encontrando congestionamento de rede e saindo da sequência ou não. Se isso acontecer (ou impedir que isso aconteça em primeiro lugar), use **Qualidade de Serviço (QoS)**. 

Com a QoS, você prioriza o tráfego de rede sensível a atrasos (por exemplo, fluxos de voz ou vídeo), permitindo que ele "corte na linha" em frente ao tráfego menos sensível (como baixar um novo aplicativo, em que um segundo a mais para baixar não é grande coisa). O QoS identifica e marca todos os pacotes em fluxos em tempo real usando Objetos de Política de Grupo do Windows e um recurso de roteamento chamado Listas de Controle de Acesso baseado em Porta, que instrui sua rede a dar voz, vídeo e tela compartilhando sua própria largura de banda de rede dedicada.

Idealmente, você implementará a QoS em sua rede interna enquanto se prepara para implantar o Teams, mas pode fazê-lo a qualquer momento. Se você for pequeno o suficiente, talvez não precise de QoS.

Quando estiver pronto, leia [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).

Para usar a QoS para gerenciar o tráfego de reuniões, leia Definir como você deseja lidar com o tráfego de mídia em tempo [real para reuniões do Teams.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)


## <a name="related-topics"></a>Tópicos Relacionados

[Configurar análise de chamada](set-up-call-analytics.md)

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Configurar o CQD](turning-on-and-using-call-quality-dashboard.md)

[Gerenciar a qualidade de chamada e reunião no Teams](quality-of-experience-review-guide.md)

[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)