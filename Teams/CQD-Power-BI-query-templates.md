---
title: Usar o Power BI para analisar dados do CQD para o Microsoft Teams
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
description: Use o Power BI para analisar dados do CQD para o Microsoft Teams.
ms.openlocfilehash: a06a3cb76cd778c132b3e8745b279035e875f16e
ms.sourcegitcommit: f122c078b6458754500f3cc68086d6ccfa62d183
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588324"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Usar o Power BI para analisar dados do CQD para o Microsoft Teams

Novidades em janeiro de 2020: [Baixe os modelos de consulta do Power bi para CQD](https://www.microsoft.com/download/details.aspx?id=102291). Modelos personalizáveis do Power BI que você pode usar para analisar e relatar seus dados do CQD.

Para os relatórios do painel de qualidade de chamada (CQD) no Microsoft Teams, se você preferir usar o Power BI para consultar e relatar seus dados, baixe os modelos do Power BI do CQD. Ao abrir os modelos no Power BI, você será solicitado a entrar com as credenciais de administrador do CQD. Você pode personalizar esses modelos de consulta e distribuí-los para qualquer pessoa em sua organização que tenha uma licença do Power BI e permissões de administrador do CQD.

Antes de poder usar esses arquivos do PBIT, você precisará [instalar o conector do Power bi para Microsoft CQD](CQD-Power-BI-connector.md) usando o arquivo *MicrosoftCallQuality. pqx* incluído no [Download](https://www.microsoft.com/download/details.aspx?id=102291). 

Verifique se você tem a [função de acesso CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) certa para acessar os relatórios do Power bi. 

|  |  |
|---------|---------|
|<strong>(Novo!)</strong> Atendedor automático do teams CQD & relatório histórico de filas de chamadas. PBit     |  Este modelo fornece os três relatórios a seguir:</p><li>Atendedor automático – mostrando a análise de chamadas que chegam aos atendedores automáticos.</li><li>Fila de chamadas – mostrando a análise de chamadas que chegam às suas filas de chamadas.</li><li>Linha do tempo do agente – mostrar um modo de exibição de linha do tempo dos agentes ativos nas chamadas da fila de chamadas.</li><br>Para saber mais, leia [atendedor automático & relatório histórico histórico da fila de chamadas](aa-cq-cqd-historical-reports.md).        |
|Relatório de assistência técnica CQD. PBit     |Ao integrar dados de construção e EUII, esse relatório foi projetado para permitir que você faça uma busca detalhada de um único usuário para localizar a causa raiz de upstreams de baixa qualidade de chamadas para aquele usuário (por exemplo, o usuário está em um prédio com problemas de rede).         |
|Relatório avançado de localização CQD. PBit     | Renovar relatórios de localização SPD do CQD. Inclui 9 relatórios, fornecimento de qualidade de chamada, criação de WiFi, confiabilidade e classificar minhas informações de chamada (RMC) com buscas adicionais por meio do edifício ou pelo usuário.  Certifique-se de carregar os dados de construção para maximizar sua experiência com relatórios.        |
|Relatório de dispositivo móvel CQD. PBit     | Fornece ideias especificamente ajustadas em relação a usuários de dispositivos móveis, incluindo qualidade da chamada, confiabilidade e classifique minha chamada. Exibir relatórios de rede móvel, rede WiFi e sistema operacional móvel (Android, iOS).        |
|CQD o relatório de roteamento direto PSTN. PBit     |Fornece ideias específicas para chamadas PSTN que passam pelo roteamento direto. Para saber mais, leia [usando o relatório de roteamento direto PSTN CQD](CQD-PSTN-report.md).         |
|Relatório de resumo CQD. PBit     |Melhores visualizações, apresentação aprimorada, maior densidade de informações e datas de rolagem. Esses relatórios facilitam a identificação de exceções. Analise a qualidade da chamada por local com um mapa interativo fácil de usar. 9 novos relatórios:</p>-Qualidade geral<br>-Confiabilidade geral<br>-RMC (classifique minha chamada em geral)<br>-Qualidade de conferência<br>-Qualidade P2P<br>-Confiabilidade da conferência<br>-Confiabilidade P2P<br>-Conferência RMC<br>-RMC P2P         |
|<strong>(Novo!)</strong> Relatório de utilização do teams CQD. PBit     | Mostra como os usuários em sua organização estão usando o Teams e o quanto. Certifique-se de carregar os dados de construção para maximizar sua experiência com relatórios. Para saber mais, leia [use o relatório do Power bi do CQD para exibir a utilização do Microsoft Teams](CQD-teams-utilization-report.md).        |
|Relatório de comentários do usuário do CQD (classificar minha chamada). PBit     | Mostra os dados de Tarifa de minha chamada de forma que você possa usar facilmente para ajudar a fazer chamadas para a sua organização. Referência cruzada com as literalmente para identificar oportunidades de educação do usuário final.        |

> [!TIP]
> Depois de configurar seus relatórios do Power BI para dados do CQD, adicione-os como uma guia a um canal. Depois de selecionar **+** em um canal, selecione **Power bi** e localize seu relatório. Para saber mais, leia [Inserir relatório com a guia Power bi para Teams](https://docs.microsoft.com/power-bi/service-embed-report-microsoft-teams). Lembre-se: somente as pessoas com uma licença do Power BI e credenciais de administrador do CQD podem acessar esses relatórios.


## <a name="related-topics"></a>Tópicos relacionados

[Dimensões e medidas disponíveis no Painel de Qualidade de Chamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no painel de qualidade da chamada](stream-classification-in-call-quality-dashboard.md)

[Configurar a Análise de Chamada do Skype for Business](set-up-call-analytics.md)

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Análise de Chamada e Painel de Qualidade de Chamadas](difference-between-call-analytics-and-call-quality-dashboard.md)
 
