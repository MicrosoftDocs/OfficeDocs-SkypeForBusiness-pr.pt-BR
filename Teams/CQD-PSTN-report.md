---
title: Usando o relatório de Roteamento Direto PSTN do CQD
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
localization_priority: Normal
description: Use o relatório CQD (Painel de Qualidade de Chamada) PSTN do Microsoft Teams para monitorar e solucionar problemas de chamadas PSTN no Microsoft Teams.
ms.openlocfilehash: e4662d80dbba88c1049c7ef98569dae408ca9ba0
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583098"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a>Usando o relatório de Roteamento Direto PSTN do CQD

Novo em março de 2020, adicionamos um relatório de Roteamento Direto do CQD (Painel de Qualidade de Chamada do Microsoft Teams) aos nossos modelos de consulta do Power BI para download para [CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) 


O relatório de Roteamento Direto PSTN do CQD (CQD PSTN Direct Routing Report.pbit) ajuda você a entender os padrões de uso e a qualidade dos seus serviços PSTN. Use este relatório para monitorar o uso do serviço, informações sobre o controlador de borda de sessão (SBC), o serviço de telefonia, os parâmetros de rede e os detalhes da Taxa de Eficácia da Rede. Essas informações podem ajudá-lo a identificar problemas, incluindo o motivo das chamadas não a atender. Por exemplo, você poderá ver quando o volume cair ou quantas chamadas serão afetadas e por qual motivo.


