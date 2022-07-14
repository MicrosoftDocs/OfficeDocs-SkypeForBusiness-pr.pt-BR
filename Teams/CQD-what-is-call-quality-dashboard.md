---
title: O que é o CQD (Painel de Qualidade de Chamada)?
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Saiba mais sobre o CQD (Painel de Qualidade de Chamadas) e como usá-lo para ver relatórios sobre a qualidade da reunião e da chamada no Microsoft Teams.
ms.openlocfilehash: 3bc3c9dcd83e4ff95a07fbffb6f07da39d254cde
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790066"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>O que é o CQD (Painel de Qualidade de Chamada)?

O Painel de Qualidade de Chamadas da Microsoft (CQD) [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) – mostra a qualidade da chamada e da reunião, em nível de toda a **organização, para** o Microsoft Teams, o Skype for Business Online e o Skype for Business Server 2019. 

  
A versão mais recente do CQD apresenta um feed de dados [quase em tempo real (NRT](CQD-data-and-reports.md)), o que significa que os registros de chamada estão disponíveis no CQD dentro de 30 minutos após o final de uma chamada.

Sempre que o CQD inclui dados de informações de identificação do usuário final [(EUII](CQD-data-and-reports.md#euii-data)), ele é gerenciado da mesma maneira que [euII em todo o Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).

O CQD foi projetado para ajudar administradores do Teams, Skype for Business administradores e engenheiros de rede a monitorar a qualidade de chamadas e reuniões em nível de toda a organização. Você usará o CQD para ajudá-lo a **otimizar sua rede para** impulsionar a qualidade do desempenho. Quando precisar examinar as informações de chamada e reunião de um usuário **específico, use** dados CQD em conjunto com a análise de [chamadas por usuário](use-call-analytics-to-troubleshoot-poor-call-quality.md).

Por exemplo, usando o CQD, você pode determinar que a baixa qualidade de chamada de um usuário (que você observou usando a análise de chamadas por usuário) é devido a um problema de rede que também afeta muitos outros usuários. O CQD captura a experiência de chamada individual e a qualidade geral das chamadas feitas usando o Teams ou Skype for Business. Com o CQD, os padrões gerais podem se tornar aparentes, para que os engenheiros de rede possam fazer avaliações informadas da qualidade da chamada. O CQD fornece relatórios de métricas de qualidade de chamada que fornecem insights sobre a qualidade geral da chamada, fluxos de cliente-servidor, fluxos cliente-cliente e [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252) de qualidade de voz. 
  
![Captura de tela do Painel de Qualidade da Chamada.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

No CQD, incentivamos você a carregar informações de criação e ponto de extremidade, que permitem usar relatórios do Location-Enhanced para analisar a qualidade e a confiabilidade da chamada no prédio de um usuário. Os dados podem ser avaliados para determinar se o problema é isolado para um único usuário ou afeta um segmento maior de usuários. Para ativar exibições específicas do ponto de extremidade ou de compilação no CQD, [](CQD-upload-tenant-building-data.md) um administrador deve carregar informações de criação ou ponto de extremidade na página upload de dados do locatário **CQD.**

![Captura de tela dos relatórios de Location-Enhanced painel de qualidade de chamada.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

Não perca nosso artigo Gerenciar [](quality-of-experience-review-guide.md) qualidade de chamada e reunião, que oferece diretrizes detalhadas para o administrador do Teams ou engenheiro de suporte responsável por gerenciar a qualidade do serviço no Teams.


## <a name="use-power-bi-to-analyze-cqd-data"></a>Usar o Power BI para analisar dados CQD

Novidade em janeiro de 2020: [baixe modelos de consulta do Power BI para CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modelos personalizáveis do Power BI que você pode usar para analisar e relatar seus dados CQD.

Leia [Use o Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md) para saber mais.



## <a name="related-topics"></a>Tópicos relacionados

[Melhorar e monitorar a qualidade da chamada para o Teams](monitor-call-quality-qos.md)

[Configurar o Painel de Qualidade de Chamada (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Carregar dados de locatário e de criação](CQD-upload-tenant-building-data.md)

[Dados e relatórios do CQD](CQD-data-and-reports.md)

[Usar o CQD para gerenciar a qualidade da chamada e da reunião](quality-of-experience-review-guide.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no CQD](stream-classification-in-call-quality-dashboard.md)

[Usar o Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md)


[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)
