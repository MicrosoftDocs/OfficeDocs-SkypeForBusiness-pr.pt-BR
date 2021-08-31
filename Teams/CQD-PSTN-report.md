---
title: Usando o relatório de Roteamento Direto PSTN PSTN
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies, fan.fan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
description: Use o Microsoft Teams de Qualidade de Chamada (CQD)) relatório de Roteamento Direto PSTN para monitorar e solucionar problemas de chamadas PSTN no Microsoft Teams.
ms.openlocfilehash: ae36ff214de2142b74b8493e925e25f32572709c
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726420"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a>Usando o relatório de Roteamento Direto PSTN PSTN

Novo em março de 2020, adicionamos um relatório de Roteamento Direto do Painel de Qualidade de Chamada (CQD) Microsoft Teams PSTN para nossos modelos de consulta Power BI para download para [CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). 


O relatório de Roteamento Direto PSTN (CQD PSTN Direct Routing Report.pbit) ajuda você a entender os padrões de uso e a qualidade dos seus serviços PSTN. Use este relatório para monitorar o uso do serviço, informações sobre seu Controlador de Borda de Sessão (SBC), o serviço de telefonia, os parâmetros de rede e os detalhes da Taxa de Eficácia de Rede. Essas informações podem ajudá-lo a identificar problemas, incluindo o motivo das chamadas não a atender. Por exemplo, você poderá ver quando o volume cair ou quantas chamadas serão afetadas e por qual motivo.


