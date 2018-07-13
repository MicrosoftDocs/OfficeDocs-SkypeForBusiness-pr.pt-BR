---
title: Classificação de fluxo no Painel de Qualidade de Chamadas
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Saiba como a qualidade do fluxo é classificada no Painel de Qualidade de Chamadas para o Microsoft Teams e o Skype for Business Online.
ms.openlocfilehash: 6cd19fb1f163f6e7a9e11598b03f539b5fc1a02d
ms.sourcegitcommit: 411d59a92ad73555cf39d9c64822b24240b5af8a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2018
ms.locfileid: "20327074"
---
# <a name="stream-classification-in-call-quality-dashboard"></a>Classificação de fluxo no Painel de Qualidade de Chamadas

Com o PQC (Painel de Qualidade de Chamadas) para o Microsoft Teams e Skype for Business Online, você tem acesso a informações sobre a qualidade das chamadas feitas usando os serviços do Microsoft Teams e do Skype for Business. Este tópico fornece informações detalhadas sobre a classificação de qualidade dos fluxos de mídia. Para saber mais sobre o PQC e como habilitá-lo, veja [Ativar e usar o Painel de Qualidade de Chamadas](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Definições do classificador

Os fluxos no CQD são classificados como bons, ruins ou não classificados com base nos valores das principais métricas de qualidade disponíveis. As métricas e condições usadas para classificar o fluxo são mostradas nas tabelas abaixo. As dimensões "Ruim devido a" do CQD podem ser usadas para entender qual métrica é responsável por uma classificação ruim. Veja [Dimensões e medidas disponíveis no Painel de Qualidade de Chamadas](dimensions-and-measures-available-in-call-quality-dashboard.md) para mais informações sobre essas dimensões.

### <a name="audio-classifier"></a>Classificador de áudio

Um fluxo de áudio é marcado como ruim se uma ou mais das seguintes condições forem atendidas:

|**Métrica**|**Condição**|**Explicação**|
|:-----|:-----|:-----|
|Média de degradação de áudio|> 1,0|Média da degradação da pontuação média de opinião sobre a rede para transmissão. Representa o quanto a perda e a tremulação da rede afetou a qualidade do áudio recebido.|
|Viagem de ida e volta|> 500|Tempo médio da viagem de ida e volta de propagação da rede calculado conforme especificado em RFC3550 em milissegundos.|
|Taxa de perda de pacotes|> 0,1|Taxa média de perda de pacotes da transmissão.|
|Tremulação|> 30|Média de tremulação para transmissão em milissegundos.|
|Taxa média de amostras ocultas|> 0,07|Taxa média do número de quadros de áudio com amostras ocultas geradas por recuperação de perda de pacotes para o número total de quadros de áudio.|

### <a name="video-classifier"></a>Classificador de Vídeo

Um fluxo de vídeo é marcado como bom ou ruim com base no valor da primeira métrica disponível na seguinte ordem:

|**Etapa Nº**|**Métrica**|**Condição**|**Classificação se a condição for verdadeira**|**Classificação se a condição for falsa**|**Classificação se a métrica não estiver disponível**|**Explicação**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Média percentual de perda de quadros de vídeo locais|> 50% |Ruim|Bom|Seguir para a Etapa 2|Porcentagem média da perda dos quadros de vídeo conforme exibido para o usuário. Isso inclui quadros recuperados das perdas de rede.|
|2|Média da taxa de quadros de vídeo|<7|Ruim|Bom|Seguir para a Etapa 3|Média de quadros por segundo recebidos para uma transmissão de vídeo calculados durante a sessão.|
|3|Postagem de vídeo FECPLR|> 0,15|Ruim|Bom|Não classificado|Taxa de perda de pacotes após a aplicação de FEC ter sido agregada em todos as transmissões e codecs de vídeo.|

### <a name="vbss-classifier"></a>Classificador VBSS

Um fluxo VBSS é marcado como bom ou ruim com base no valor da primeira métrica disponível na seguinte ordem:

|**Etapa Nº**|**Métrica**|**Condição**|**Classificação se a condição for verdadeira**|**Classificação se a condição for falsa**|**Classificação se a métrica não estiver disponível**|**Explicação**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Média percentual de perda de quadros de vídeo locais|> 50% |Ruim|Bom|Seguir para a Etapa 2|Porcentagem média da perda dos quadros de vídeo conforme exibido para o usuário. Isso inclui quadros recuperados das perdas de rede.|
|2|Média da taxa de quadros de vídeo|< 2|Ruim|Bom|Seguir para a Etapa 3|Média de quadros por segundo recebidos para uma transmissão de vídeo calculados durante a sessão.|
|3|Postagem de vídeo FECPLR|> 0,15|Ruim|Bom|Não classificado|Taxa de perda de pacotes após a aplicação de FEC ter sido agregada em todos as transmissões e codecs de vídeo.|

### <a name="application-sharing-classifier"></a>Classificador de compartilhamento de aplicativos

Um fluxo de compartilhamento de aplicativo é marcado como ruim se uma ou mais das seguintes condições forem atendidas:

**Métrica**|**Condição**|**Explicação**|
|:-----|:-----|:-----|
|Total percentual de blocos danificados|>36|Percentual de blocos que são descartados em vez de serem enviados para um par remoto (por exemplo, da MCU para um visualizador). Os blocos descartados podem ser causados por restrições de largura de banda entre o cliente e o servidor.|
|Média de latência de processamento de blocos RDP no Compartilhamento de Aplicativo|> 400|Média de latência de blocos de processamento em milissegundos na pilha RDP no servidor de conferência.|
|Média unidirecional relativa do compartilhamento de aplicativo|> 1,75|Média de atraso unidirecional relativo entre os pontos de extremidade em milissegundos para fluxos de compartilhamento de aplicativo.|

## <a name="unclassified-streams"></a>Fluxos não classificados

No CQD, um fluxo é marcado como não classificado quando a conectividade do ICE falha ou quando todas as métricas necessárias para calcular a classificação do fluxo não são relatadas.

Para verificar se há falhas de conectividade ICE, examine as dimensões "Ice de primeira conectividade" e "Ice de segunda conectividade" em busca de um valor "FALHOU". Se um dos valores indicar uma falha, o fluxo será marcado como não classificado.

Se a conectividade ICE for bem-sucedida para um fluxo não classificado, o fluxo provavelmente será considerado não classificado, pois as métricas principais do fluxo não foram relatadas. Existem algumas razões pelas quais essas métricas podem não ser relatadas:

- **Relatórios de QoE não foram recebidos** - As métricas usadas para classificação são relatadas em um relatório de QoE enviado no final de uma chamada. Se esse relatório não for produzido (por exemplo, porque alguns pontos de extremidade de terceiros podem não enviar QoE) ou não puder ser enviado (por exemplo, devido a uma interrupção da rede), o CQD não poderá classificar o fluxo.

> [!TIP]
> A dimensão "Registro de QoE disponível" pode ser usada para determinar se um relatório de QoE foi recebido para um fluxo. Observe que essa dimensão terá um valor "Verdadeiro" se um relatório de QoE for recebido de um dos pontos de extremidade. Um relatório de QoE de ambos os pontos de extremidade é necessário para o relatório de métricas mais preciso.

- **Chamadas curtas** - Chamadas curtas podem não ter atividade de mídia suficiente para calcular as principais métricas de fluxo. Sem essas métricas, o CQD não consegue classificar o fluxo.

> [!TIP]
> As dimensões "Duração (Segundos)", "Duração (Minutos)", "Duração 5 segundos ou menos" e "Duração 60 segundos ou mais" podem ser usadas para determinar a duração de um fluxo. A medida "Duração média da chamada" também pode ser usada para calcular a duração média de um conjunto de fluxos.

- **Baixa utilização de pacotes** - Como no cenário de "chamadas curtas", a utilização suficiente de pacotes é necessária para o cálculo das principais métricas de fluxo. Sem essas métricas, o CQD não consegue classificar o fluxo.
    - Um cenário comum de baixa utilização de pacotes ocorre quando um usuário entra em uma reunião para ouvir o apresentador, mas nunca fala (provavelmente silenciando o microfone durante a maior parte da chamada). Nesse cenário, um fluxo de áudio terá alta utilização de pacotes (entrada para o cliente) enquanto o outro terá pouca ou nenhuma utilização de pacotes (saída do cliente). Nesse cenário, a duração do fluxo pode ser de uma hora ou mais, mas a utilização do pacote no fluxo do cliente para o servidor será extremamente baixa devido ao silêncio do microfone, resultando em um fluxo não classificado.

> [!TIP]
> A dimensão "Utilização de pacote" e a medida "Utilização média de pacote" podem ser usadas para determinar a atividade de pacote de um fluxo.


## <a name="related-topics"></a>Tópicos relacionados
[Ativar e usar o Painel de Qualidade de Chamadas (PQC)](turning-on-and-using-call-quality-dashboard.md)

[Dimensões e mensurações disponíveis no Painel de Qualidade de Chamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade das chamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)
