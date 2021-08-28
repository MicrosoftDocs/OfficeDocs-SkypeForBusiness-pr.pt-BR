---
title: O que é o Painel de Qualidade de Chamada (CQD)?
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Saiba mais sobre o CQD (Painel de Qualidade de Chamada) e como usá-lo para ver relatórios sobre a qualidade da reunião e da chamada no Microsoft Teams.
ms.openlocfilehash: 92b7bdcd5acaa86c530f5d0380666b2ebce3eed8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593265"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>O que é o Painel de Qualidade de Chamada (CQD)?

O Painel de Qualidade de Chamada da Microsoft (CQD) - mostra a qualidade de chamada e reunião, no nível de toda a organização, para Microsoft Teams, Skype for Business Online e [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) Skype for Business Server 2019.  

  
A versão mais recente do CQD apresenta um feed de dados quase em tempo [real (NRT),](CQD-data-and-reports.md)o que significa que os registros de chamada estão disponíveis no CQD dentro de 30 minutos após o final de uma chamada.

Sempre que o CQD inclui dados de informações de identificação do usuário final [(EUII),](CQD-data-and-reports.md#euii-data)ele é gerenciado da mesma maneira que [euII](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)em todo o Microsoft 365 .

O CQD foi projetado para ajudar Teams administradores, administradores de Skype for Business e engenheiros de rede monitoram a qualidade de chamada e reunião em nível de toda a organização. Você usará o CQD para ajudá-lo a **otimizar sua rede para** impulsionar a qualidade do desempenho. Quando você precisar procurar informações de chamada e reunião para um usuário **específico,** use dados CQD em conjunto com a análise de chamada [por usuário.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

Por exemplo, usando o CQD, você pode determinar que a qualidade de chamada ruim de um usuário (que você observou usando análise de chamada por usuário) é devido a um problema de rede que também afeta muitos outros usuários. O CQD captura a experiência de chamada individual e a qualidade geral das chamadas feitas usando Teams ou Skype for Business. Com o CQD, os padrões gerais podem se tornar aparentes, para que os engenheiros de rede possam fazer avaliações informadas da qualidade da chamada. O CQD fornece relatórios de métricas de qualidade de chamada que proporcionam uma visão geral da qualidade da chamada, fluxos de cliente-cliente, fluxos cliente-cliente e SLA de qualidade de [voz.](https://go.microsoft.com/fwlink/p/?linkid=846252) 
  
![Captura de tela do Painel de Qualidade de Chamada.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

No CQD, recomendamos que você carregue informações de construção e ponto de extremidade, o que permite que você use Location-Enhanced Relatórios para analisar a qualidade e a confiabilidade de chamada no edifício de um usuário. Os dados podem ser avaliados para determinar se o problema está isolado para um único usuário ou afeta um segmento maior de usuários. Para ativar exibições específicas de criação ou ponto [](CQD-upload-tenant-building-data.md) de extremidade no CQD, um administrador deve carregar informações de construção ou ponto de extremidade na página CQD **Tenant Data Upload** page.

![Captura de tela dos relatórios de Location-Enhanced do Painel de Qualidade de Chamada.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

Não perca nosso artigo [Gerenciar](quality-of-experience-review-guide.md) qualidade de chamada e reunião, que oferece orientações detalhadas para o administrador do Teams ou engenheiro de suporte responsável pelo gerenciamento da qualidade do serviço no Teams.

## <a name="legacy-version-of-cqd-cqdlynccom"></a>Versão herdada do CQD (CQD.lync.com)

A versão atual do CQD ( substituiu a https://CQD.Teams.microsoft.com) versão herdada do CQD ( https://CQD.lync.com) . Você ainda pode usar o CQD.lync.com (disponível no centro de administração do Skype for Business), mas, a partir de 1º de julho de 2020, ele está usando os dados do CQD. Teams.microsoft.com e você não pode mais exibir ou modificar seus dados de construção ou consulta do CQD antigo (CQD.lync.com). Se você ainda não tiver migrado esses dados do CQD.lync.com e ainda precisar deles, registre um tíquete de suporte.

> [!IMPORTANT]
> A partir de 31 de julho de 2021, estamos retirando a versão herdada do CQD (CQD.lync.com). Após essa data, você será redirecionado automaticamente para o CQD. Teams.microsoft.com ao tentar acessar CQD.lync.com, e todos os dados de consulta ou construção não migrados serão perdidos.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Usar Power BI para analisar dados CQD

Novidade em janeiro de 2020: [Baixar Power BI de consulta para CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modelos de Power BI personalizáveis que você pode usar para analisar e relatar seus dados CQD.

Leia [Use Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md) para saber mais.



## <a name="related-topics"></a>Tópicos relacionados

[Melhorar e monitorar a qualidade de chamada para Teams](monitor-call-quality-qos.md)

[Configurar o Painel de Qualidade de Chamada (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Upload locatário e a criação de dados](CQD-upload-tenant-building-data.md)

[Dados e relatórios do CQD](CQD-data-and-reports.md)

[Usar o CQD para gerenciar a qualidade de chamada e reunião](quality-of-experience-review-guide.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md)


[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)
