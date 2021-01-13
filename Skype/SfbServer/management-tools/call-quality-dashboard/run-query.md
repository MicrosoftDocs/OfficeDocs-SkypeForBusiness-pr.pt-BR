---
title: Executar Consulta
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 'Resumo: saiba mais sobre a operação Executar Consulta, que faz parte da API de Dados para Painel de Qualidade de Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: bff24ca5a4d651ba276b4b0d795afabce3c6d0dd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803111"
---
# <a name="run-query"></a>Executar Consulta

**Resumo:** Saiba mais sobre a operação Executar Consulta, que faz parte da API de Dados para Painel de Qualidade de Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.

A operação Executar Consulta faz parte da API de Dados do Painel de Qualidade da Chamada.

## <a name="run-query"></a>Executar Consulta

A operação Executar Consulta oferece a capacidade de executar uma consulta no cubo com base em dimensões, medidas e filtros especificados e retornar os dados.


|**Method**|**URI de solicitação**|**Versão HTTP**|
|:-----|:-----|:-----|
|POSTAR  <br/> |https:// \<portal\> /QoEDataService/RunQuery  <br/> |HTTP/1.1  <br/> |

 **Parâmetros de URI** - Nenhum.

 **Solicitação de headers** - nenhum outro.

 **Corpo da** Solicitação - Veja um exemplo de carga de solicitação em JSON. Ele contém dimensões, filtros e medidas necessárias para uma consulta.

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

 *Filtros*  - Uma lista de expressões de filtro a serem aplicadas de forma que o conjunto de dados resultante reflita somente o subconjunto dos dados de interesse.

 *Dimensões*  - Uma lista de dimensões que serão usadas para agregar os dados. Pelo menos uma dimensão é necessária, mas várias dimensões podem ser especificadas para obter nível adicional de sub-agregação.

 *Medidas*  - Uma lista de medidas, também conhecidas como fatos, que são as métricas desejadas a serem agregadas com base nas dimensões especificadas.

 *Tendência*  - Instruções de controle adicionais para personalizar os dados de resultado.

 **Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.

 **Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).

 **Response Headers** - Sem outros headers.

 **Corpo de** Resposta - Abaixo está um exemplo de carga de resposta em JSON. Ele contém uma tabela de dados que contém os dados, também conterá um metadados, que mostra o tempo de execução da consulta e se os dados são do cache ou não.

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

 *Tempo de Execução*  - O tempo total que o servidor levou para retornar os dados. Isso pode ou não envolver cache.

 *Resultado de*  Dados - O resultado da consulta. Trata-se de uma matriz bidimensional contendo todas as permutações dos membros das dimensões e cada elemento contendo os nomes dos membros das dimensões, bem como os valores agregados das Medidas especificadas.

 *O resultado é De Cache*  - Para diagnóstico. Indica se o resultado veio do cache ou do cubo QoE.
