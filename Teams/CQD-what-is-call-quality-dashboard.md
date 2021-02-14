---
title: O que é o CQD (Painel de Qualidade de Chamada)?
ms.author: serdars
author: SerdarSoysal
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
description: Saiba mais sobre o CQD (Painel de Qualidade de Chamada) e como usá-lo para ver relatórios sobre a qualidade da reunião e da chamada no Microsoft Teams.
ms.openlocfilehash: 9ba1956533887314a9ffa7ad994cbb4c81ffe103
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583480"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>O que é o CQD (Painel de Qualidade de Chamada)?

O Painel de Qualidade de Chamada da Microsoft (CQD) – – – mostra a qualidade de chamadas e reuniões, em nível de organização, para o Microsoft Teams, o Skype for Business Online e o [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) Skype for Business Server 2019.  

  
A versão mais recente do CQD apresenta um feed de dados em tempo [real (NRT),](CQD-data-and-reports.md)o que significa que os registros de chamada estão disponíveis no CQD dentro de 30 minutos após o final de uma chamada.

Sempre que o CQD inclui dados de identificação do usuário final [(EUII),](CQD-data-and-reports.md#euii-data)ele é gerenciado da mesma forma que o EUII em todo [o Microsoft 365.](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)

O CQD foi projetado para ajudar administradores do Teams, administradores do Skype for Business e engenheiros de rede a monitorar a qualidade de chamadas e reuniões em todo o nível da organização. Você usará o CQD para ajudá-lo a **otimizar sua rede** para impulsionar a qualidade do desempenho. Quando precisar procurar informações de chamada e reunião para um usuário **específico,** use dados CQD em conjunto com a análise de chamada [por usuário.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

Por exemplo, usando o CQD, você pode determinar que a baixa qualidade de chamada de um usuário (que você observou usando a análise de chamada por usuário) é devido a um problema de rede que também afeta muitos outros usuários. O CQD captura a experiência de chamada individual e a qualidade geral das chamadas feitas usando o Teams ou o Skype for Business. Com o CQD, os padrões gerais podem se tornar aparentes, para que os engenheiros de rede possam fazer avaliações informadas sobre a qualidade da chamada. O CQD fornece relatórios de métricas de qualidade de chamada que proporcionam informações sobre a qualidade geral da chamada, fluxos cliente-servidor, fluxos cliente e SLA de qualidade de [voz.](https://go.microsoft.com/fwlink/p/?linkid=846252) 
  
![Captura de tela do Painel de Qualidade da Chamada.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

No CQD, incentivamos você a carregar informações de construção e ponto de extremidade, que permitem que você use Location-Enhanced Relatórios para analisar a qualidade e a confiabilidade de chamada no edifício de um usuário. Os dados podem ser avaliados para determinar se o problema é isolado para um único usuário ou afeta um segmento maior de usuários. Para ativar exibições específicas do edifício ou do [](CQD-upload-tenant-building-data.md) ponto de **extremidade** no CQD, um administrador deve carregar informações sobre o edifício ou o ponto de extremidade na página upload de dados do locatário CQD.

![Captura de tela dos relatórios do Painel de Location-Enhanced Qualidade da Chamada.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

Não perca nosso [](quality-of-experience-review-guide.md) artigo Gerenciar chamada e qualidade de reunião, que oferece orientações detalhadas para o administrador ou engenheiro de suporte do Teams responsável pelo gerenciamento da qualidade do serviço no Teams.

## <a name="older-version-of-cqd-cqdlynccom"></a>Versão mais antiga do CQD (CQD.lync.com)

A versão atual do CQD ( está substituindo a versão https://CQD.Teams.microsoft.com) mais antiga do CQD ( https://CQD.lync.com) . Você ainda pode usar o CQD.lync.com (disponível no Centro de administração do Skype for Business), mas a partir de 1º de julho de 2020, ele usará os dados do CQD. Teams.microsoft.com. Desativaremos o acesso ao CQD.lync.com em breve, portanto, você deve ir para o CQD. Teams.microsoft.com se você ainda não fez isso.

> [!IMPORTANT]
> A partir de 1º de julho de 2020, você não poderá mais exibir ou modificar seus dados de construção ou consulta do antigo CQD (CQD.lync.com). Se você ainda não tiver migrado esses dados do CQD.lync.com e ainda precisar deles, registre um tíquete de suporte.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Usar o Power BI para analisar dados CQD

Novo em janeiro de 2020: Baixe modelos de consulta [do Power BI para CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) Modelos personalizáveis do Power BI que você pode usar para analisar e relatar seus dados CQD.

Leia [Use o Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md) para saber mais.



## <a name="related-topics"></a>Tópicos relacionados

[Melhorar e monitorar a qualidade da chamada para o Teams](monitor-call-quality-qos.md)

[Configurar o Painel de Qualidade de Chamada (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Carregar dados de locatário e de construção](CQD-upload-tenant-building-data.md)

[Dados e relatórios do CQD](CQD-data-and-reports.md)

[Usar o CQD para gerenciar a qualidade da chamada e da reunião](quality-of-experience-review-guide.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de Fluxo no CQD](stream-classification-in-call-quality-dashboard.md)

[Usar o Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md)


[Solução de problemas do Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)