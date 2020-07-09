---
title: O que é o painel de qualidade de chamada (CQD)?
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Saiba mais sobre o painel de qualidade de chamada (CQD) e como usá-lo para ver relatórios sobre a qualidade da reunião e da chamada no Microsoft Teams.
ms.openlocfilehash: b7830d60139991b7ccc18679af798c74430e8ed1
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45088239"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>O que é o painel de qualidade de chamada (CQD)?

O painel de qualidade da chamada da Microsoft (CQD)- [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) mostra a qualidade da chamada e da reunião, em um **nível da organização**, para o Microsoft Teams, o Skype for Business Online e o Skype for Business Server 2019. 

  
A versão mais recente do CQD apresenta um [feed de dados near-real-time (NRT)](CQD-data-and-reports.md), o que significa que os registros de chamadas estão disponíveis no CQD dentro de 30 minutos após o término de uma chamada.

Sempre que CQD inclui [dados de EUII (informações identificáveis pelo usuário final)](CQD-data-and-reports.md#euii-data), ele é gerenciado da mesma forma que [EUII durante o Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).

O CQD foi projetado para ajudar os administradores de equipe, os administradores do Skype for Business e os engenheiros de rede a monitorarem a qualidade de chamadas e reuniões no nível da organização. Você usará o CQD para ajudá-lo a **otimizar sua rede** para impulsionar a qualidade do desempenho. Quando precisar procurar informações de chamada e de reunião para um **usuário específico**, use dados do CQD em conjunto com a análise de [chamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)por usuário.

Por exemplo, usando CQD, você pode determinar que a qualidade de chamadas deficientes do usuário (que você observou usando a análise de chamadas por usuário) se deve a um problema de rede que também afete muitos outros usuários. O CQD captura a experiência de chamadas individuais e a qualidade geral das chamadas feitas usando o Microsoft Teams ou o Skype for Business. Com o CQD, os padrões gerais podem se tornar aparentes, para que os engenheiros de rede possam fazer avaliações informadas de qualidade das chamadas. O CQD fornece relatórios de métricas de qualidade de chamada que proporcionam a você uma visão geral da qualidade da chamada, do servidor-fluxo de cliente, do cliente-fluxo de cliente e do [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)de qualidade de voz. 
  
![Captura de tela do painel de qualidade da chamada.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

No CQD, incentivamos você a carregar informações de edifício e ponto de extremidade, o que permite usar relatórios de localização avançada para analisar a qualidade de chamadas e a confiabilidade dentro do prédio de um usuário. Os dados podem ser avaliados para determinar se o problema está isolado a um único usuário ou afeta um segmento maior de usuários. Para ativar modos de exibição específicos de construção ou ponto de extremidade no CQD, um administrador deve [carregar informações de construção ou de ponto de extremidade](CQD-upload-tenant-building-data.md) na página de **carregamento de dados de locatários** do CQD.

![Captura de tela dos relatórios de localização avançada do painel de qualidade da chamada.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

Não perca nosso artigo [gerenciar a qualidade da chamada e da reunião](quality-of-experience-review-guide.md) , que oferece orientações detalhadas para o administrador do teams ou engenheiro de suporte responsável por gerenciar a qualidade do serviço no Teams.

## <a name="older-version-of-cqd-cqdlynccom"></a>Versão mais antiga do CQD (CQD.lync.com)

A versão atual do CQD ( https://CQD.Teams.microsoft.com) substituindo a versão mais antiga do CQD ( https://CQD.lync.com) . Você ainda pode usar o CQD.lync.com (disponível no centro de administração do Skype for Business), mas a partir de 1 ° de julho de 2020, ele está usando os dados do CQD. Teams.microsoft.com. Desativaremos o acesso ao CQD.lync.com em breve, portanto, você deve se mover para o CQD. Teams.microsoft.com se ainda não fez isso.

> [!IMPORTANT]
> A partir de 1 ° de julho de 2020, você não pode mais exibir ou modificar seus dados de construção ou consulta do antigo CQD (CQD.lync.com). Se ainda não migrou esses dados do CQD.lync.com e ainda precisa dele, registre um tíquete de suporte.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Usar o Power BI para analisar dados do CQD

Novidades em janeiro de 2020: [Baixe os modelos de consulta do Power bi para CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modelos personalizáveis do Power BI que você pode usar para analisar e relatar seus dados do CQD.

Leia [use o Power bi para analisar dados do CQD](CQD-Power-BI-query-templates.md) para saber mais.



## <a name="related-topics"></a>Tópicos relacionados

[Melhorar e monitorar a qualidade da chamada para equipes](monitor-call-quality-qos.md)

[Configurar o painel de qualidade da chamada (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Carregar dados do locatário e construção](CQD-upload-tenant-building-data.md)

[Dados e relatórios do CQD](CQD-data-and-reports.md)

[Usar o CQD para gerenciar a qualidade da chamada e da reunião](quality-of-experience-review-guide.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no CQD](stream-classification-in-call-quality-dashboard.md)

[Usar o Power BI para analisar dados do CQD](CQD-Power-BI-query-templates.md)


[Solução de problemas do Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)