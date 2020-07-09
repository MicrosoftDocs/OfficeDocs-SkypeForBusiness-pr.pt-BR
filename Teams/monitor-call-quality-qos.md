---
title: Monitorar e melhorar a qualidade das chamadas para o Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Use as configurações de qualidade do serviço (QoS) e, em seguida, faça a análise de chamada e painel de qualidade da chamada no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2d5db11bbd9608aebb1eb2b73ebacc9793629e44
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085928"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Monitorar e melhorar a qualidade das chamadas para o Microsoft Teams

Este artigo apresenta três ferramentas importantes que você pode usar para monitorar, solucionar problemas, gerenciar e melhorar a qualidade das chamadas no Microsoft Teams. 

- **Painel de qualidade de chamada (CQD)**: para analisar tendências ou problemas de toda a organização, melhorar o desempenho

- **Análise de chamadas**: para analisar a qualidade da chamada e da reunião para usuários individuais

- **QoS (qualidade de serviço)**: priorizar o tráfego de rede importante



## <a name="monitor-and-troubleshoot-call-quality"></a>Monitorar e solucionar problemas com a qualidade das chamadas
Você usará a análise de **chamadas** por usuário e o **painel de qualidade da chamada** para encontrar e solucionar problemas de qualidade de chamada que surgem durante a operação contínua. Isso permite que você conduza melhorias de desempenho em toda a sua rede. Ambas as ferramentas estão no centro de administração do teams.

 - A **análise de chamadas** mostra informações detalhadas sobre os dispositivos, redes e conectividade relacionados a ***chamadas e reuniões específicas*** para cada usuário no Microsoft Teams. Os agentes de administração do Teams e da assistência técnica usarão essas informações para solucionar problemas de qualidade de chamada e conexão em uma chamada específica. Para saber mais, leia [Configurar análise de chamadas](set-up-call-analytics.md) e [use a análise de chamadas para solucionar problemas de qualidade de chamadas ruins](use-call-analytics-to-troubleshoot-poor-call-quality.md).
 
 - O **painel de qualidade de chamada (CQD)** oferece uma ***visão geral*** da qualidade das chamadas em toda a sua organização. Use as informações do CQD para ajudá-lo a identificar e corrigir problemas. Primeiro, [Configure o CQD](turning-on-and-using-call-quality-dashboard.md). Em seguida, leia [gerenciar a qualidade da chamada e da reunião no Teams](quality-of-experience-review-guide.md).

 A análise de chamadas e o CQD são executados em paralelo e podem ser usados de forma independente ou em conjunto. Por exemplo, se um especialista em suporte a comunicações determinar que precisa de mais ajuda para solucionar o problema de chamada de um usuário, ele escalonará a chamada para um engenheiro de suporte a comunicações, que terá acesso a informações adicionais sobre a chamada. Por sua vez, o engenheiro de suporte à comunicação alerta um engenheiro de rede para um possível problema relacionado a sites que observou na análise de chamadas. O engenheiro de rede verifica CQD para ver se um problema geral relacionado ao site pode ser um motivo contribuinte do problema com a chamada do usuário.


## <a name="prioritize-important-network-traffic-using-qos"></a>Priorize o tráfego de rede importante usando QoS
À medida que seus usuários começarem a usar o Microsoft Teams para chamadas e reuniões, eles poderão enfrentar a voz de um autor ou recortar ou recortar uma chamada ou reunião. O vídeo compartilhado pode congelar ou ser pixel ou falhar completamente. Isso ocorre devido aos pacotes de IP que representam o tráfego de voz e vídeo que está encontrando o congestionamento da rede e que chega fora de sequência. Se isso acontecer (ou para impedir que isso aconteça em primeiro lugar), use a **QoS (qualidade de serviço)**. 

Com a QoS, você prioriza o tráfego de rede sensível à demora (por exemplo, fluxos de voz ou vídeo), permitindo que ele seja "recortado em linha" na frente do tráfego que seja menos confidencial (como baixar um novo aplicativo, onde um segundo adicional para baixar não é um negócio). A QoS identifica e marca todos os pacotes em fluxos em tempo real usando objetos de política de grupo do Windows e um recurso de roteamento chamado de listas de controle de acesso baseado em porta, o que instrui sua rede a fornecer voz, vídeo e tela que compartilhem sua própria largura de banda de rede dedicada.

O ideal é que você implemente a QoS na sua rede interna enquanto estiver pronto para implantar o Microsoft Teams, mas você pode fazer isso a qualquer momento. Se você for suficientemente pequeno, talvez não precise de QoS.

Quando estiver pronto, leia [implementar qualidade de serviço (QoS) no Microsoft Teams](QoS-in-Teams.md).

Para usar a QoS para gerenciar o tráfego de reunião, confira [definir como deseja manipular o tráfego de mídia em tempo real para reuniões de equipe](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).


## <a name="related-topics"></a>Tópicos Relacionados

[Configurar a análise de chamadas](set-up-call-analytics.md)

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Configurar o CQD](turning-on-and-using-call-quality-dashboard.md)

[Gerenciar a qualidade da chamada e da reunião no Teams](quality-of-experience-review-guide.md)

[Solução de problemas do Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

