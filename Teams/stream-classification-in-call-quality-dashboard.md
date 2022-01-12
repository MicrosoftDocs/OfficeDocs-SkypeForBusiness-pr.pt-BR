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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Saiba como a qualidade do fluxo é classificada no Painel de Qualidade de Chamada (CQD) para Microsoft Teams e Skype for Business Online.
ms.openlocfilehash: 21de07e2b590bafcb7de65495e6b7d68faa381cc
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767194"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>Classificação de fluxo no Painel de Qualidade de Chamada (CQD)

O Painel de Qualidade de Chamadas (CQD) para Microsoft Teams e Skype for Business Online permite obter informações sobre a qualidade das chamadas feitas usando serviços Microsoft Teams e Skype for Business. Este tópico fornece informações detalhadas sobre a classificação de qualidade dos fluxos de mídia. Para saber mais sobre o CQD e como defini-lo, consulte [Configurar Painel de Qualidade de Chamada](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Definições do classificador

Fluxos no CQD são classificados como _Good_, _Poor_ ou _Unclassified_ com base nos valores das métricas de qualidade de chave disponíveis. As métricas e condições usadas para classificar o fluxo são mostradas nas tabelas a seguir. As dimensões "Poor Due To" do CQD podem ser usadas para entender qual métrica é responsável por uma _classificação Ruim._ Para obter mais informações sobre essas dimensões, consulte [Dimensões e medidas disponíveis no Painel de](dimensions-and-measures-available-in-call-quality-dashboard.md)Qualidade de Chamada.

### <a name="audio-classifier"></a>Classificador de áudio

Se uma ou mais das seguintes condições são atendidas, um fluxo de áudio é marcado como _Poor_:

|Indicador|Cenário|Condição|Explicação|
|:-----|:-----|:-----|:-----|
|Ida e volta|ALL|> 500|Tempo médio de propagação de rede de ida e volta, calculado em milissegundos. Detalhes disponíveis em [RFC3550](https://tools.ietf.org/html/rfc3550).|
|Taxa de perda de pacotes|ALL|> 0,1|Taxa média de perda de pacotes para fluxo.|
|Tremulação|ALL|> 30|Tremência média para fluxo em milissegundos.|
||||

### <a name="video-classifier-due-to-freeze"></a>Classificador de Vídeo devido a Freeze

O fluxo de vídeo  é marcado _como Bom_ ou Ruim com base no valor de uma pontuação de classificador gerada para estimar que o usuário final experimentou o Vídeo Congelado. Este classificador está disponível apenas para Microsoft Teams produto.

|Etapa Nº|Indicador|Cenário|Condição |Classificação se a condição for verdadeira |Classificação se a condição for falsa |Classificação se a métrica não estiver disponível |Explicação |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Vídeo ruim devido ao classificador de congelamento |Is Server Pair is Client : Server|>0,246|_Ruim_|_Bom_|_Não classificado_|Uma Pontuação entre 0 e 1 gerada com base em uma combinação de experiência do usuário, estatísticas de duração de congelamento e experiência geral de chamada |
|2|Vídeo ruim devido ao classificador de congelamento |É Par de Servidores é Cliente : Cliente|>0,524|_Ruim_|_Bom_|_Não classificado_|Uma Pontuação entre 0 e 1 gerada com base em uma combinação de experiência do usuário, estatísticas de duração de congelamento e experiência geral de chamada |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>Classificador de Vídeo
Um fluxo de vídeo é marcado como _Bom_ ou Ruim _com_ base no valor da primeira métrica disponível na seguinte ordem:

|Etapa Nº|Indicador|Condição |Classificação se a condição for verdadeira |Classificação se a condição for falsa |Classificação se a métrica não estiver disponível |Explicação |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Avg percentual de perda de quadro local de vídeo|> 50% |_Ruim_|_Bom_|Seguir para a Etapa 2|Porcentagem média de quadros de vídeo perdidos conforme exibido para o usuário. A média inclui quadros recuperados de perdas de rede.|
|2|Avg da taxa de quadros de vídeo|<7|_Ruim_|_Bom_|Seguir para a Etapa 3|Quadros médios por segundo recebidos para um fluxo de vídeo, calculados durante a duração da sessão.|
|3|FECPLR de Postagem de Vídeo|> 0,15|_Ruim_|_Bom_|_Não classificado_|Taxa de perda de pacotes após a aplicação do FEC agregada em todos os fluxos de vídeo e codecs.|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>Classificador VBSS

Um fluxo VBSS é  marcado como _Bom_ ou Ruim com base no valor da primeira métrica disponível na seguinte ordem:

|Etapa Nº |Indicador |Condição |Classificação se a condição for verdadeira |Classificação se a condição for falsa |Classificação se a métrica não estiver disponível |Explicação |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Avg percentual de perda de quadro local de vídeo|Codec NÃO é H264S</br>E</br>StreamDirection é Entrada</br></br>Se FrameLoss > 50%|_Ruim_|_Bom_|_Não classificado_|Porcentagem média de quadros de vídeo perdidos conforme exibido para o usuário. A média inclui quadros recuperados de perdas de rede. FrameLoss só é usado para classificar fluxos de entrada que não são H264S.|
|2|Avg da taxa de quadros de vídeo|< 1|_Ruim_|_Bom_|_Não classificado_|Quadros médios por segundo recebidos para um fluxo de vídeo, calculados durante a duração da sessão. Aplica-se a todos os fluxos de saída e streamDirection para H264S.|
| |  | | | |  ||


### <a name="application-sharing-classifier"></a>Classificador de compartilhamento de aplicativos

Um fluxo de compartilhamento de aplicativos será marcado como _Ruim_ se uma ou mais das seguintes condições são atendidas:

| Indicador     | Condição | Explicação |
|:---        |:---       | :--- |
| Total de porcentagem de telhas mimadas | >36 | Porcentagem de blocos descartados em vez de enviados para um par remoto (por exemplo, da MCU para um visualizador). Blocos descartados (ou estragados) podem ser causados por restrições de largura de banda entre cliente e servidor. |
| Média de Latência de Processamento de Tile RDP de AppSharing | > 400 | Latência média em blocos de processamento de milissegundos na Pilha RDP no servidor de conferência. |
| Média relativa do OneWay appSharing | > 1,75 | Atraso relativo médio entre os pontos de extremidade em segundos para fluxos de compartilhamento de aplicativos. |
| | | |

## <a name="unclassified-streams"></a>Fluxos não classificados

No CQD, um  fluxo é marcado como Não classificado quando a conectividade ICE (Estabelecimento de Conectividade Interativa) falha ou quando todas as métricas necessárias para calcular a classificação de fluxo não são relatadas.

Para verificar se há falhas de conectividade ICE, examine as dimensões "Ice de primeira conectividade" e "Ice de segunda conectividade" em busca de um valor "FALHOU". Se um dos valores indicar uma falha, o fluxo será marcado como _Unclassified_.

Se a conectividade ICE  tiver sido bem-sucedida para um fluxo não classificado, o fluxo provavelmente será considerado _Não classificado_ porque as métricas de fluxo de teclas não foram relatadas. Existem algumas razões pelas quais essas métricas podem não ser relatadas:

- **Relatórios de QoE não foram recebidos** — As métricas usadas para classificação são relatadas em um relatório de QoE enviado no final de uma chamada. Se esse relatório não for produzido (por exemplo, porque alguns pontos de extremidade de terceiros podem não enviar QoE) ou não puder ser enviado (por exemplo, devido a uma interrupção de rede), o CQD não poderá classificar o fluxo.

  > [!TIP]
  > A dimensão "Registro de QoE disponível" pode ser usada para determinar se um relatório de QoE foi recebido para um fluxo. Observe que essa dimensão terá um valor "Verdadeiro" se um relatório de QoE for recebido de um dos pontos de extremidade. Um relatório de QoE de ambos os pontos de extremidade é necessário para o relatório de métricas mais preciso.

- **Chamadas curtas** — chamadas curtas podem não ter atividade de mídia suficiente para calcular métricas de fluxo de chaves. Sem essas métricas, o CQD não consegue classificar o fluxo.

  > [!TIP]
  > As dimensões "Duração (Segundos)", "Duração (Minutos)", "Duração 5 segundos ou menos" e "Duração 60 segundos ou mais" podem ser usadas para determinar a duração de um fluxo. A medida "Duração média da chamada" também pode ser usada para calcular a duração média de um conjunto de fluxos.

- **Baixa utilização de** pacotes — como o cenário de "chamada curta", a utilização de pacote suficiente é necessária para a computação de métricas de fluxo de chaves. Sem essas métricas, o CQD não consegue classificar o fluxo.
  - Um cenário comum de baixa utilização de pacotes ocorre quando um participante ins participa de uma reunião para ouvir o apresentador, mas nunca fala (o microfone é mudo para a maioria da chamada). Aqui, o fluxo de áudio de entrada para o cliente tem alta utilização de pacotes enquanto o fluxo de áudio de saída do cliente tem pouca ou nenhuma utilização de pacote. A duração do fluxo pode ser de uma hora ou mais, mas _a_ utilização do pacote no fluxo do cliente para o servidor é baixa desde que o microfone foi silenciado e um fluxo não classificado resulta.

  > [!TIP]
  > A dimensão "Utilização de pacote" e a medida "Utilização média de pacote" podem ser usadas para determinar a atividade de pacote de um fluxo.

## <a name="related-topics"></a>Tópicos Relacionados
[Melhorar e monitorar a qualidade de chamada para Teams](monitor-call-quality-qos.md)

[O que é CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar o Painel de Qualidade de Chamada (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Upload locatário e a criação de dados](CQD-upload-tenant-building-data.md)

[Dados e relatórios do CQD](CQD-data-and-reports.md)

[Usar o CQD para gerenciar a qualidade de chamada e reunião](quality-of-experience-review-guide.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Usar Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md)
