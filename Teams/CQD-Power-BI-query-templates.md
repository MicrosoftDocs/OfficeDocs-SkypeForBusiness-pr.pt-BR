---
title: Use Power BI para analisar dados CQD para Microsoft Teams
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- remotework
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
description: Use Power BI para analisar dados CQD para Microsoft Teams.
ms.openlocfilehash: 4a96a53454f1f4d89feed3ea87342a7991d7975c
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013765"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Use Power BI para analisar dados CQD para Microsoft Teams

Novidade em janeiro de 2020: [Baixar Power BI de consulta para CQD](https://www.microsoft.com/download/details.aspx?id=102291). Modelos de Power BI personalizáveis que você pode usar para analisar e relatar seus dados CQD.

Para relatórios do CQD (Painel de Qualidade de Chamada) no Teams, se você preferir usar o Power BI para consultar e relatar seus dados, baixe nossos modelos de Power BI CQD. Ao abrir os modelos no Power BI, você será solicitado a entrar com suas credenciais de administrador do CQD. Você pode personalizar esses modelos de consulta e distribuí-los para qualquer pessoa em sua organização que tenha uma licença Power BI e permissões de administrador do CQD.

Antes de poder usar esses arquivos PBIT, você precisará instalar o conector de Power BI [para o Microsoft CQD](CQD-Power-BI-connector.md) usando o arquivo *MicrosoftCallQuality.pqx* incluído no [download](https://www.microsoft.com/download/details.aspx?id=102291). 

Certifique-se de ter a função de acesso [CQD correta](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) para acessar os relatórios Power BI dados. 

|&nbsp;|&nbsp;|
|---------|---------|
|<strong>(Novo!)</strong> CQD Teams Atendedor Automático & Relatório Histórico da Fila de Chamada.pbit     |  Este modelo fornece os três relatórios a seguir:</p><li>Atendedor Automático – mostrando a análise das chamadas que vêm para seus Assistentes Automáticos.</li><li>Fila de Chamadas – mostrando a análise das chamadas que vêm em suas Filas de Chamadas.</li><li>Linha do tempo do agente – mostrando uma exibição de linha do tempo dos agentes que estão ativos em chamadas de Fila de Chamadas.</li><br>Para saber mais, leia Atendedor Automático & Relatório Histórico [da Fila de Chamada.](aa-cq-cqd-historical-reports.md)        |
|CQD Helpdesk Report.pbit     |Integrando dados de construção e EUII, este relatório foi projetado para permitir que você faça a pesquisa de um único usuário para encontrar a causa raiz upstream da qualidade de chamada ruim para esse usuário (por exemplo, o usuário está em um edifício que está enfrentando problemas de rede).         |
|CQD Location Enhanced Report.pbit     | Re-imaginar relatórios de localização do SPD do CQD. Inclui 9 relatórios, fornecendo informações de Qualidade de Chamada, WiFi de Criação, Confiabilidade e Taxa de Chamada (RMC) com drill-thrus adicionais por building ou por usuário.  Certifique-se de carregar os dados de construção para maximizar sua experiência de relatórios.        |
|CQD Mobile Device Report.pbit     | Fornece informações especificamente ajustadas para usuários de dispositivos móveis, incluindo Qualidade de Chamada, Confiabilidade e Rate My Call. Exibir relatórios de rede móvel, rede WiFi e sistema operacional móvel (Android, iOS).        |
|CQD PSTN Direct Routing Report.pbit     |Fornece informações específicas para chamadas PSTN que passam por Roteamento Direto. Para saber mais, leia [Using the CQD PSTN Direct Routing Report](CQD-PSTN-report.md).         |
|Relatório de Resumo do CQD.pbit     |Visualizações melhores, apresentação aprimorada, maior densidade de informações e datas de lançamento. Esses relatórios facilitam a identificação de outliers. Detalhar a qualidade da chamada por local com um mapa interativo fácil de usar. 9 novos relatórios:</p>- Qualidade Geral<br>- Confiabilidade geral<br>- RMC (Taxa minha chamada) Geral<br>- Qualidade da Conferência<br>- Qualidade P2P<br>- Confiabilidade de Conferência<br>- Confiabilidade P2P<br>- RMC de conferência<br>- RMC P2P         |
|<strong>(Novo!)</strong> CQD Teams Relatório de Utilização.pbit     | Mostra como os usuários em sua organização estão usando Teams e quanto. Certifique-se de carregar os dados de construção para maximizar sua experiência de relatórios. Para saber mais, [leia Use CQD Power BI relatório para exibir Microsoft Teams utilização](CQD-teams-utilization-report.md).        |
|CQD User Feedback (Rate My Call) Report.pbit     | Mostra Rate My Call data de uma maneira que você pode usar facilmente para ajudar a dar suporte à chamada para sua organização. Referência cruzada com verbatims para identificar oportunidades de educação do usuário final.        |

> [!TIP]
> Depois de configurar seus relatórios de Power BI para dados CQD, adicione-os como uma guia a um canal. Depois de selecionar **+** em um canal, selecione **Power BI** e encontre seu relatório. Para saber mais, leia [Embed report with the Power BI tab for Teams](/power-bi/service-embed-report-microsoft-teams). Lembre-se de que somente as pessoas com uma Power BI e credenciais de administrador do CQD podem acessar esses relatórios.


## <a name="related-topics"></a>Tópicos relacionados

[Dimensões e medidas disponíveis no Painel de Qualidade de Chamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no painel de qualidade da chamada](stream-classification-in-call-quality-dashboard.md)

[Configurar a Análise de Chamada do Skype for Business](set-up-call-analytics.md)

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Análise de Chamada e Painel de Qualidade de Chamadas](./monitor-call-quality-qos.md)
