---
title: Executar Consulta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 'Resumo: Saiba mais sobre a operação executar consulta, que faz parte da API de dados para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 8d31ea4c597ea3353fdd5da3e863938aababe819
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991396"
---
# <a name="run-query"></a>Executar Consulta

**Resumo:** Saiba mais sobre a operação executar consulta, que faz parte da API de dados para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.

A operação executar consulta faz parte da API de dados para o painel de qualidade da chamada.

## <a name="run-query"></a>Executar Consulta

Executar a operação de consulta fornece a capacidade de executar uma consulta no cubo com base em dimensões, medidas e filtros especificados e retornar os dados.


|**Forma**|**URI de solicitação**|**Versão HTTP**|
|:-----|:-----|:-----|
|Postar  <br/> |https://\<do\>portal de/QoEDataService/RunQuery  <br/> |HTTP/1.1  <br/> |

 **Parâmetros de URI** -nenhum.

 **Solicitar cabeçalhos** -sem cabeçalhos adicionais.

 **Corpo da solicitação** -aqui está um exemplo de carga de solicitação em JSON. Ele contém dimensões, filtros e medidas necessárias para uma consulta.

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

 *Filtros* -uma lista de expressões de filtro a ser aplicada de forma que o conjunto de dados resultante reflita apenas o subconjunto dos dados que são de interesse.

 *Dimensões* -uma lista de dimensões que será usada para agregar os dados. Pelo menos uma dimensão é necessária, mas várias dimensões podem ser especificadas para obter um nível adicional de subagregações.

 *Medições* – uma lista de medições, também conhecidas como fatos, que são as métricas desejadas a serem agregadas com base nas dimensões que você especificou.

 *Tendência* -instruções de controle adicionais para personalizar os dados do resultado.

 **Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.

 **Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK).

 **Cabeçalhos de resposta** -sem cabeçalhos adicionais.

 **Corpo da resposta** -abaixo está uma carga de resposta de exemplo em JSON. Ele contém uma tabela de dados que contém os dados; além disso, ele conterá um metadados, que mostra o tempo de execução da consulta e se os dados são do cache.

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

 *Tempo de execução* – o tempo total necessário para que o servidor retorne os dados. Isso pode ou não incluir o cache.

 *Resultado dos dados* -o resultado da consulta. É uma matriz bidimensional contendo todas as permutações de membros das dimensões e cada elemento que contém os nomes dos membros das dimensões, bem como os valores agregados das medidas especificadas.

 O *resultado é do cache* -para diagnóstico. Indica se o resultado veio do cache ou do cubo de QoE.
