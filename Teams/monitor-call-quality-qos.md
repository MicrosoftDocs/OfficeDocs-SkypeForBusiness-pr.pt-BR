---
title: Monitorar e melhorar a qualidade da chamada para o Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Use as configurações de QoS (Qualidade de Serviço) e, em seguida, Análise de Chamadas e Painel de Qualidade de Chamadas no Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac317ff6ac17a2b6a0e94c0fa5683979cb887b90
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66793238"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Monitorar e melhorar a qualidade da chamada para o Microsoft Teams

Este artigo apresenta três ferramentas importantes que você pode usar para monitorar, solucionar problemas, gerenciar e melhorar a qualidade das chamadas no Microsoft Teams. 

- **Painel de Qualidade de Chamada (CQD):** para analisar tendências ou problemas em toda a organização, impulsionar melhorias no desempenho

- **Análise de chamadas**: para analisar a qualidade da chamada e da reunião para usuários individuais

- **QoS (Qualidade de Serviço):** para priorizar o tráfego de rede importante



## <a name="monitor-and-troubleshoot-call-quality"></a>Monitorar e solucionar problemas de qualidade de chamada
Você usará a Análise de Chamadas **por usuário e** o  Painel de Qualidade de Chamadas para localizar e solucionar problemas de qualidade de chamada que ocorrem durante a operação em andamento. Isso permite que você conduza melhorias de desempenho em sua rede. Ambas as ferramentas estão no centro de administração do Teams.

 - **A análise de** chamadas mostra informações detalhadas sobre dispositivos, redes e conectividade relacionadas a chamadas e reuniões específicas  **_para cada_** usuário no Teams. Os administradores e agentes de assistência técnica do Teams usarão essas informações para solucionar problemas de conexão e qualidade de chamada em uma chamada específica. Para saber mais, leia [Configurar a análise de chamadas e](set-up-call-analytics.md) [usar a Análise de Chamadas para solucionar problemas de baixa qualidade de chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md).
 
 - **O CQD (Painel de Qualidade de Chamadas)** **_oferece uma_** exibição em toda a rede da qualidade da chamada em toda a sua organização. Use informações do CQD para ajudá-lo a identificar e corrigir problemas. Primeiro, [configure o CQD](turning-on-and-using-call-quality-dashboard.md). Em seguida, [leia Gerenciar a qualidade da chamada e da reunião no Teams](quality-of-experience-review-guide.md).

 A análise de chamadas e o CQD são executados em paralelo e podem ser usados de forma independente ou em conjunto. Por exemplo, se um especialista em suporte de comunicações determinar que precisa de mais ajuda para solucionar o problema de chamada de um usuário, ele escalona a chamada para um engenheiro de suporte de comunicações, que tem acesso a informações adicionais sobre a chamada. Por sua vez, o engenheiro de suporte de comunicações alerta um engenheiro de rede para um possível problema relacionado ao site que percebeu na análise de chamadas. O engenheiro de rede verifica o CQD para ver se um problema geral relacionado ao site pode ser uma causa de contribuição do problema de chamada do usuário.


## <a name="prioritize-important-network-traffic-using-qos"></a>Priorizar o tráfego de rede importante usando QoS
À medida que os usuários começam a usar o Teams para chamadas e reuniões, eles podem ter a voz de um chamador quebrando ou cortando e cortando uma chamada ou reunião. O vídeo compartilhado pode congelar ou pixelar ou falhar completamente. Isso ocorre devido aos pacotes IP que representam o tráfego de voz e vídeo encontrando congestionamento de rede e saindo da sequência ou não. Se isso acontecer (ou para impedir que isso aconteça em primeiro lugar), use **qoS (Qualidade de Serviço)**. 

Com a QoS, você prioriza o tráfego de rede sensível ao atraso (por exemplo, fluxos de voz ou vídeo), permitindo que ele "corte na linha" na frente do tráfego menos sensível (como baixar um novo aplicativo, em que um segundo extra para baixar não é grande coisa). A QoS identifica e marca todos os pacotes em fluxos em tempo real usando objetos do Windows Política de Grupo e um recurso de roteamento chamado Listas de Controle de Acesso baseadas em porta, que instrui sua rede a fornecer voz, vídeo e compartilhamento de tela com sua própria largura de banda de rede dedicada.

Idealmente, você implementará a QoS em sua rede interna enquanto estiver pronto para implantar o Teams, mas poderá fazer isso a qualquer momento. Se você for pequeno o suficiente, talvez não precise de QoS.

Quando estiver pronto, leia [Implementar qoS (qualidade de serviço) no Microsoft Teams](QoS-in-Teams.md).

Para usar a QoS para gerenciar o tráfego de reunião, leia Definir como você deseja lidar com o tráfego de mídia em tempo [real para reuniões do Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).


## <a name="related-topics"></a>Tópicos Relacionados

[Configurar a análise de chamadas](set-up-call-analytics.md)

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Configurar o CQD](turning-on-and-using-call-quality-dashboard.md)

[Gerenciar a qualidade da chamada e da reunião no Teams](quality-of-experience-review-guide.md)

[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)
