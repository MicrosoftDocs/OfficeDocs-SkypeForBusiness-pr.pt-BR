---
title: Executar Consulta
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 'Resumo: Saiba mais sobre a operação de executar consulta, que é parte da API de dados para o painel de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: 8a1bea338039914695e16d1294f28abfe1e4b559
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899148"
---
# <a name="run-query"></a>Executar Consulta

**Resumo:** Saiba mais sobre a operação de executar consulta, que é parte da API de dados para o painel de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.

A operação de executar consulta é parte da API de dados para o painel de qualidade de chamada.

## <a name="run-query"></a>Executar Consulta

Execute a consulta operação fornece a capacidade de executar uma consulta no cubo com base em filtros, medidas e dimensões especificadas e retornar os dados de volta.


|**Método**|**URI de solicitação**|**Versão de HTTP**|
|:-----|:-----|:-----|
|Postar  <br/> |https://\<portal\>/QoEDataService/RunQuery  <br/> |HTTP/1.1  <br/> |

 **Parâmetros URI** - None.

 **Cabeçalhos de solicitação** - sem cabeçalhos adicionais.

 **Corpo da solicitação** - aqui é uma carga de solicitação de amostra em JSON. Ele contém dimensões, filtros e medida necessária para uma consulta.

```
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

 *Filtros* - uma lista de expressões de filtro a ser aplicado, de forma que o conjunto de dados resultante refletirão apenas o subconjunto dos dados interessantes.

 *Dimensões* - uma lista de dimensões que será usado para os dados de agregação. Pelo menos uma dimensão é necessária mas várias dimensões podem ser especificados para obter um nível adicional de agregações subsites.

 *Medições* - uma lista de medidas, também conhecido como fatos, que são as métricas desejadas a ser agregado baseadas nas dimensões especificadas por você.

 *Tendência* - instruções de controle adicional para personalizar os dados resultantes.

 **Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.

 **Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).

 **Cabeçalhos de resposta** - sem cabeçalhos adicionais.

 **Corpo de resposta** - abaixo é uma carga de resposta de exemplo em JSON. Ele contém uma tabela de dados que contém os dados, também conterá um metadados, que mostra o tempo de execução de consulta e se são ou não os dados do cache.

```
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

 *Tempo de execução* - o tempo total necessário para que o servidor retornar os dados. Isso pode ou não pode envolver cache.

 *Resultado de dados* - o resultado da consulta. É uma matriz bidimensional que contém todas as permutas dos membros das dimensões e cada elemento contendo nomes de membros das dimensões, bem como os valores agregados das medidas especificados.

 *Resultado é o Cache de* - de diagnósticos. Indica se o resultado provém do cache ou do cubo QoE.
