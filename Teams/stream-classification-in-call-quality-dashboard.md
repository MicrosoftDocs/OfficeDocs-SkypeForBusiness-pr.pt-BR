---
title: Classificação de fluxo no painel de qualidade de chamada (CQD)
ms.author: lolajacobsen
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
description: Saiba como a qualidade do fluxo é classificada no painel de qualidade da chamada (CQD) para Microsoft Teams e Skype for Business online.
ms.openlocfilehash: 28c3857f1bf30903e9a59d45e8149f8ecbfc57be
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085887"
---
# <a name="stream-classification-in-call-quality-dashboard-cqd"></a>Classificação de fluxo no painel de qualidade de chamada (CQD)

O painel de qualidade de chamada (CQD) para Microsoft Teams e o Skype for Business Online permite que você obtenha ideias sobre a qualidade das chamadas feitas usando o Microsoft Teams e os serviços do Skype for Business. Este tópico fornece informações detalhadas sobre a classificação de qualidade de fluxos de mídia. Para saber mais sobre o CQD e como configurá-lo, consulte [Configurar o painel de qualidade de chamada](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Definições do classificador

Fluxos no CQD são classificados como _satisfatórios_, _ruins_ou não _classificados_ com base nos valores das métricas de qualidade de tecla disponíveis. As métricas e condições usadas para classificar o fluxo são mostradas nas tabelas a seguir. As dimensões "ruim devido a" de CQD podem ser usadas para compreender qual medida é responsável por uma classificação _deficiente_ . Para obter mais informações sobre essas dimensões, consulte [dimensões e medidas disponíveis no painel de qualidade da chamada](dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="audio-classifier"></a>Classificador de áudio

Se uma ou mais das seguintes condições forem atendidas, um fluxo de áudio será marcado como _ruim_:

|Indicador|Condição|Explicação|
|:-----|:-----|:-----|
|Média de degradação de áudio|> 1,0|Média de pontuação média média média de Pontuação do Stream. Quanta perda de rede e Tremulação afetaram a qualidade do áudio recebido.|
|Viagem de ida e volta|> 500|Tempo médio de propagação da rede de ida e volta, calculado em milissegundos. Detalhes disponíveis em [RFC3550](https://tools.ietf.org/html/rfc3550).|
|Taxa de perda de pacotes|> 0,1|Taxa média de perda de pacotes do Stream.|
|Tremulação|> 30|Variação média do fluxo em milissegundos.|
|Índice médio de amostras ocultas|> 0,07|Razão média do número de quadros de áudio com amostras ocultas geradas pelo reparo de perda de pacotes para o número total de quadros de áudio.|
||||

### <a name="video-classifier-due-to-freeze"></a>Classificador de vídeo devido ao congelamento

O fluxo de vídeo é marcado como _bom_ ou _ruim_ com base no valor de uma pontuação do classificador gerada para estimar que o usuário final tenha detectado vídeo congelado. Esse classificador só está disponível para o produto Microsoft Teams.

|Etapa Nº|Indicador|Cenário|Condição |Classificação se a condição for verdadeira |Classificação se a condição for falsa |Classificação se a métrica não estiver disponível |Explicação |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Vídeo ruim devido ao classificador de congelamento |O par de servidores é cliente: servidor|>0,246|_Satisfatório_|_Corretamente_|_Não classificados_|Uma pontuação entre 0 e 1 que é gerada com base em uma combinação de experiência do usuário, congelar estatísticas de duração e experiência em chamadas gerais |
|2|Vídeo ruim devido ao classificador de congelamento |O par de servidores é cliente: cliente|>0,524|_Satisfatório_|_Corretamente_|_Não classificados_|Uma pontuação entre 0 e 1 que é gerada com base em uma combinação de experiência do usuário, congelar estatísticas de duração e experiência em chamadas gerais |
|  |  |  |  |  |  |  |

### <a name="video-classifier"></a>Classificador de Vídeo
Um fluxo de vídeo é marcado como _bom_ ou _ruim_ com base no valor da primeira métrica disponível na seguinte ordem:

|Etapa Nº|Indicador|Condição |Classificação se a condição for verdadeira |Classificação se a condição for falsa |Classificação se a métrica não estiver disponível |Explicação |
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|1|Porcentagem média de perda de quadro local de vídeo|> 50% |_Satisfatório_|_Corretamente_|Seguir para a Etapa 2|Porcentagem média de quadros de vídeo perdidos como exibido para o usuário. A média inclui quadros recuperados de perdas na rede.|
|2|Taxa média de quadros de vídeo|<7|_Satisfatório_|_Corretamente_|Seguir para a Etapa 3|Média de quadros por segundo recebidos para um fluxo de vídeo, calculados durante a duração da sessão.|
|3|Publicação com vídeo FECPLR|> 0,15|_Satisfatório_|_Corretamente_|_Não classificados_|Taxa de perda de pacotes após a aplicação de FEC agregada em todos os fluxos de vídeo e codecs.|
|  |  |  |  |  |  |  |

### <a name="vbss-classifier"></a>Classificador VBSS

Um fluxo VBSS é marcado como _bom_ ou _ruim_ com base no valor da primeira métrica disponível na seguinte ordem:

|Etapa Nº |Indicador |Condição |Classificação se a condição for verdadeira |Classificação se a condição for falsa |Classificação se a métrica não estiver disponível |Explicação |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Porcentagem média de perda de quadro local de vídeo|> 50% |_Satisfatório_|_Corretamente_|Seguir para a Etapa 2|Porcentagem média de quadros de vídeo perdidos como exibido para o usuário. A média inclui quadros recuperados de perdas na rede.|
|2|Taxa média de quadros de vídeo|< 2|_Satisfatório_|_Corretamente_|Seguir para a Etapa 3|Média de quadros por segundo recebidos para um fluxo de vídeo, calculados durante a duração da sessão.|
|3|Publicação com vídeo FECPLR|> 0,15|_Satisfatório_|_Corretamente_|_Não classificados_|Taxa de perda de pacotes após a aplicação de FEC agregada em todos os fluxos de vídeo e codecs.|
| |  | | | |  ||

### <a name="application-sharing-classifier"></a>Classificador de compartilhamento de aplicativos

Um fluxo de compartilhamento de aplicativos será marcado como _ruim_ se uma ou mais das seguintes condições forem atendidas:

| Indicador     | Condição | Explicação |
|:---        |:---       | :--- |
| Porcentagem total de danificados de bloco | >36 | Porcentagem de blocos que são descartados em vez de serem enviados para um par remoto (por exemplo, do MCU para um visualizador). Blocos descartados (ou danificados) podem ser causados por restrições de largura de banda entre o cliente e o servidor. |
| Média de latência de processamento de bloco RDP compartilhamento | > 400 | Média de latência em milissegundos processando blocos na pilha RDP no servidor de conferência. |
| Média de compartilhamento relativa a OneWay | > 1,75 | Atraso médio relativo relativo entre os pontos de extremidade em segundos para fluxos de compartilhamento de aplicativos. |
| | | |

## <a name="unclassified-streams"></a>Fluxos não classificados

No CQD, um fluxo é marcado como não _classificado_ quando a conectividade do estabelecimento de conectividade interativa (ICE) falha ou quando todas as métricas necessárias para calcular a classificação de fluxo não são relatadas.

Para verificar se há falhas de conectividade ICE, examine as dimensões "Ice de primeira conectividade" e "Ice de segunda conectividade" em busca de um valor "FALHOU". Se o valor indicar uma falha, o fluxo será marcado como não _classificado_.

Se a conectividade do ICE for bem-sucedida para um fluxo não _classificado_ , é provável que o fluxo seja considerado não _classificado_ porque as métricas de fluxo de chave não foram relatadas. Existem algumas razões pelas quais essas métricas podem não ser relatadas:

- Os **relatórios de QoE não foram recebidos** — as métricas usadas para classificação são relatadas em um relatório de QoE enviado ao fim de uma chamada. Se esse relatório não for produzido (por exemplo, porque alguns pontos de extremidade de terceiros não podem enviar QoE) ou não puderem ser enviados (por exemplo, devido a uma falha de rede), CQD não poderá classificar o fluxo.

> [!TIP]
> A dimensão "Registro de QoE disponível" pode ser usada para determinar se um relatório de QoE foi recebido para um fluxo. Observe que essa dimensão terá um valor "Verdadeiro" se um relatório de QoE for recebido de um dos pontos de extremidade. Um relatório de QoE de ambos os pontos de extremidade é necessário para o relatório de métricas mais preciso.

- **Chamadas curtas** – chamadas curtas podem não ter atividade de mídia suficiente para calcular as métricas de fluxo de chave. Sem essas métricas, o CQD não consegue classificar o fluxo.

> [!TIP]
> As dimensões "Duração (Segundos)", "Duração (Minutos)", "Duração 5 segundos ou menos" e "Duração 60 segundos ou mais" podem ser usadas para determinar a duração de um fluxo. A medida "Duração média da chamada" também pode ser usada para calcular a duração média de um conjunto de fluxos.

- **Baixa utilização de pacotes** , como o cenário "chamada curta", a utilização de pacotes suficiente é necessária para o cálculo das principais métricas de fluxo. Sem essas métricas, o CQD não consegue classificar o fluxo.
  - Um cenário comum de pouca utilização de pacotes ocorre quando um participante ingressa em uma reunião para ouvir o apresentador, mas nunca fala (o microfone está mudo para a maioria da chamada). Aqui, o fluxo de áudio de entrada do cliente tem alta utilização de pacote enquanto o fluxo de áudio de saída do cliente não tem pouca utilização de pacote. A duração do fluxo pode ser uma hora ou mais, mas a utilização do pacote no fluxo do cliente para o servidor está baixa desde que o microfone foi desativado, e os resultados de fluxo não _classificados_ .

> [!TIP]
> A dimensão "Utilização de pacote" e a medida "Utilização média de pacote" podem ser usadas para determinar a atividade de pacote de um fluxo.

## <a name="related-topics"></a>Tópicos Relacionados
[Melhorar e monitorar a qualidade da chamada para equipes](monitor-call-quality-qos.md)

[O que é CQD?](CQD-what-is-call-quality-dashboard.md)

[Configurar o painel de qualidade da chamada (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Carregar dados do locatário e construção](CQD-upload-tenant-building-data.md)

[Dados e relatórios do CQD](CQD-data-and-reports.md)

[Usar o CQD para gerenciar a qualidade da chamada e da reunião](quality-of-experience-review-guide.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Usar o Power BI para analisar dados do CQD](CQD-Power-BI-query-templates.md)
