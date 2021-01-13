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
# <a name="run-query"></a><span data-ttu-id="e9a7a-104">Executar Consulta</span><span class="sxs-lookup"><span data-stu-id="e9a7a-104">Run Query</span></span>

<span data-ttu-id="e9a7a-105">**Resumo:** Saiba mais sobre a operação Executar Consulta, que faz parte da API de Dados para Painel de Qualidade de Chamada.</span><span class="sxs-lookup"><span data-stu-id="e9a7a-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="e9a7a-106">O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e9a7a-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="e9a7a-107">A operação Executar Consulta faz parte da API de Dados do Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="e9a7a-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>

## <a name="run-query"></a><span data-ttu-id="e9a7a-108">Executar Consulta</span><span class="sxs-lookup"><span data-stu-id="e9a7a-108">Run Query</span></span>

<span data-ttu-id="e9a7a-109">A operação Executar Consulta oferece a capacidade de executar uma consulta no cubo com base em dimensões, medidas e filtros especificados e retornar os dados.</span><span class="sxs-lookup"><span data-stu-id="e9a7a-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>


|<span data-ttu-id="e9a7a-110">**Method**</span><span class="sxs-lookup"><span data-stu-id="e9a7a-110">**Method**</span></span>|<span data-ttu-id="e9a7a-111">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="e9a7a-111">**Request URI**</span></span>|<span data-ttu-id="e9a7a-112">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="e9a7a-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e9a7a-113">POSTAR</span><span class="sxs-lookup"><span data-stu-id="e9a7a-113">POST</span></span>  <br/> |<span data-ttu-id="e9a7a-114">https:// \<portal\> /QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="e9a7a-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="e9a7a-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="e9a7a-115">HTTP/1.1</span></span>  <br/> |

 <span data-ttu-id="e9a7a-116">**Parâmetros de URI** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="e9a7a-116">**URI Parameters** - None.</span></span>

 <span data-ttu-id="e9a7a-117">**Solicitação de headers** - nenhum outro.</span><span class="sxs-lookup"><span data-stu-id="e9a7a-117">**Request Headers** - No additional headers.</span></span>

 <span data-ttu-id="e9a7a-118">**Corpo da** Solicitação - Veja um exemplo de carga de solicitação em JSON.</span><span class="sxs-lookup"><span data-stu-id="e9a7a-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="e9a7a-119">Ele contém dimensões, filtros e medidas necessárias para uma consulta.</span><span class="sxs-lookup"><span data-stu-id="e9a7a-119">It contains dimensions, filters, and measurement required for a query.</span></span>

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

 <span data-ttu-id="e9a7a-120">*Filtros*  - Uma lista de expressões de filtro a serem aplicadas de forma que o conjunto de dados resultante reflita somente o subconjunto dos dados de interesse.</span><span class="sxs-lookup"><span data-stu-id="e9a7a-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>

 <span data-ttu-id="e9a7a-121">*Dimensões*  - Uma lista de dimensões que serão usadas para agregar os dados.</span><span class="sxs-lookup"><span data-stu-id="e9a7a-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="e9a7a-122">Pelo menos uma dimensão é necessária, mas várias dimensões podem ser especificadas para obter nível adicional de sub-agregação.</span><span class="sxs-lookup"><span data-stu-id="e9a7a-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>

 <span data-ttu-id="e9a7a-123">*Medidas*  - Uma lista de medidas, também conhecidas como fatos, que são as métricas desejadas a serem agregadas com base nas dimensões especificadas.</span><span class="sxs-lookup"><span data-stu-id="e9a7a-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>

 <span data-ttu-id="e9a7a-124">*Tendência*  - Instruções de controle adicionais para personalizar os dados de resultado.</span><span class="sxs-lookup"><span data-stu-id="e9a7a-124">*Trend*  - Additional control instructions to customize the result data.</span></span>

 <span data-ttu-id="e9a7a-125">**Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="e9a7a-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>

 <span data-ttu-id="e9a7a-126">**Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="e9a7a-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>

 <span data-ttu-id="e9a7a-127">**Response Headers** - Sem outros headers.</span><span class="sxs-lookup"><span data-stu-id="e9a7a-127">**Response Headers** - No additional headers.</span></span>

 <span data-ttu-id="e9a7a-128">**Corpo de** Resposta - Abaixo está um exemplo de carga de resposta em JSON.</span><span class="sxs-lookup"><span data-stu-id="e9a7a-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="e9a7a-129">Ele contém uma tabela de dados que contém os dados, também conterá um metadados, que mostra o tempo de execução da consulta e se os dados são do cache ou não.</span><span class="sxs-lookup"><span data-stu-id="e9a7a-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>

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

 <span data-ttu-id="e9a7a-130">*Tempo de Execução*  - O tempo total que o servidor levou para retornar os dados.</span><span class="sxs-lookup"><span data-stu-id="e9a7a-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="e9a7a-131">Isso pode ou não envolver cache.</span><span class="sxs-lookup"><span data-stu-id="e9a7a-131">This may or may not involve cache.</span></span>

 <span data-ttu-id="e9a7a-132">*Resultado de*  Dados - O resultado da consulta.</span><span class="sxs-lookup"><span data-stu-id="e9a7a-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="e9a7a-133">Trata-se de uma matriz bidimensional contendo todas as permutações dos membros das dimensões e cada elemento contendo os nomes dos membros das dimensões, bem como os valores agregados das Medidas especificadas.</span><span class="sxs-lookup"><span data-stu-id="e9a7a-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>

 <span data-ttu-id="e9a7a-134">*O resultado é De Cache*  - Para diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="e9a7a-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="e9a7a-135">Indica se o resultado veio do cache ou do cubo QoE.</span><span class="sxs-lookup"><span data-stu-id="e9a7a-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>
