---
title: Executar Consulta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 'Resumo: Saiba mais sobre a operação executar consulta, que faz parte da API de dados para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 4e520921496a1650af12b342fd5a0244fe9eb7a5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816680"
---
# <a name="run-query"></a><span data-ttu-id="47421-104">Executar Consulta</span><span class="sxs-lookup"><span data-stu-id="47421-104">Run Query</span></span>

<span data-ttu-id="47421-105">**Resumo:** Saiba mais sobre a operação executar consulta, que faz parte da API de dados para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="47421-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="47421-106">O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="47421-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="47421-107">A operação executar consulta faz parte da API de dados para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="47421-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>

## <a name="run-query"></a><span data-ttu-id="47421-108">Executar Consulta</span><span class="sxs-lookup"><span data-stu-id="47421-108">Run Query</span></span>

<span data-ttu-id="47421-109">Executar a operação de consulta fornece a capacidade de executar uma consulta no cubo com base em dimensões, medidas e filtros especificados e retornar os dados.</span><span class="sxs-lookup"><span data-stu-id="47421-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>


|<span data-ttu-id="47421-110">**Forma**</span><span class="sxs-lookup"><span data-stu-id="47421-110">**Method**</span></span>|<span data-ttu-id="47421-111">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="47421-111">**Request URI**</span></span>|<span data-ttu-id="47421-112">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="47421-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="47421-113">Postar</span><span class="sxs-lookup"><span data-stu-id="47421-113">POST</span></span>  <br/> |<span data-ttu-id="47421-114">https://\<do\>portal de/QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="47421-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="47421-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="47421-115">HTTP/1.1</span></span>  <br/> |

 <span data-ttu-id="47421-116">**Parâmetros de URI** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="47421-116">**URI Parameters** - None.</span></span>

 <span data-ttu-id="47421-117">**Solicitar cabeçalhos** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="47421-117">**Request Headers** - No additional headers.</span></span>

 <span data-ttu-id="47421-118">**Corpo da solicitação** -aqui está um exemplo de carga de solicitação em JSON.</span><span class="sxs-lookup"><span data-stu-id="47421-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="47421-119">Ele contém dimensões, filtros e medidas necessárias para uma consulta.</span><span class="sxs-lookup"><span data-stu-id="47421-119">It contains dimensions, filters, and measurement required for a query.</span></span>

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

 <span data-ttu-id="47421-120">*Filtros* -uma lista de expressões de filtro a ser aplicada de forma que o conjunto de dados resultante reflita apenas o subconjunto dos dados que são de interesse.</span><span class="sxs-lookup"><span data-stu-id="47421-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>

 <span data-ttu-id="47421-121">*Dimensões* -uma lista de dimensões que será usada para agregar os dados.</span><span class="sxs-lookup"><span data-stu-id="47421-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="47421-122">Pelo menos uma dimensão é necessária, mas várias dimensões podem ser especificadas para obter um nível adicional de subagregações.</span><span class="sxs-lookup"><span data-stu-id="47421-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>

 <span data-ttu-id="47421-123">*Medições* – uma lista de medições, também conhecidas como fatos, que são as métricas desejadas a serem agregadas com base nas dimensões que você especificou.</span><span class="sxs-lookup"><span data-stu-id="47421-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>

 <span data-ttu-id="47421-124">*Tendência* -instruções de controle adicionais para personalizar os dados do resultado.</span><span class="sxs-lookup"><span data-stu-id="47421-124">*Trend*  - Additional control instructions to customize the result data.</span></span>

 <span data-ttu-id="47421-125">**Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="47421-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>

 <span data-ttu-id="47421-126">**Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="47421-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>

 <span data-ttu-id="47421-127">**Cabeçalhos de resposta** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="47421-127">**Response Headers** - No additional headers.</span></span>

 <span data-ttu-id="47421-128">**Corpo da resposta** -abaixo está uma carga de resposta de exemplo em JSON.</span><span class="sxs-lookup"><span data-stu-id="47421-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="47421-129">Ele contém uma tabela de dados que contém os dados; além disso, ele conterá um metadados, que mostra o tempo de execução da consulta e se os dados são do cache.</span><span class="sxs-lookup"><span data-stu-id="47421-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>

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

 <span data-ttu-id="47421-130">*Tempo de execução* – o tempo total necessário para que o servidor retorne os dados.</span><span class="sxs-lookup"><span data-stu-id="47421-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="47421-131">Isso pode ou não incluir o cache.</span><span class="sxs-lookup"><span data-stu-id="47421-131">This may or may not involve cache.</span></span>

 <span data-ttu-id="47421-132">*Resultado dos dados* -o resultado da consulta.</span><span class="sxs-lookup"><span data-stu-id="47421-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="47421-133">É uma matriz bidimensional contendo todas as permutações de membros das dimensões e cada elemento que contém os nomes dos membros das dimensões, bem como os valores agregados das medidas especificadas.</span><span class="sxs-lookup"><span data-stu-id="47421-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>

 <span data-ttu-id="47421-134">O *resultado é do cache* -para diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="47421-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="47421-135">Indica se o resultado veio do cache ou do cubo de QoE.</span><span class="sxs-lookup"><span data-stu-id="47421-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>