O Relatório de Roteamento Direto PSTN do CQD tem quatro seções:

  - [Visão geral do PSTN](#pstn-overview)

  - [Detalhes do serviço](#service-details)

  - [Taxa de eficácia da rede](#network-effectiveness-ratio)

  - [Parâmetros de rede](#network-parameters)

## <a name="highlights"></a>Realçadores

1. Analisar por tipo de chamada, SBC, país chamador e chamador

   O relatório de Roteamento Direto PSTN do CQD agrega métricas de confiabilidade e uso para todos os SBCs em seu locatário nos últimos 7, 30 ou 180 dias (6 meses). Você pode analisar dados por tipo de chamada, SBC, país de chamador e chamador. Se você estiver interessado em um determinado SBC ou país, poderá identificar alterações nas tendências ao longo do intervalo de tempo selecionado.
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Captura de tela dos filtros disponíveis no relatório de Roteamento Direto do PSTN do CQD.":::
   
2. Acompanhar tendências

    A análise de tendências é essencial ao tentar entender o uso e a confiabilidade do serviço. As tendências de hora em hora fornecem uma olhada de perto no desempenho diário, o que ajuda a identificar incidentes em tempo real. As tendências diárias permitem que você veja a saúde do serviço de uma perspectiva de longo prazo. É importante poder mudar entre esses dois modos com granularidade de dados apropriada. O relatório de Roteamento Direto PSTN do CQD fornece uma visão geral de tendências de 6 meses, tendências diárias de 7 e 30 dias e tendências por hora para que você possa analisar o desempenho em cada nível.
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Captura de tela dos gráficos de tendências no relatório de Roteamento Direto do PSTN do CQD.":::

3. Faça uma análise de SBC ou nível do usuário

   Estamos criando recursos de análise em várias categorias de dados no CQD, o que permite entender rapidamente a distribuição de uso ou confiabilidade no nível SBC ou do usuário. Usando o drill through, você pode rapidamente resolver problemas e entender o impacto real do usuário. Os recursos do relatório de Roteamento Direto do PSTN do CQD são detalhados nas métricas Detalhe do Serviço e Taxa de Eficácia da Rede. Clique no ponto de dados em que você está interessado para fazer uma análise de detalhes no nível do usuário ou SBC.
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Captura de tela mostrando a funcionalidade de drill-through em um ponto de dados.":::


## <a name="pstn-overview"></a>Visão geral do PSTN

O Relatório de Roteamento Direto PSTN do CQD fornece as seguintes informações relacionadas à saúde geral do serviço nos últimos 180 dias.
![Captura de tela: relatório CQD PSTN.](media/CQD-PSTN-report1.png)

Por exemplo, se você estiver interessado no uso geral e na saúde sobre todas as chamadas de entrada que passam pelo SBC abc.bca.adatum.biz com os EUA como o país interno:

| **Chamada** | **Descrição**                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1            | Você pode usar os filtros na parte superior para detalhar e selecionar ByotIn como tipo de chamada, abc.bca.contoso.com como Controlador de Quadro de Sessão e EUA como país interno. |
| 2            | Tendência de uso dos últimos 180 dias. Você pode encontrar o relatório de detalhes de uso na página Detalhes do Serviço.                                                                     |
| 3            | Tendência de atraso, latência, tremência e perda de pacotes nos últimos 180 dias. Você pode encontrar o relatório detalhado na página Parâmetros de Rede.                           |
| 4            | Tendência de Chamada Simultânea e Usuário Ativo Diário nos últimos 180 dias. Este gráfico pode ajudá-lo a entender o volume máximo do serviço.                            |
| 5            | Motivo de término de chamada superior afetou a qualidade do serviço nos últimos 180 dias. Você pode encontrar detalhes de saúde do serviço na página Network Effective Ratio(NER).                    |

## <a name="service-details"></a>Detalhes do serviço

Esta página fornece tendências de uso do serviço por dia e análise de comentários do usuário por geográfico.

  - **Total de chamadas de tentativa –** Total de chamadas de tentativa nesse intervalo de tempo, incluindo chamadas bem-sucedidas e com falha

  - **Total de chamadas conectadas -** Total de chamadas conectadas nesse intervalo de tempo

  - **Total de Minutos –** Uso total de minutos nesse intervalo de tempo

  - **Dau (Daily Active Users) –** Contagem de usuários ativos diários que fizeram pelo menos uma chamada conectada nesse dia

  - **Chamadas simultâneas –** Máximo de chamadas ativas simultâneas em um minuto

  - **Comentários do usuário –** A pontuação "Rate My Call" vem do usuário. 3 a 5 é considerado uma boa chamada. 1-2 é considerado como uma chamada ruim.

![Captura de tela: relatório CQD PSTN.](media/CQD-PSTN-report2.png)

Por exemplo:

1.  Se você vir que a duração média da chamada cai para 0 em 14/02/2020, primeiro você pode verificar se o volume da chamada parece normal e ver se há uma grande discrepância entre o total de chamadas de conexão e o total de chamadas de tentativa. Em seguida, vá para a página Taxa de Eficácia de Rede para investir em motivos de falha de chamada.

2.  Se você vir o aumento de pontos vermelhos no mapa de comentários do usuário, poderá ir para a página Taxa de Eficácia de Rede e Parâmetro de Rede para ver se há alguma anomalia e você pode levantar um tíquete usando o MS Service Desk.

## <a name="network-effectiveness-ratio"></a>Taxa de eficácia da rede

Essa é a mesma métrica que aparece no painel Saúde Geral. Você pode verificar o número de NER por hora com os detalhes de chamadas afetadas para ambas as direções de chamada (entrada/saída) na taxa de eficácia da rede por hora e gráfico de motivos de término de chamada abaixo.

  - **NER** - A capacidade (%) de uma rede de fazer chamadas medindo o número de chamadas enviadas versus o número de chamadas entregues a um destinatário.

  - **Código de resposta SIP**- Um código de resposta inteiro de três dígitos mostra o status da chamada.

  - **Código de resposta da Microsoft**- Um código de resposta enviado do componente microsoft.

  - **Descrição** – A fase do motivo que corresponde ao código de resposta SIP e ao código de resposta da Microsoft.

  - **Número de chamadas afetadas** – O número total de chamadas foi afetada durante o intervalo de tempo selecionado.

> ![Captura de tela: relatório CQD PSTN.](media/CQD-PSTN-report3.png)
> 
Por exemplo:

![Captura de tela: relatório CQD PSTN.](media/CQD-PSTN-report4.png)

Se o NER Diário tiver um dip em 05/02/2020, você poderá clicar na data e outros gráficos aumentarão para essa data específica.

![Captura de tela: relatório CQD PSTN.](media/CQD-PSTN-report5.png)

No NER Good Percentage Hourly Trend, você pode encontrar que o dip acontece por volta das 21:00. Em seguida, clique novamente para ampliar para a hora 21 e verifique Detalhes da Chamada Efetiva para ver quantas chamadas falharam nessa hora e quais são os motivos de término da chamada. Você pode começar com disparos de autoprofissão em qualquer problema SBC ou relatar ao Service Desk se o problema não estiver relacionado ao SBC.

## <a name="network-parameters"></a>Parâmetros de rede

Todos os parâmetros de rede são medidos da interface roteamento direto para o Controlador de Borda de Sessão. Para obter informações sobre os valores recomendados, consulte Prepare your [organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.

  - **Tremido** – É a medida milissegunda de variação no tempo de atraso de propagação da rede calculada entre dois pontos de extremidade usando RTCP (O Protocolo de Controle RTP).

  - **Perda de pacotes** – é uma medida de pacote que falhou ao chegar; ele é calculado entre dois pontos de extremidade.

  - **Latência** - (Também conhecido como tempo de viagem de ida e volta) é o tempo necessário para que um sinal seja enviado mais o tempo necessário para o reconhecimento desse sinal ser recebido. Esse atraso de tempo consiste nos tempos de propagação entre os dois pontos de um sinal.

> ![Captura de tela: relatório CQD PSTN.](media/CQD-PSTN-report6.png)

Por exemplo:

Se você vir um pico em qualquer um dos quatro gráficos (Latência, Tremência, Taxa de Perda de Pacote, Atraso pós-discagem) para uma data específica, por exemplo, Latência em 14/02/2020, clique no ponto de data. E o gráfico de tendências por hora na parte inferior será atualizado para mostrar o número por hora. Você pode verificar os SBCs ou levantar um tíquete com o MS Service Desk.

![Captura de tela: relatório CQD PSTN.](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a>Tópicos relacionados

[Use Power BI para analisar dados CQD para Microsoft Teams](CQD-PSTN-report.md)

[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)