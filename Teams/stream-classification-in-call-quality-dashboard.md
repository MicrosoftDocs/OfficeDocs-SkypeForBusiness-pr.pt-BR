---
title: Classificação de fluxo no Painel de Qualidade de Chamada (CQD)
ms.author: serdars
author: lolaj
manager: serdars
ms.reviewer: gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Saiba como a qualidade do fluxo é classificada no Painel de Qualidade de Chamada (CQD) do Microsoft Teams e do Skype for Business Online.
ms.openlocfilehash: 400dcd953805595b4457b4ca9443c31b66f7425d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909035"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>Classificação de Fluxo no Painel de Qualidade da Chamada (CQD)

O Painel de Qualidade de Chamada (CQD) do Microsoft Teams e do Skype for Business Online permite que você obtenha informações sobre a qualidade das chamadas feitas usando os serviços do Microsoft Teams e do Skype for Business. Este tópico fornece informações detalhadas sobre a classificação de qualidade dos fluxos de mídia. Para saber mais sobre o CQD e como configurar, consulte Configurar o Painel de Qualidade [da Chamada.](turning-on-and-using-call-quality-dashboard.md)

## <a name="classifier-definitions"></a>Definições do classificador

Os fluxos no CQD são classificados como _Bons,_ Ruins ou _Não Classificados_ com base nos valores das métricas de qualidade de chave disponíveis. As métricas e condições usadas para classificar o fluxo são mostradas nas tabelas a seguir. As dimensões "Poor Due To" do CQD podem ser usadas para entender qual métrica é responsável por uma _classificação_ Ruim. Para obter mais informações sobre essas dimensões, consulte Dimensões e [medidas disponíveis no Painel de Qualidade da Chamada.](dimensions-and-measures-available-in-call-quality-dashboard.md)

### <a name="audio-classifier"></a>Classificador de áudio

Se uma ou mais das seguintes condições são atendidas, um fluxo de áudio é marcado como _Ruim:_