O Relatório de Roteamento Direto PSTN do CQD tem quatro seções:

  - [Visão geral do PSTN](#pstn-overview)

  - [Detalhes do Serviço](#service-details)

  - [Taxa de Eficácia da Rede](#network-effectiveness-ratio)

  - [Parâmetros de Rede](#network-parameters)

## <a name="highlights"></a>Destaques

1. Analisar por tipo de chamada, SBC, país de chamador e destinatário

   O relatório roteamento direto PSTN do CQD agrega métricas de uso e confiabilidade para todos os SBCs em seu locatário nos últimos 7, 30 ou 180 dias (6 meses). Você pode analisar dados por tipo de chamada, SBC, país de chamador e destinatário da chamada. Se estiver interessado em um SBC ou país específico, você poderá identificar alterações nas tendências ao longo do intervalo de tempo selecionado.
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Captura de tela dos filtros disponíveis no relatório de Roteamento Direto PSTN do CQD":::
   
2. Controlar tendências

    A análise de tendências é essencial ao tentar entender o uso e a confiabilidade do serviço. As tendências de hora em hora fornecem uma olhada de perto no desempenho diário, o que ajuda a identificar incidentes em tempo real. As tendências diárias permitem que você veja a saúde do serviço de uma perspectiva de longo prazo. É importante poder se deslocar entre esses dois modos com granularidade de dados apropriada. O relatório roteamento direto PSTN do CQD fornece uma visão geral de tendências de 6 meses, tendências diárias de 7 e 30 dias e tendências por hora para que você possa analisar o desempenho em cada nível.
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Captura de tela dos gráficos de tendências no relatório de Roteamento Direto PSTN do CQD":::

3. Fazer drill through até o SBC ou nível do usuário

   Estamos criando recursos de drill-through em várias categorias de dados no CQD, o que permite entender rapidamente a distribuição de uso ou confiabilidade no nível SBC ou do usuário. Ao usar o drill through, você pode rapidamente resolver problemas e entender o impacto real do usuário. O relatório de Roteamento Direto PSTN do CQD apresenta uma análise das métricas de Detalhes do Serviço e Taxa de Eficácia da Rede. Clique no ponto de dados em que você está interessado para fazer uma análise de detalhes em nível de usuário ou SBC.
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Captura de tela mostrando o recurso de drill-through em um ponto de dados":::


## <a name="pstn-overview"></a>Visão geral do PSTN

O Relatório de Roteamento Direto PSTN do CQD fornece as seguintes informações relacionadas à saúde geral do serviço dos últimos 180 dias.
![Captura de tela: relatório CQD PSTN](media/CQD-PSTN-report1.png)

Por exemplo, se você estiver interessado no uso geral e na saúde de todas as chamadas de entrada que passam por SBC abc.bca.adatum.biz com os EUA como país interno:

| **Ligar para fora** | **Descrição**                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1            | Você pode usar os filtros na parte superior para fazer drill down e selecionar ByotIn como tipo de chamada, abc.bca.contoso.com como Controlador de Quadro de Sessão e EUA como país interno. |
| 2            | Tendência de uso dos últimos 180 dias. Você pode encontrar o relatório de detalhes de uso na página Detalhes do Serviço.                                                                     |
| 3            | Tendência pós-Atraso de Discagem, Latência, Tremida e Perda de Pacote dos últimos 180 dias. Você pode encontrar um relatório de detalhes na página Parâmetros de Rede.                           |
| 4            | Tendência de Chamada Simultânea e Usuário Ativo Diário dos últimos 180 dias. Este gráfico pode ajudá-lo a entender o volume máximo do serviço.                            |
| 5            | O Principal Motivo de Término da Chamada afetou a qualidade do serviço dos últimos 180 dias. Você pode encontrar detalhes de saúde do serviço na página Network Effective Ratio(NER).                    |

## <a name="service-details"></a>Detalhes do Serviço

Esta página fornece tendências de uso do serviço por dia e detalhamento dos comentários dos usuários por geografia.

  - **Total de Chamadas de Tentativa –** Total de chamadas de tentativa nesse intervalo de tempo, incluindo chamadas bem-sucedidas e com falha

  - **Total de Chamadas Conectadas -** Total de chamadas conectadas nesse intervalo de tempo

  - **Total de Minutos –** Uso total de minutos nesse intervalo de tempo

  - **Usuários Ativos Diários (DAU) –** Contagem de usuários ativos diários que fizeram pelo menos uma chamada conectada naquele dia

  - **Chamadas Simultâneas –** Máximo de chamadas ativas simultâneas em um minuto

  - **Comentários do Usuário –** A pontuação "Classificação minha chamada" vem do usuário. 3 a 5 é considerado uma boa chamada. 1 a 2 é considerado uma chamada ruim.

![Captura de tela: relatório CQD PSTN](media/CQD-PSTN-report2.png)

Por exemplo:

1.  Se você vir que a duração média da chamada cai para 0 em 14/02/2020, primeiro é possível verificar se o volume da chamada parece normal e ver se há uma grande discrepância entre o total de chamadas conectadas e as chamadas de tentativa totais. Em seguida, vá para a página Network Effectiveness Ratio para investir em motivos de falha de chamada.

2.  Se você vir o aumento de pontos vermelhos no mapa de comentários do usuário, pode ir para a página Network Effectiveness Ratio e o Parâmetro de Rede para ver se há alguma anômala e você pode levantar um tíquete usando o MS Service Desk.

## <a name="network-effectiveness-ratio"></a>Taxa de Eficácia da Rede

Essa é a mesma métrica que aparece no painel Saúde Geral. Você pode verificar o número de NER por hora com detalhes de chamadas afetadas para as duas direções de chamada (entrada/saída) na taxa de eficácia de rede por hora e o gráfico de motivos de término da chamada abaixo.

  - **NER** – A capacidade (%) de uma rede para fazer chamadas medindo o número de chamadas enviadas versus o número de chamadas entregues a um destinatário.

  - **Código de resposta SIP**- Um código de resposta inteiro de três dígitos mostra o status da chamada.

  - **Código de resposta da Microsoft**- Um código de resposta enviado do componente da Microsoft.

  - **Descrição** : a fase do motivo correspondente ao código de resposta SIP e ao código de resposta da Microsoft.

  - **Número de chamadas afetadas** – o número total de chamadas foi afetado durante o intervalo de tempo selecionado.

> ![Captura de tela: relatório CQD PSTN](media/CQD-PSTN-report3.png)
> 
Por exemplo:

![Captura de tela: relatório CQD PSTN](media/CQD-PSTN-report4.png)

Se o NER Diário tiver um mergulho em 05/02/2020, você poderá clicar na data e outros gráficos ampliarão para essa data específica.

![Captura de tela: relatório CQD PSTN](media/CQD-PSTN-report5.png)

No NER Good Percentage Hourly Trend, você pode descobrir que o mergulho acontece por volta das 21:00. Em seguida, clique novamente para ampliar até a hora 21 e verifique Detalhes da Chamada Efetiva para ver quantas chamadas falharam nessa hora e quais são os motivos de término da chamada. Você pode começar com problemas pessoais para resolver qualquer problema SBC ou relatar ao Service Desk se o problema não estiver relacionado ao SBC.

## <a name="network-parameters"></a>Parâmetros de Rede

Todos os parâmetros de rede são medidos da interface roteamento direto para o Controlador de Borda de Sessão. Para obter informações sobre os valores recomendados, consulte Preparar a rede da sua organização para o [Microsoft Teams](prepare-network.md)e veja a borda do cliente para os valores recomendados pelo Microsoft Edge.

  - **Jitter** – é a medida milissegunda de variação no tempo de atraso de propagação da rede calculado entre dois pontos de extremidade usando RTCP (O Protocolo de Controle RTP).

  - **Perda de pacote** – é uma medida de pacote que não conseguiu chegar; ele é calculado entre dois pontos de extremidade.

  - **Latência** - (também conhecido como tempo de viagem de ida e volta) é o tempo necessário para que um sinal seja enviado, além do tempo necessário para que o sinal seja recebido. Esse atraso consiste nos tempos de propagação entre os dois pontos de um sinal.

> ![Captura de tela: relatório CQD PSTN](media/CQD-PSTN-report6.png)

Por exemplo:

Se você vir um pico em qualquer um dos quatro gráficos (Latência, Tremência, Taxa de Perda de Pacote, Atraso Pós-Discagem) para uma data específica, por exemplo, Latência em 14/02/2020, clique no ponto de data. E o gráfico de tendências por hora na parte inferior será atualizado para mostrar o número por hora. Você pode verificar os SBCs ou levantar um tíquete com o MS Service Desk.

![Captura de tela: relatório CQD PSTN](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a>Tópicos relacionados

[Usar o Power BI para analisar dados CQD para o Microsoft Teams](CQD-PSTN-report.md)

[Solução de problemas do Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)