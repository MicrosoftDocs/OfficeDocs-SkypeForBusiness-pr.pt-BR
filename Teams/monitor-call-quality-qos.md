---
title: Monitorar e melhorar a qualidade da chamada para Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Use configurações de Qualidade do Serviço (QoS) e, em seguida, Chame Análise e Painel de Qualidade de Chamada no Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 969fc5645023bfcf4ad2bc0aadfe692f61b350f0
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2022
ms.locfileid: "69245794"
---
# <a name="improve-call-quality-in-microsoft-teams"></a>Melhorar a qualidade da chamada no Microsoft Teams

Este artigo apresenta três ferramentas importantes que você pode usar para monitorar, solucionar problemas, gerenciar e melhorar a qualidade da chamada no Microsoft Teams. 

- **Painel de Qualidade de Chamada (CQD)**: para analisar tendências ou problemas em toda a organização, impulsione melhorias no desempenho

- **Análise de chamadas**: para analisar a qualidade da chamada e da reunião para usuários individuais

- **Qualidade do Serviço (QoS)**: para priorizar o tráfego de rede importante



## <a name="monitor-and-troubleshoot-call-quality"></a>Monitorar e solucionar problemas de qualidade de chamada
Você usará a **análise de chamadas** por usuário e **o Painel de Qualidade de Chamada** para localizar e solucionar problemas de qualidade de chamada que aparecem durante a operação em andamento. Isso permite que você conduza melhorias de desempenho em toda a rede. Ambas as ferramentas estão no centro de administração do Teams.

 - **A análise de** chamadas mostra informações detalhadas sobre dispositivos, redes e conectividade  **_relacionadas a chamadas e reuniões específicas_** para cada usuário no Teams. Os agentes auxiliares e administradores do Teams usarão essas informações para solucionar problemas de qualidade de chamada e conexão em uma chamada específica. Para saber mais, leia [Configurar análise de chamadas](set-up-call-analytics.md) e [usar o Call Analytics para solucionar problemas de má qualidade de chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md).
 
 - **O CQD (Painel de Qualidade de Chamada)** oferece uma **_visão em toda a rede_** da qualidade da chamada em toda a sua organização. Use informações do CQD para ajudá-lo a identificar e corrigir problemas. Primeiro, [configure o CQD](turning-on-and-using-call-quality-dashboard.md). Em seguida, leia [Gerenciar qualidade de chamada e reunião no Teams](quality-of-experience-review-guide.md).

 A análise de chamadas e o CQD são executados em paralelo e podem ser usados independentemente ou juntos. Por exemplo, se um especialista em suporte a comunicações determinar que eles precisam de mais ajuda para solucionar problemas de chamada de um usuário, eles escalonam a chamada para um engenheiro de suporte de comunicação, que tem acesso a informações adicionais sobre a chamada. Por sua vez, o engenheiro de suporte a comunicações alerta um engenheiro de rede para um possível problema relacionado ao site que eles notaram na análise de chamadas. O engenheiro de rede verifica o CQD para ver se um problema geral relacionado ao site pode ser uma causa contribuinte do problema de chamada do usuário.


## <a name="prioritize-important-network-traffic-using-qos"></a>Priorizar o tráfego de rede importante usando o QoS
À medida que seus usuários começam a usar o Teams para chamadas e reuniões, eles podem experimentar a voz de um chamador quebrando ou cortando dentro e fora de uma chamada ou reunião. O vídeo compartilhado pode congelar ou pixelar ou falhar completamente. Isso ocorre devido aos pacotes IP que representam o tráfego de voz e vídeo que encontram congestionamento de rede e chegam fora da sequência ou não. Se isso acontecer (ou para evitar que isso aconteça em primeiro lugar), use **QoS (Qualidade do Serviço)**. 

Com o QoS, você prioriza o tráfego de rede com problemas de atraso (por exemplo, fluxos de voz ou vídeo), permitindo que ele "corte na linha" na frente do tráfego que seja menos sensível (como baixar um novo aplicativo, onde um segundo extra para baixar não é grande coisa). O QoS identifica e marca todos os pacotes em fluxos em tempo real usando objetos do Windows Política de Grupo e um recurso de roteamento chamado Listas de Controle de Acesso baseadas em porta, que instrui sua rede a fornecer voz, vídeo e tela compartilhando sua própria largura de banda de rede dedicada.

Idealmente, você implementará o QoS em sua rede interna enquanto se prepara para implantar o Teams, mas pode fazê-lo a qualquer momento. Se você for pequeno o suficiente, talvez não precise de QoS.

Quando estiver pronto, leia [Implementar QoS (Qualidade do Serviço) no Microsoft Teams](QoS-in-Teams.md).

Para usar o QoS para gerenciar o tráfego de reunião, leia [Definir como você deseja lidar com o tráfego de mídia em tempo real para reuniões do Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).


## <a name="related-topics"></a>Tópicos Relacionados

[Configurar análise de chamadas](set-up-call-analytics.md)

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Configurar o CQD](turning-on-and-using-call-quality-dashboard.md)

[Gerenciar a qualidade da chamada e da reunião no Teams](quality-of-experience-review-guide.md)

[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)
