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
ms.openlocfilehash: 7d951c0e96f98c343a388e536311bf00890e5302
ms.sourcegitcommit: e38776625a3623216b0d5f092fffaff67519b1a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2022
ms.locfileid: "66056951"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Use Power BI para analisar dados CQD para Microsoft Teams

Novidade em janeiro de 2020: [baixe Power BI de consulta para CQD](https://www.microsoft.com/download/details.aspx?id=102291). Modelos Power BI personalizados que você pode usar para analisar e relatar seus dados CQD.

Para relatórios do CQD (Painel de Qualidade de Chamada) no Teams, se você preferir usar o Power BI para consultar e relatar seus dados, baixe nossos modelos de Power BI CQD. Ao abrir os modelos no Power BI, você será solicitado a entrar com suas credenciais de administrador do CQD. Você pode personalizar esses modelos de consulta e distribuí-los para qualquer pessoa em sua organização que tenha uma licença de Power BI e permissões de administrador CQD.

Antes de usar esses arquivos PBIT, você precisará instalar o [conector Power BI para Microsoft CQD](CQD-Power-BI-connector.md) usando o arquivo *MicrosoftCallQuality.pqx* incluído no [download](https://www.microsoft.com/download/details.aspx?id=102291). 

Verifique se você tem a função de acesso [CQD correta](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) para acessar os relatórios Power BI dados. 

|Pbit |Descrição |
|:----------|:---------|
|<strong>(Novo!)</strong> QER.pbit     |  O modelo QER (Relatório de Qualidade da Experiência) permite que os clientes identifiquem proativamente problemas que estão afetando a experiência de reunião e chamada do Teams antes que eles escalonem. Os relatórios também são fornecidos para permitir que os administradores respondam rapidamente ao escalonamento de problemas e ajudam a responder à pergunta: "O que aconteceu durante a reunião?"  Este modelo fornece os seguintes relatórios:</p><li>Pesquisa – habilita a pesquisa por URL de Reunião, ID de Conferência, Sub-rede ou UPN.</li><li>Detalhes da Integridade da Reunião – métricas detalhadas para uma única reunião.</li><li>Detalhes de Integridade do Usuário – métricas detalhadas para um único usuário.</li><li>Integridade de Mídia – visão geral de alto nível de KHI (Indicadores Chave de Integridade) para a reunião geral do locatário e a integridade da chamada.</li><li>Configuração de mídia – analisar falhas de configuração de mídia.</li><li>Confiabilidade de mídia – analisar problemas de confiabilidade de mídia.</li><li>Integridade de áudio/vídeo/compartilhamento – examine KHIs de nível médio para integridade de áudio, vídeo ou compartilhamento.</li><li>Detalhes de integridade de áudio/vídeo/compartilhamento – examine as métricas detalhadas sobre integridade de áudio, vídeo ou compartilhamento.</li><li>VPN – examine o impacto da VPN na integridade da reunião. (VPN estimada ou mapeada)</li><li>10 principais relatórios – identifique as áreas de problema em seu locatário.</li><li>Dailies – examine o relatório diário dos KHIs.</li><li>Uso – uso geral de reunião e chamada.</li><li>Comentários do usuário – examine os comentários da pesquisa do usuário, também conhecido como Rate My Call.</li><li>Transporte – identificar redes que estão bloqueando o UDP.</li><li>Dispositivos – examine o impacto dos dispositivos.</li><li>Clientes – examine as métricas voltadas para o cliente.</li><li>Criando dados – examine o arquivo de dados de criação no CQD.</li><li>Integridade do PSTN e Detalhes do Usuário – dois relatórios que fornecem um resumo de alto nível, bem como a integridade do usuário individual para chamadas baseadas em PSTN.</li><li>Métricas de rede – dois relatórios que exibem detalhes brutos da métrica de rede para tremulação, perda de pacotes e latência.</li>  |
|CQD Teams Atendedor Automático & Histórico da Fila de Chamadas.pbit     |  Esse modelo fornece os três relatórios a seguir:</p><li>Atendedor Automático – mostrando a análise para chamadas que vêm para seus Atendedores Automáticos.</li><li>Fila de Chamadas – mostrando a análise para chamadas que vêm para suas Filas de Chamadas.</li><li>Linha do tempo do agente – mostrando uma exibição de linha do tempo dos agentes que estão ativos em chamadas da Fila de Chamadas.</li><br>Para saber mais, leia [o Auto Attendant & Histórico da Fila de Chamadas](aa-cq-cqd-historical-reports.md). |
|CQD Helpdesk Report.pbit     |Integrando dados de compilação e EUII, este relatório foi projetado para permitir que você faça drill up de um único usuário para encontrar a causa raiz upstream de baixa qualidade de chamada para esse usuário (por exemplo, o usuário está em um prédio que está enfrentando problemas de rede). |
|CQD Location Enhanced Report.pbit     | Imaginando novamente os relatórios de localização do SPD do CQD. Inclui 9 relatórios, fornecendo informações de Qualidade de Chamada, Compilando WiFi, Confiabilidade e Rate My Call (RMC) com drill-thrus adicionais por build ou por usuário. Certifique-se de carregar os dados de compilação para maximizar sua experiência de relatório. |
|CQD Mobile Device Report.pbit     | Fornece insights especificamente ajustados para usuários de dispositivos móveis, incluindo Qualidade de Chamada, Confiabilidade e Rate My Call. Exiba relatórios de rede móvel, rede WiFi e sistema operacional móvel (Android, iOS). |
|CQD PSTN Direct Routing Report.pbit     |Fornece insights específicos para chamadas PSTN que passam pelo Roteamento Direto. Para saber mais, leia [Usando o Relatório de Roteamento Direto PSTN do CQD](CQD-PSTN-report.md). |
|CQD Summary Report.pbit     |Melhores visualizações, apresentação aprimorada, maior densidade de informações e datas sem interrupção. Esses relatórios facilitam o identificador de exceções. Analise a qualidade da chamada por local com um mapa interativo fácil de usar. Nove novos relatórios:</p>- Qualidade Geral<br>– Confiabilidade geral<br>- RMC (Classificar Minha Chamada) Geral<br>- Qualidade da Conferência<br>- Qualidade P2P<br>– Confiabilidade de conferência<br>- Confiabilidade P2P<br>- Conferência RMC<br>- RMC P2P         |
|Relatório de utilização Teams CQD.pbit     | Mostra como os usuários em sua organização estão usando Teams e quanto. Certifique-se de carregar os dados de compilação para maximizar sua experiência de relatório. Para saber mais, leia [Usar o relatório Power BI CQD para exibir Microsoft Teams utilização](CQD-teams-utilization-report.md). |
|CQD User Feedback (Rate My Call) Report.pbit     | Mostra os dados de Rate My Call de uma maneira que você pode usar facilmente para ajudar a dar suporte à chamada para sua organização. Referência cruzada com textuais para identificar oportunidades de educação do usuário final. |

> [!TIP]
> Depois de configurar seus relatórios de Power BI para dados CQD, adicione-os como uma guia a um canal. Depois de selecionar **+** em um canal, selecione **Power BI** e, em seguida, localize o relatório. Para saber mais, leia [Inserir relatório com a guia Power BI para Teams](/power-bi/service-embed-report-microsoft-teams). Lembre-se de que somente as pessoas com uma Power BI e credenciais de administrador do CQD podem acessar esses relatórios.

## <a name="related-topics"></a>Tópicos relacionados

[Dimensões e medidas disponíveis no Painel de Qualidade de Chamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no painel de qualidade da chamada](stream-classification-in-call-quality-dashboard.md)

[Configurar a Análise de Chamada do Skype for Business](set-up-call-analytics.md)

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Análise de Chamada e Painel de Qualidade de Chamadas](./monitor-call-quality-qos.md)