|Indicador|Cenário|Condição|Explicação|
|:-----|:-----|:-----|:-----|
|Audio Degradation Avg|A Descrição da Carga não é STIM|> 1,0|Média da degradação da pontuação média de opinião de rede para stream. Quanto a perda de rede e a tremedeira afetaram a qualidade do áudio recebido.|
|Ida|Todos|> 500|Tempo médio de propagação da rede de ida e volta, calculado em milissegundos. Detalhes disponíveis no [RFC3550.](https://tools.ietf.org/html/rfc3550)|
|Taxa de perda de pacote|Todos|> 0,1|Média da taxa de perda de pacote para stream.|
|Tremulação|Todos|> 30|Média de tremida para fluxo em milissegundos.|
|Ratio Concealed Samples Avg|A Descrição da Carga não é STIM|> 0,07|Taxa média do número de quadros de áudio com amostras ocultas geradas pela perda de pacotes para o número total de quadros de áudio.|
||||

### <a name="video-classifier-due-to-freeze"></a>Classificador de Vídeo devido ao congelamento

O stream de vídeo é marcado  _como Bom_ ou Ruim _com_ base no valor de uma pontuação de classificador gerada para estimar que o usuário final experimentou o Vídeo Congelado. Este classificador está disponível apenas para produtos do Microsoft Teams.

|Etapa Nº|Indicador|Cenário|Condição |Classificação se a condição for verdadeira |Classificação se a condição for falsa |Classificação se a métrica não estiver disponível |Explicação |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Poor Due to Freeze Classifier |Is Server Pair is Client : Server|>0,246|_Pobre_|_Bom_|_Unclassified_|Uma Pontuação entre 0 e 1 gerada com base em uma combinação de experiência do usuário, congelar estatísticas de duração e experiência geral de chamada |
|2|Video Poor Due to Freeze Classifier |Is Server Pair is Client : Client|>0,524|_Pobre_|_Bom_|_Unclassified_|Uma Pontuação entre 0 e 1 gerada com base em uma combinação de experiência do usuário, congelar estatísticas de duração e experiência geral de chamada |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>Classificador de Vídeo
Um fluxo de vídeo é marcado como _Bom_ ou Ruim _com_ base no valor da primeira métrica disponível na seguinte ordem:

|Etapa Nº|Indicador|Condição |Classificação se a condição for verdadeira |Classificação se a condição for falsa |Classificação se a métrica não estiver disponível |Explicação |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Local Frame Loss Percentage Avg|> 50% |_Pobre_|_Bom_|Seguir para a Etapa 2|Porcentagem média de quadros de vídeo perdidos conforme exibido para o usuário. A média inclui quadros recuperados das perdas de rede.|
|2|Video Frame Rate Avg|<7|_Pobre_|_Bom_|Seguir para a Etapa 3|Média de quadros por segundo recebidos para um fluxo de vídeo, calculados durante a sessão.|
|3|FECPLR de postagem de vídeo|> 0,15|_Pobre_|_Bom_|_Unclassified_|Taxa de perda de pacotes após a aplicação do FEC agregada em todos os fluxos de vídeo e codecs.|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>Classificador VBSS

Um fluxo VBSS é marcado como _Bom_ ou Ruim _com_ base no valor da primeira métrica disponível na seguinte ordem:

|Etapa Nº |Indicador |Condição |Classificação se a condição for verdadeira |Classificação se a condição for falsa |Classificação se a métrica não estiver disponível |Explicação |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|> 50% |_Pobre_|_Bom_|Seguir para a Etapa 2|Porcentagem média de quadros de vídeo perdidos conforme exibido para o usuário. A média inclui quadros recuperados das perdas de rede.|
|2|Video Frame Rate Avg|< 2|_Pobre_|_Bom_|Seguir para a Etapa 3|Média de quadros por segundo recebidos para um fluxo de vídeo, calculados durante a sessão.|
|3|FECPLR de postagem de vídeo|> 0,15|_Pobre_|_Bom_|_Unclassified_|Taxa de perda de pacotes após a aplicação do FEC agregada em todos os fluxos de vídeo e codecs.|
| |  | | | |  ||

### <a name="application-sharing-classifier"></a>Classificador de compartilhamento de aplicativos

Um fluxo de compartilhamento de aplicativos é marcado _como Ruim_ se uma ou mais das seguintes condições são atendidas:

| Indicador     | Condição | Explicação |
|:---        |:---       | :--- |
| Total da Porcentagem de Telhas Mimadas | >36 | Porcentagem de blocos que são descartados em vez de enviados para um ponto remoto (por exemplo, da MCU para um visualizador). Os blocos descartados (ou mimados) podem ser causados por restrições de largura de banda entre cliente e servidor. |
| AppSharing RDP Tile Processing Latency Average | > 400 | Latência média em blocos de processamento de milissegundos na Pilha RDP no servidor de conferência. |
| AppSharing Relative OneWay Average | > 1,75 | Média de atraso one-way relativo entre os pontos de extremidade em segundos para fluxos de compartilhamento de aplicativos. |
| | | |

## <a name="unclassified-streams"></a>Fluxos não classificados

No CQD, um  fluxo é marcado como Não classificado quando falha a conectividade Interativa de Conectividade (ICE) ou quando todas as métricas necessárias para calcular a classificação de fluxo não são relatadas.

Para verificar se há falhas de conectividade ICE, examine as dimensões "Ice de primeira conectividade" e "Ice de segunda conectividade" em busca de um valor "FALHOU". Se um dos valores indicar uma falha, o fluxo será marcado como _Não Classificado._

Se a conectividade ICE tiver sido bem-sucedida para um _fluxo_ não classificado, o fluxo provavelmente será considerado Não _Classificado_ porque as métricas de fluxo de chave não foram relatadas. Existem algumas razões pelas quais essas métricas podem não ser relatadas:

- **Os relatórios de QoE não** foram recebidos — as métricas usadas para classificação são relatadas em um relatório de QoE enviado no final de uma chamada. Se esse relatório não for produzido (por exemplo, porque alguns pontos de extremidade de terceiros podem não enviar QoE) ou não puderem ser enviados (por exemplo, devido a uma interrupção de rede), o CQD não poderá classificar o fluxo.

  > [!TIP]
  > A dimensão "Registro de QoE disponível" pode ser usada para determinar se um relatório de QoE foi recebido para um fluxo. Observe que essa dimensão terá um valor "Verdadeiro" se um relatório de QoE for recebido de um dos pontos de extremidade. Um relatório de QoE de ambos os pontos de extremidade é necessário para o relatório de métricas mais preciso.

- **Chamadas curtas** — chamadas curtas podem não ter atividade de mídia suficiente para calcular as principais métricas de fluxo. Sem essas métricas, o CQD não consegue classificar o fluxo.

  > [!TIP]
  > As dimensões "Duração (Segundos)", "Duração (Minutos)", "Duração 5 segundos ou menos" e "Duração 60 segundos ou mais" podem ser usadas para determinar a duração de um fluxo. A medida "Duração média da chamada" também pode ser usada para calcular a duração média de um conjunto de fluxos.

- **Uso baixo de pacotes** — como o cenário de "chamada curta", o uso suficiente de pacotes é necessário para a computação de métricas de fluxo de chave. Sem essas métricas, o CQD não consegue classificar o fluxo.
  - Um cenário comum de uso baixo de pacotes ocorre quando um participante participa de uma reunião para ouvir o apresentador, mas nunca fala (o microfone está com mudo mudo durante a maior parte da chamada). Aqui, o fluxo de áudio de entrada para o cliente tem alta utilização de pacotes, enquanto a saída de fluxo de áudio do cliente tem pouca ou nenhuma utilização de pacote. A duração do fluxo pode ser de uma hora ou mais, mas a utilização do pacote no fluxo do cliente para o servidor é baixa, uma vez que o microfone estava com mudo mudo e um resultado de _fluxo_ não classificado.

  > [!TIP]
  > A dimensão "Utilização de pacote" e a medida "Utilização média de pacote" podem ser usadas para determinar a atividade de pacote de um fluxo.

## <a name="related-topics"></a>Tópicos Relacionados
[Melhorar e monitorar a qualidade da chamada para o Teams](monitor-call-quality-qos.md)

[O que é CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar o Painel de Qualidade de Chamada (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Carregar dados de locatário e de construção](CQD-upload-tenant-building-data.md)

[Dados e relatórios do CQD](CQD-data-and-reports.md)

[Usar o CQD para gerenciar a qualidade da chamada e da reunião](quality-of-experience-review-guide.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Usar o Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md)
