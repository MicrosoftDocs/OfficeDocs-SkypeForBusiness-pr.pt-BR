---
title: Classificação de fluxo no Painel de Qualidade de Chamada (CQD)
author: CarolynRowe
ms.author: crowe
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
description: Saiba como a qualidade do fluxo é classificada no Painel de Qualidade de Chamadas (CQD) do Microsoft Teams e Skype for Business Online.
ms.openlocfilehash: 9b17cf115759e96edbccdb85369ac42fd5861ff7
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794289"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>Classificação de fluxo no Painel de Qualidade de Chamada (CQD)

O Painel de Qualidade de Chamadas (CQD) para Microsoft Teams e Skype for Business Online permite que você obtenha insights sobre a qualidade das chamadas feitas usando o Microsoft Teams e Skype for Business serviços. Este tópico fornece informações detalhadas sobre a classificação de qualidade dos fluxos de mídia. Para saber mais sobre o CQD e como configurá-lo, consulte [Configurar o Painel de Qualidade de Chamadas](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Definições do classificador

Os fluxos no CQD são classificados como _Bons__, Ruins_ ou _Não Classificados_ com base nos valores das métricas de qualidade de chave disponíveis. As métricas e condições usadas para classificar o fluxo são mostradas nas tabelas a seguir. As dimensões "Ruim devido a" do CQD podem ser usadas para entender qual métrica é responsável por _uma classificação_ ruim. Para obter mais informações sobre essas dimensões, consulte [Dimensões e medidas disponíveis no Painel de Qualidade de Chamadas](dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="audio-classifier"></a>Classificador de áudio

Se uma ou mais das seguintes condições forem atendidas e a Utilização de Pacotes for > 500 pacotes, um fluxo de áudio será marcado como _Ruim_:

|Indicador|Cenário|Condição|Explicação|
|:-----|:-----|:-----|:-----|
|Ida|TODOS|> 500|Tempo médio de propagação de rede de ida e volta, calculado em milissegundos. Detalhes disponíveis no [RFC3550](https://tools.ietf.org/html/rfc3550).|
|Taxa de perda de pacotes|TODOS|> 0,1|Taxa média de perda de pacotes para fluxo.|
|Tremulação|TODOS|> 30|Tremulação média para fluxo em milissegundos.|
||||

### <a name="video-classifier-due-to-freeze"></a>Classificador de Vídeo devido a Congelamento

O fluxo de vídeo é marcado como  _Bom_ ou Ruim com base no valor de uma pontuação de classificador gerada para estimar que o usuário final experimentou o Vídeo Congelado. Este classificador está disponível apenas para o produto Microsoft Teams.

|Etapa Nº|Indicador|Cenário|Condição |Classificação se a condição for verdadeira |Classificação se a condição for falsa |Classificação se a métrica não estiver disponível |Explicação |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Video Poor Due to Freeze Classifier |O Par de Servidores é Cliente: Servidor|>0,246|_Pobre_|_Bom_|_Unclassified_|Uma Pontuação entre 0 e 1 gerada com base em uma combinação de experiência do usuário, congelar estatísticas de duração e experiência geral de chamada |
|2|Video Poor Due to Freeze Classifier |O Par de Servidores é Cliente: Cliente|>0,524|_Pobre_|_Bom_|_Unclassified_|Uma Pontuação entre 0 e 1 gerada com base em uma combinação de experiência do usuário, congelar estatísticas de duração e experiência geral de chamada |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>Classificador de Vídeo
Um fluxo de vídeo é marcado _como Bom_ ou _Ruim com base_ no valor da primeira métrica disponível na seguinte ordem:

|Etapa Nº|Indicador|Condição |Classificação se a condição for verdadeira |Classificação se a condição for falsa |Classificação se a métrica não estiver disponível |Explicação |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Média de Percentual de Perda de Quadro Local de Vídeo|> 50% |_Pobre_|_Bom_|Seguir para a Etapa 2|Percentual médio de quadros de vídeo perdidos conforme exibido para o usuário. A média inclui quadros recuperados de perdas de rede.|
|2|Média de taxa de quadros de vídeo|<7|_Pobre_|_Bom_|Seguir para a Etapa 3|Média de quadros por segundo recebidos para um fluxo de vídeo, calculados durante a sessão.|
|3|FECPLR de Postagem de Vídeo|> 0,15|_Pobre_|_Bom_|_Unclassified_|Taxa de perda de pacotes após a agregação do FEC em todos os fluxos de vídeo e codecs.|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>Classificador VBSS

Um fluxo VBSS é marcado como _Bom_ ou _Ruim com base_ no valor da primeira métrica disponível na seguinte ordem:

|Etapa Nº |Indicador |Condição |Classificação se a condição for verdadeira |Classificação se a condição for falsa |Classificação se a métrica não estiver disponível |Explicação |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Média de Percentual de Perda de Quadro Local de Vídeo|Codec não é H264S</br>E</br>StreamDirection é Entrada</br></br>Se FrameLoss > 50%|_Pobre_|_Bom_|_Unclassified_|Percentual médio de quadros de vídeo perdidos conforme exibido para o usuário. A média inclui quadros recuperados de perdas de rede. FrameLoss só é usado para classificar fluxos de entrada não H264S.|
|2|Média de taxa de quadros de vídeo|< 1|_Pobre_|_Bom_|_Unclassified_|Média de quadros por segundo recebidos para um fluxo de vídeo, calculados durante a sessão. Aplica-se a todos os fluxos de saída e streamDirection para H264S.|
| |  | | | |  ||


### <a name="application-sharing-classifier"></a>Classificador de compartilhamento de aplicativos

Um fluxo de compartilhamento de aplicativos será marcado _como Ruim_ se uma ou mais das seguintes condições forem atendidas:

| Indicador     | Condição | Explicação |
|:---        |:---       | :--- |
| Total de Percentual de Blocos Mimados | >36 | Porcentagem de blocos que são descartados em vez de enviados para um par remoto (por exemplo, do MCU para um visualizador). Blocos descartados (ou mimados) podem ser causados por restrições de largura de banda entre o cliente e o servidor. |
| Média de Latência de Processamento de Bloco RDP do AppSharing | > 400 | Latência média em blocos de processamento de milissegundos na pilha RDP no servidor de conferência. |
| AppSharing Relative OneWay Average | > 1,75 | Atraso médio relativo unidirecional entre os pontos de extremidade em segundos para fluxos de compartilhamento de aplicativos. |
| | | |

## <a name="unclassified-streams"></a>Fluxos não classificados

No CQD, um fluxo é marcado como  Não Classificado quando a conectividade ice (estabelecimento de conectividade interativa) falha ou quando todas as métricas necessárias para calcular a classificação de fluxo não são relatadas.

Para verificar se há falhas de conectividade ICE, examine as dimensões "Ice de primeira conectividade" e "Ice de segunda conectividade" em busca de um valor "FALHOU". Se um dos valores indicar uma falha, o fluxo será marcado como _Não Classificado_.

Se a conectividade ICE tiver sido bem-sucedida para um fluxo não classificado, o fluxo provavelmente  será considerado Não Classificado porque as métricas de fluxo de chave não foram relatadas. Existem algumas razões pelas quais essas métricas podem não ser relatadas:

- **Relatórios de QoE não foram** recebidos — As métricas usadas para classificação são relatadas em um relatório de QoE enviado ao final de uma chamada. Se esse relatório não for produzido (por exemplo, porque alguns pontos de extremidade de terceiros podem não enviar QoE) ou não puderem ser enviados (por exemplo, devido a uma interrupção de rede), o CQD não poderá classificar o fluxo.

  > [!TIP]
  > A dimensão "Registro de QoE disponível" pode ser usada para determinar se um relatório de QoE foi recebido para um fluxo. Observe que essa dimensão terá um valor "Verdadeiro" se um relatório de QoE for recebido de um dos pontos de extremidade. Um relatório de QoE de ambos os pontos de extremidade é necessário para o relatório de métricas mais preciso.

- **Chamadas curtas —** chamadas curtas podem não ter atividade de mídia suficiente para computar as métricas de fluxo de chaves. Sem essas métricas, o CQD não consegue classificar o fluxo.

  > [!TIP]
  > As dimensões "Duração (Segundos)", "Duração (Minutos)", "Duração 5 segundos ou menos" e "Duração 60 segundos ou mais" podem ser usadas para determinar a duração de um fluxo. A medida "Duração média da chamada" também pode ser usada para calcular a duração média de um conjunto de fluxos.

- **Baixa utilização de pacotes** — como o cenário de "chamada curta", a utilização de pacotes suficiente é necessária para a computação de métricas de fluxo de chaves. Sem essas métricas, o CQD não consegue classificar o fluxo.
  - Um cenário comum de baixa utilização de pacotes ocorre quando um participante ingressa em uma reunião para ouvir o apresentador, mas nunca fala (o microfone fica mudo na maior parte da chamada). Aqui, o fluxo de áudio de entrada para o cliente tem alta utilização de pacotes, enquanto o fluxo de áudio de saída do cliente tem pouca ou nenhuma utilização de pacotes. A duração do fluxo pode ser de uma hora ou mais, _mas a_ utilização do pacote no fluxo do cliente para o servidor é baixa, pois o microfone estava mudo e um fluxo não classificado resulta.

  > [!TIP]
  > A dimensão "Utilização de pacote" e a medida "Utilização média de pacote" podem ser usadas para determinar a atividade de pacote de um fluxo.

## <a name="related-topics"></a>Tópicos Relacionados
[Melhorar e monitorar a qualidade da chamada para o Teams](monitor-call-quality-qos.md)

[O que é CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar o Painel de Qualidade de Chamada (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Carregar dados de locatário e de criação](CQD-upload-tenant-building-data.md)

[Dados e relatórios do CQD](CQD-data-and-reports.md)

[Usar o CQD para gerenciar a qualidade da chamada e da reunião](quality-of-experience-review-guide.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Usar o Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md)
