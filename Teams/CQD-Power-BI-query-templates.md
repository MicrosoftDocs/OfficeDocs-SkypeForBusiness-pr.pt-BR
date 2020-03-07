---
title: Usar o Power BI para analisar dados do CQD para o Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Use o Power BI para analisar dados do CQD para o Microsoft Teams.
ms.openlocfilehash: d737f321ea8684ffe99b50575b1b2e8d044804d0
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559360"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Usar o Power BI para analisar dados do CQD para o Microsoft Teams

Novidades em janeiro de 2020: [Baixe os modelos de consulta do Power bi para CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modelos personalizáveis do Power BI que você pode usar para analisar e relatar seus dados do CQD.

Para os relatórios do CQD no Microsoft Teams, se você preferir usar o Power BI para consultar e relatar seus dados, baixe os modelos do Power BI do CQD. Ao abrir os modelos no Power BI, você será solicitado a entrar com as credenciais de administrador do CQD. Você pode personalizar esses modelos de consulta e distribuí-los para qualquer pessoa em sua organização que tenha uma licença do Power BI e permissões de administrador do CQD.

Antes de poder usar esses arquivos PBIX, você precisará [instalar o conector do Power bi para Microsoft CQD](CQD-Power-BI-connector.md) usando o arquivo *MicrosoftCallQuality. pqx* incluído no [Download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). 


|  |  |
|---------|---------|
|Relatório de assistência técnica CQD. pbix     |Ao integrar dados de construção e EUII, esse relatório foi projetado para permitir que você faça uma busca detalhada de um único usuário para localizar a causa raiz de upstreams de baixa qualidade de chamadas para aquele usuário (por exemplo, o usuário está em um prédio com problemas de rede).         |
|CQD de relatório de localização avançada do local. pbix     | Renovar relatórios de localização SPD do CQD. Inclui 9 relatórios, fornecimento de qualidade de chamada, criação de WiFi, confiabilidade e classificar minhas informações de chamada (RMC) com buscas adicionais por meio do edifício ou pelo usuário.        |
|Relatório de dispositivo móvel CQD. pbix     | Fornece ideias especificamente ajustadas em relação a usuários de dispositivos móveis, incluindo qualidade da chamada, confiabilidade e classifique minha chamada. Exibir relatórios de rede móvel, rede WiFi e sistema operacional móvel (Android, iOS).        |
|CQD o relatório de roteamento direto PSTN. pbix     |Fornece ideias específicas para chamadas PSTN que passam pelo roteamento direto. Para saber mais, leia [usando o relatório de roteamento direto PSTN CQD](CQD-PSTN-report.md).         |
|Relatório de resumo CQD. pbix     |Melhores visualizações, apresentação aprimorada, maior densidade de informações e datas de rolagem. Esses relatórios facilitam a identificação de exceções. Analise a qualidade da chamada por local com um mapa interativo fácil de usar. 9 novos relatórios:</p>-Qualidade geral<br>-Confiabilidade geral<br>-RMC (classifique minha chamada em geral)<br>-Qualidade de conferência<br>-Qualidade P2P<br>-Confiabilidade da conferência<br>-Confiabilidade P2P<br>-Conferência RMC<br>-RMC P2P         |
|**(Novo!)** Relatório de utilização do teams CQD. pbix     | Mostra como os usuários em sua organização estão usando o Teams e o quanto. Para saber mais, leia [use o relatório do Power bi do CQD para exibir a utilização do Microsoft Teams](CQD-teams-utilization-report.md).        |
|CQD comentários do usuário (classifique minha chamada) Report. pbix     | Mostra os dados de Tarifa de minha chamada de forma que você possa usar facilmente para ajudar a fazer chamadas para a sua organização. Referência cruzada com as literalmente para identificar oportunidades de educação do usuário final.        |


## <a name="related-topics"></a>Tópicos relacionados

[Dimensões e medidas disponíveis no Painel de Qualidade de Chamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no painel de qualidade da chamada](stream-classification-in-call-quality-dashboard.md)

[Configurar a Análise de Chamada do Skype for Business](set-up-call-analytics.md)

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Análise de Chamada e Painel de Qualidade de Chamadas](difference-between-call-analytics-and-call-quality-dashboard.md)
 