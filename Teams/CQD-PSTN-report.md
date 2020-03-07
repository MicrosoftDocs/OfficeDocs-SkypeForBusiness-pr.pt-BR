---
title: Usando o relatório de roteamento direto do CQD PSTN
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
description: Use o relatório de roteamento direto PSTN do CQD para monitorar e solucionar problemas de chamadas PSTN no Microsoft Teams.
ms.openlocfilehash: 32d91d56e51c5706c3e460029312f3b6bb6948c3
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559358"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a>Usando o relatório de roteamento direto do CQD PSTN

Novidades de março de 2020, adicionamos um relatório de roteamento direto de PSTN CQD a nossos [modelos de consulta para download do Power bi para CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). 


O CQD PSTN Direct Routing Report ajuda os clientes a entender os padrões de uso e a qualidade de suas informações de monitoração de serviços PSTN sobre seu SBC, o serviço de telefonia, os parâmetros de rede e os detalhes da taxa de eficácia da rede e o uso da atender. Essas informações podem ajudá-lo a identificar problemas, incluindo o motivo para as chamadas descartadas. Por exemplo, você poderá saber quando o volume será eliminado, quantas chamadas serão afetadas por qual motivo.

O relatório de roteamento direto PSTN CQD tem quatro seções:

  - [Visão geral da PSTN](#pstn-overview)

  - [Detalhes do serviço](#service-details)

  - [Taxa de eficácia da rede](#network-effectiveness-ratio)

  - [Parâmetros de rede](#network-parameters)

## <a name="pstn-overview"></a>Visão geral da PSTN

O CQD PSTN Direct Routing Report fornece as informações a seguir relacionadas à integridade geral do serviço dos últimos 180 dias.
![Captura de tela: relatório PSTN CQD](media/CQD-PSTN-report1.png)

Por exemplo, se você estiver interessado no uso geral e na integridade de todas as chamadas recebidas por meio do SBC abc.bca.adatum.biz conosco como o país interno:

| **Chame para fora** | **Descrição**                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1            | Você pode usar os filtros na parte superior para fazer drill down e selecionar ByotIn como tipo de chamada, abc.bca.contoso.com como controlador de placa de sessão e EUA como país interno. |
| 2            | Tendência de uso dos últimos 180 dias. Você pode encontrar o relatório de detalhes de uso na página de detalhes do serviço.                                                                     |
| 3            | Atraso de discagem, latência, tremulação e tendência de perda de pacote nos últimos 180 dias. Você pode encontrar um relatório detalhado na página parâmetros de rede.                           |
| 4            | Chamada simultânea e tendência de usuário ativo diário para os últimos 180 dias. Este gráfico pode ajudá-lo a entender o volume máximo do serviço.                            |
| 5            | Melhor motivo de término de chamada afetado qualidade do serviço dos últimos 180 dias. Você pode encontrar detalhes de integridade do serviço na página de índice efetivo de rede (NER).                    |

## <a name="service-details"></a>Detalhes do serviço

Esta página fornece as tendências de uso de serviço por dia e a divisão de comentários do usuário por meio do meio geográfico.

  - **Total de chamadas de tentativa –** Total de chamadas de tentativa nesse intervalo de tempo, incluindo tanto êxito como chamadas com falha

  - **Total de chamadas conectadas-** Total de chamadas conectadas nesse intervalo de tempo

  - **Total de minutos –** Uso total de minutos nesse intervalo de tempo

  - **Usuários ativos diariamente (DAU) –** Contagem de usuários ativos diários que fizeram pelo menos uma chamada conectada nesse dia

  - **Chamadas simultâneas –** Máximo de chamadas ativas simultâneas em um minuto

  - **Comentários do usuário –** A pontuação "classificar minha chamada" vem do usuário. 3-5 é considerado uma boa chamada. 1-2 é considerado como uma chamada incorreta.

![Captura de tela: relatório PSTN CQD](media/CQD-PSTN-report2.png)

Por exemplo:

1.  Se você vir as quedas médias de duração da chamada para 0 no 02/14/2020, você pode primeiro verificar se o volume da chamada está normal e ver se há uma grande discrepância entre o total de chamadas do Connect e as chamadas de tentativas totais. Em seguida, acesse a página de razão da eficácia da rede para investir em motivos de falha na chamada.

2.  Se vir o aumento dos pontos vermelhos no mapa de comentários do usuário, você poderá acessar a página de índice de eficácia da rede e o parâmetro de rede para ver se há anomalias e se você pode disparar um bilhete usando o MS Service Desk.

## <a name="network-effectiveness-ratio"></a>Taxa de eficácia da rede

Esta é a mesma métrica que aparece no painel de integridade geral. Você pode verificar o número de NER por hora com os detalhes das chamadas afetadas para as direções da chamada (de entrada/saída) na taxa de eficácia horária da rede e no gráfico de motivo de término da chamada abaixo.

  - **Ner** – a capacidade (%) de uma rede para entregar chamadas medindo o número de chamadas enviadas versus o número de chamadas entregues a um destinatário.

  - **Código de resposta SIP**-um código de resposta de inteiro de três dígitos mostra o status da chamada.

  - **Código de resposta da Microsoft**-um código de resposta enviado do componente da Microsoft.

  - **Descrição** – a fase de motivo correspondente ao código de resposta SIP e ao código de resposta da Microsoft.

  - **Número de chamadas afetadas** – o número total de chamadas que você tem afetado durante o intervalo de tempo selecionado.

> ![Captura de tela: relatório PSTN CQD](media/CQD-PSTN-report3.png)
> 
Por exemplo:

![Captura de tela: relatório PSTN CQD](media/CQD-PSTN-report4.png)

Se o NER diário tiver um DIP no 02/05/2020, você poderá clicar na data e outros gráficos serão ampliados para essa data específica.

![Captura de tela: relatório PSTN CQD](media/CQD-PSTN-report5.png)

Na NER boa porcentagem de tendência horária, você pode encontrar o DIP em torno de 21:00. Em seguida, clique novamente para aplicar zoom à hora 21 e verificar detalhes de chamadas afetadas para ver quantas chamadas falharam nessa hora e quais são os motivos de término da chamada. Você pode começar com a solução de problemas do SBC em qualquer problema de SBC ou relatório para o serviço de suporte se o problema não estiver relacionado ao SBC.

## <a name="network-parameters"></a>Parâmetros de rede

Todos os parâmetros de rede são medidos da interface de roteamento direto para o controlador de borda de sessão. Para obter informações sobre os valores recomendados, consulte [preparar a rede da sua organização para o Microsoft Teams](prepare-network.md)e verificar os valores recomendados de borda do cliente para o Microsoft Edge.

  - **Tremulação** – é a medida de milissegundos da variação no tempo de atraso de propagação de rede calculado entre dois pontos de extremidade usando RTCP (o protocolo de controle RTP).

  - **Perda de pacotes** – é uma medida do pacote que falhou ao chegar; Ele é calculado entre dois pontos de extremidade.

  - **Latência** -(também conhecido como tempo de viagem de ida e volta) é o período de tempo que leva para o envio de um sinal mais o tempo necessário para que a confirmação daquele sinal seja recebida. Esse atraso de tempo consiste nos tempos de propagação entre os dois pontos de um sinal.

> ![Captura de tela: relatório PSTN CQD](media/CQD-PSTN-report6.png)

Por exemplo:

Se você vir um pico em qualquer um dos quatro gráficos (latência, tremulação, taxa de perda de pacote, atraso de discagem automática) para uma data específica, por exemplo, latência em 02/14/2020, clique no ponto de data. O gráfico de tendências horárias na parte inferior será atualizado para mostrar o número por hora. Você pode verificar o SBCs ou disparar um bilhete com o MS Service Desk.

![Captura de tela: relatório PSTN CQD](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a>Tópicos relacionados

[Usar o Power BI para analisar dados do CQD para o Microsoft Teams](CQD-PSTN-report.md)