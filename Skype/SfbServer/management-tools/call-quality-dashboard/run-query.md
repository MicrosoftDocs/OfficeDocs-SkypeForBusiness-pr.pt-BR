---
title: Executar a consulta
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 'Resumo: Saiba mais sobre a operação de executar consulta, que é parte da API de dados para o painel de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.'
ms.openlocfilehash: 720bcc16b89ed2cd2b92eababb389d6c363d734d
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375636"
---
# <a name="run-query"></a><span data-ttu-id="dbf3d-104">Executar a consulta</span><span class="sxs-lookup"><span data-stu-id="dbf3d-104">Run Query</span></span>

<span data-ttu-id="dbf3d-105">**Resumo:** Saiba mais sobre a operação de executar consulta, que é parte da API de dados para o painel de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="dbf3d-106">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>

<span data-ttu-id="dbf3d-107">A operação de executar consulta é parte da API de dados para o painel de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>

## <a name="run-query"></a><span data-ttu-id="dbf3d-108">Executar a consulta</span><span class="sxs-lookup"><span data-stu-id="dbf3d-108">Run Query</span></span>

<span data-ttu-id="dbf3d-109">Execute a consulta operação fornece a capacidade de executar uma consulta no cubo com base em filtros, medidas e dimensões especificadas e retornar os dados de volta.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>


|<span data-ttu-id="dbf3d-110">**Método**</span><span class="sxs-lookup"><span data-stu-id="dbf3d-110">**Method**</span></span>|<span data-ttu-id="dbf3d-111">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="dbf3d-111">**Request URI**</span></span>|<span data-ttu-id="dbf3d-112">**Versão de HTTP**</span><span class="sxs-lookup"><span data-stu-id="dbf3d-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dbf3d-113">Postar</span><span class="sxs-lookup"><span data-stu-id="dbf3d-113">POST</span></span>  <br/> |<span data-ttu-id="dbf3d-114">https://\<portal\>/QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="dbf3d-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="dbf3d-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="dbf3d-115">HTTP/1.1</span></span>  <br/> |

 <span data-ttu-id="dbf3d-116">**Parâmetros URI** - None.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-116">**URI Parameters** - None.</span></span>

 <span data-ttu-id="dbf3d-117">**Cabeçalhos de solicitação** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-117">**Request Headers** - No additional headers.</span></span>

 <span data-ttu-id="dbf3d-118">**Corpo da solicitação** - aqui é uma carga de solicitação de amostra em JSON.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="dbf3d-119">Ele contém dimensões, filtros e medida necessária para uma consulta.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-119">It contains dimensions, filters, and measurement required for a query.</span></span>

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

 <span data-ttu-id="dbf3d-120">*Filtros* - uma lista de expressões de filtro a ser aplicado, de forma que o conjunto de dados resultante refletirão apenas o subconjunto dos dados interessantes.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>

 <span data-ttu-id="dbf3d-121">*Dimensões* - uma lista de dimensões que será usado para os dados de agregação.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="dbf3d-122">Pelo menos uma dimensão é necessária mas várias dimensões podem ser especificados para obter um nível adicional de agregações subsites.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>

 <span data-ttu-id="dbf3d-123">*Medições* - uma lista de medidas, também conhecido como fatos, que são as métricas desejadas a ser agregado baseadas nas dimensões especificadas por você.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>

 <span data-ttu-id="dbf3d-124">*Tendência* - instruções de controle adicional para personalizar os dados resultantes.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-124">*Trend*  - Additional control instructions to customize the result data.</span></span>

 <span data-ttu-id="dbf3d-125">**Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>

 <span data-ttu-id="dbf3d-126">**Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).</span><span class="sxs-lookup"><span data-stu-id="dbf3d-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>

 <span data-ttu-id="dbf3d-127">**Cabeçalhos de resposta** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-127">**Response Headers** - No additional headers.</span></span>

 <span data-ttu-id="dbf3d-128">**Corpo de resposta** - abaixo é uma carga de resposta de exemplo em JSON.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="dbf3d-129">Ele contém uma tabela de dados que contém os dados, também conterá um metadados, que mostra o tempo de execução de consulta e se são ou não os dados do cache.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>

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

 <span data-ttu-id="dbf3d-130">*Tempo de execução* - o tempo total necessário para que o servidor retornar os dados.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="dbf3d-131">Isso pode ou não pode envolver cache.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-131">This may or may not involve cache.</span></span>

 <span data-ttu-id="dbf3d-132">*Resultado de dados* - o resultado da consulta.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="dbf3d-133">É uma matriz bidimensional que contém todas as permutas dos membros das dimensões e cada elemento contendo nomes de membros das dimensões, bem como os valores agregados das medidas especificados.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>

 <span data-ttu-id="dbf3d-134">*Resultado é o Cache de* - de diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="dbf3d-135">Indica se o resultado provém do cache ou do cubo QoE.</span><span class="sxs-lookup"><span data-stu-id="dbf3d-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>