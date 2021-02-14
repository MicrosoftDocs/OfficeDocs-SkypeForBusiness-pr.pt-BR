---
title: Usar o Power BI para analisar dados CQD para o Microsoft Teams
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
localization_priority: Normal
description: Use o Power BI para analisar dados CQD para o Microsoft Teams.
ms.openlocfilehash: a06a3cb76cd778c132b3e8745b279035e875f16e
ms.sourcegitcommit: f122c078b6458754500f3cc68086d6ccfa62d183
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588324"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Usar o Power BI para analisar dados CQD para o Microsoft Teams

Novo em janeiro de 2020: Baixe modelos de consulta [do Power BI para CQD.](https://www.microsoft.com/download/details.aspx?id=102291) Modelos personalizáveis do Power BI que você pode usar para analisar e relatar seus dados CQD.

Para relatórios CQD (Painel de Qualidade de Chamada) no Teams, se preferir usar o Power BI para consultar e relatar seus dados, baixe nossos modelos do CQD Power BI. Ao abrir os modelos no Power BI, você será solicitado a entrar com suas credenciais de administrador do CQD. Você pode personalizar esses modelos de consulta e distribuí-los para qualquer pessoa em sua organização que tenha uma licença do Power BI e permissões de administrador do CQD.

Antes de poder usar esses arquivos PBIT, você precisará instalar o Power BI Connector para [Microsoft CQD](CQD-Power-BI-connector.md) usando o arquivo *MicrosoftCallQuality.pqx* incluído no [download.](https://www.microsoft.com/download/details.aspx?id=102291) 

Certifique-se de ter a função de [acesso CQD correta](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) para acessar os relatórios do Power BI. 

|  |  |
|---------|---------|
|<strong>(Novo!)</strong> CQD Teams Auto Attendant & Call Queue Historical Report.pbit     |  Este modelo fornece os três relatórios a seguir:</p><li>Auto Attendant – mostrando a análise das chamadas que vêm para seus Auto Attendants.</li><li>Fila de Chamadas – mostrando a análise das chamadas que estão chegando em suas Filas de Chamadas.</li><li>Linha do tempo do agente – mostrando uma exibição de linha do tempo dos agentes que estão ativos em chamadas da Fila de Chamadas.</li><br>Para saber mais, leia [o Auto Attendant & Histórico da Fila de Chamada.](aa-cq-cqd-historical-reports.md)        |
|Relatório de Ajuda do CQD.pbit     |Integrando a construção e os dados EUII, este relatório foi projetado para permitir que você faça drill up de um único usuário para encontrar a causa raiz upstream da baixa qualidade da chamada para esse usuário (por exemplo, o usuário está em um prédio que está enfrentando problemas de rede).         |
|Relatório.pbit aprimorado de localização do CQD     | Imagine os relatórios de localização do SPD do CQD. Inclui 9 relatórios, fornecendo informações de Qualidade de Chamada, WiFi de Criação, Confiabilidade e Taxa de Chamada (RMC) com drill-thrus adicionais por Building ou por Usuário.  Certifique-se de carregar os dados de construção para maximizar sua experiência de relatório.        |
|CQD Mobile Device Report.pbit     | Fornece informações especificamente voltadas para usuários de dispositivos móveis, incluindo Qualidade de Chamada, Confiabilidade e Rate My Call. Exibir a rede móvel, a rede WiFi e os relatórios do sistema operacional móvel (Android, iOS).        |
|Relatório de Roteamento Direto PSTN CQD.pbit     |Fornece informações específicas para chamadas PSTN que passam pelo Roteamento Direto. Para saber mais, leia Usando o Relatório de Roteamento Direto [PSTN do CQD.](CQD-PSTN-report.md)         |
|Relatório de Resumo do CQD.pbit     |Melhores visualizações, apresentação aprimorada, maior densidade de informações e datas de rolagem. Esses relatórios facilitam a identificação de saída. Detalhar a qualidade da chamada por local com um mapa interativo fácil de usar. 9 novos relatórios:</p>- Qualidade Geral<br>- Confiabilidade Geral<br>- RMC (Taxa Minha Chamada) Geral<br>- Qualidade da Conferência<br>- Qualidade P2P<br>- Confiabilidade de conferência<br>- Confiabilidade P2P<br>- RMC de conferência<br>- P2P RMC         |
|<strong>(Novo!)</strong> Relatório de Utilização do CQD Teams.pbit     | Mostra como os usuários em sua organização estão usando o Teams e quanto. Certifique-se de carregar os dados de construção para maximizar sua experiência de relatório. Para saber mais, leia [o relatório Usar o Power BI do CQD para exibir o uso do Microsoft Teams.](CQD-teams-utilization-report.md)        |
|CQD User Feedback (Rate My Call) Report.pbit     | Mostra a taxa de dados Minha Chamada de uma maneira que você pode usar facilmente para ajudar a dar suporte a chamada para sua organização. Referência cruzada com verbatims para identificar oportunidades de educação do usuário final.        |

> [!TIP]
> Depois de configurar seus relatórios do Power BI para dados CQD, adicione-os como uma guia a um canal. Depois de selecionar **+** em um canal, selecione **Power BI** e, em seguida, encontre seu relatório. Para saber mais, leia [o relatório Inserir com a guia Power BI para Teams.](https://docs.microsoft.com/power-bi/service-embed-report-microsoft-teams) Lembre-se de que somente as pessoas com uma licença do Power BI e credenciais de administrador do CQD podem acessar esses relatórios.


## <a name="related-topics"></a>Tópicos relacionados

[Dimensões e medidas disponíveis no Painel de Qualidade de Chamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no painel de qualidade da chamada](stream-classification-in-call-quality-dashboard.md)

[Configurar a Análise de Chamada do Skype for Business](set-up-call-analytics.md)

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Análise de Chamada e Painel de Qualidade de Chamadas](difference-between-call-analytics-and-call-quality-dashboard.md)
 
