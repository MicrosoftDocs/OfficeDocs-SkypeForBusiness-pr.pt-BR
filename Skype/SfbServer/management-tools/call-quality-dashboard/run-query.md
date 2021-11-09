---
title: Executar Consulta
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 'Resumo: saiba mais sobre a operação Executar Consulta, que faz parte da API de Dados para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.'
ms.openlocfilehash: 00060baabff5bdcc4e930f56f7885de273060597
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849804"
---
# <a name="run-query"></a>Executar Consulta

**Resumo:** Saiba mais sobre a operação Executar Consulta, que faz parte da API de Dados para Painel de Qualidade de Chamada. O Painel de Qualidade de Chamada é uma ferramenta para Skype for Business Server.

A operação Executar Consulta faz parte da API de Dados para Painel de Qualidade de Chamada.

## <a name="run-query"></a>Executar Consulta

Executar a operação de consulta fornece a capacidade de executar uma consulta no cubo com base em dimensões, medidas e filtros especificados e retornar os dados.


|**Method**|**Solicitar URI**|**Versão HTTP**|
|:-----|:-----|:-----|
|POST  <br/> |https:// \<portal\> /QoEDataService/RunQuery  <br/> |HTTP/1.1  <br/> |

 **Parâmetros URI** - Nenhum.

 **Headers de solicitação** - Sem headers adicionais.

 **Corpo da Solicitação** - Aqui está uma carga de solicitação de exemplo no JSON. Ele contém dimensões, filtros e medidas necessárias para uma consulta.

```json
{
"Filters": [{
"DataModelName": "[StartDate].[Month]",
"Caption": "July 2013",
"Value": "[2015-03-01T00:00:00]",
"Operand": 0,
"UnionGroup": ""
}],
"Dimensions": [{
"DataModelName": "[StartDate].[Month]"
}],
"Measurements": [{
"DataModelName": "[Measures].[Audio Good Streams Count]"
},
{
"DataModelName": "[Measures].[Audio UnClassified Streams Count]"
},
{
"DataModelName": "[Measures].[Audio Poor Streams Count]"
},
{
"DataModelName": "[Measures].[AudioPoorPercentage]"
}],
"Trend": {
"EnableTrend": true,
"SpanCount": 7,
"TrendDate": "2015-3",
"Type": 0
}
}
```

 *Filtros*  - Uma lista de expressões de filtro a serem aplicadas para que o conjunto de dados resultante reflita apenas o subconjunto dos dados que são de interesse.

 *Dimensões*  - Uma lista de dimensões que serão usadas para agregar os dados. Pelo menos uma dimensão é necessária, mas várias dimensões podem ser especificadas para obter nível adicional de sub-agregação.

 *Medidas*  - Uma lista de medidas, também conhecidas como fatos, que são as métricas desejadas a serem agregadas com base nas dimensões especificadas.

 *Tendência*  - Instruções de controle adicionais para personalizar os dados de resultados.

 **Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.

 **Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).

 **Headers de resposta** - Sem headers adicionais.

 **Corpo da Resposta** - Abaixo está uma carga de resposta de exemplo no JSON. Ele contém uma tabela de dados que contém os dados, também conterá um metadados, que mostra o tempo de execução da consulta e se os dados são ou não do cache.

```json
{
"ExecutionTime": "00:00:00.2102630",
"DataResult": [["September 2014",
        1792,
        34,
        78,
        4.171],
        ["October 2014",
        37017,
        1731,
        3305,
        8.197],
        ["November 2014",
        79184,
        3033,
        5556,
        6.557],
        ["December 2014",
        122253,
        4050,
        5444,
        4.263],
        ["January 2015",
        31246,
        1069,
        1342,
        4.118]],
"ResultIsFromCache": false,
"ErrorType": 0
}
```

 *Tempo de execução*  - O tempo total que levou para o servidor retornar os dados. Isso pode ou não envolver cache.

 *Resultado dos*  dados - O resultado da consulta. É uma matriz bidimensional que contém todas as permutações dos membros das dimensões e cada elemento que contém os nomes de membros das dimensões, bem como os valores agregados das Medidas especificadas.

 *Result is From Cache*  - For diagnostics. Indica se o resultado veio do cache ou do Cubo QoE.
