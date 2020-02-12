---
title: Obter o cubo
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
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Resumo: Saiba mais sobre a operação obter cubo, que faz parte da API de dados para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 1d8327439d79e7d02182dc7195bc0052bf6c923c
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888820"
---
# <a name="get-cube"></a><span data-ttu-id="bce58-104">Obter o cubo</span><span class="sxs-lookup"><span data-stu-id="bce58-104">Get Cube</span></span>
 
<span data-ttu-id="bce58-105">**Resumo:** Saiba mais sobre a operação obter cubo, que faz parte da API de dados para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="bce58-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="bce58-106">O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bce58-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="bce58-107">A operação obter cubo faz parte da API de dados para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="bce58-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="bce58-108">Obter o cubo</span><span class="sxs-lookup"><span data-stu-id="bce58-108">Get Cube</span></span>

<span data-ttu-id="bce58-109">Obter operação de cubo retorna a lista de dimensões e medidas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="bce58-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="bce58-110">**Forma**</span><span class="sxs-lookup"><span data-stu-id="bce58-110">**Method**</span></span>|<span data-ttu-id="bce58-111">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="bce58-111">**Request URI**</span></span>|<span data-ttu-id="bce58-112">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="bce58-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bce58-113">Obter</span><span class="sxs-lookup"><span data-stu-id="bce58-113">GET</span></span>  <br/> |<span data-ttu-id="bce58-114">https://\<do\>portal de/QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="bce58-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="bce58-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="bce58-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="bce58-116">**Parâmetros de URI** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="bce58-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="bce58-117">**Solicitar cabeçalhos** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="bce58-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="bce58-118">**Corpo da solicitação** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="bce58-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="bce58-119">**Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="bce58-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="bce58-120">**Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="bce58-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="bce58-121">**Cabeçalhos de resposta** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="bce58-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="bce58-122">**Corpo da resposta** -abaixo está uma carga de resposta de exemplo em JSON.</span><span class="sxs-lookup"><span data-stu-id="bce58-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bce58-123">Este exemplo está mostrando apenas dois primeiros elementos de cada grupo de elementos de cubo.</span><span class="sxs-lookup"><span data-stu-id="bce58-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
```json
{
"Kpis": [{
"FriendlyName": "Poor Trend Month",
"DataModelName": "[KPIValue].Poor Trend Month",
"Description": null
},
{
"FriendlyName": "Poor Rate Trend Month",
"DataModelName": "[KPIValue].Poor Rate Trend Month",
"Description": null
}],
"Dimensions": [{
"Category": "Access Location Pair",
"Attributes": [{
"FriendlyName": "Location Pair",
"DataModelName": "[Access Location Pair].[Location Pair]",
"Description": "Description of Location Pair"
}]
},
{
"Category": "Audio Bandwidth Est",
"Attributes": [{
"FriendlyName": "Metric",
"DataModelName": "[Audio Bandwidth Est].[Metric]",
"Description": "Description of Metric"
}]
}],
"Measurements": [{
"FriendlyName": "Audio Streams Count",
"DataModelName": "[Measures].[Audio Streams Count]",
"Description": "Description of Audio Streams Count"
},
{
"FriendlyName": "Audio Good Streams JPDR Count",
"DataModelName": "[Measures].[Audio Good Streams JPDR Count]",
"Description": "Description of Audio Good Streams JPDR Count"
}]
}
```

 <span data-ttu-id="bce58-124">*KPIs* -reservado.</span><span class="sxs-lookup"><span data-stu-id="bce58-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="bce58-125">A seção KPIs de uma carga de solicitação permite que a operação de execução de consulta retorne valores para os KPIs definidos no cubo.</span><span class="sxs-lookup"><span data-stu-id="bce58-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="bce58-126">Ainda não existem KPIs no cubo QoE.</span><span class="sxs-lookup"><span data-stu-id="bce58-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="bce58-127">*Dimensions* -a lista de dimensões que podem ser usadas em seções de filtros e dimensões de uma carga de solicitação para executar a operação de consulta.</span><span class="sxs-lookup"><span data-stu-id="bce58-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="bce58-128">Para usar uma dimensão em uma expressão de filtro, você precisa especificar um membro de dimensão, que pode ser obtido usando a operação obter membros da dimensão.</span><span class="sxs-lookup"><span data-stu-id="bce58-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="bce58-129">*Medições* – a lista de medições que podem ser usadas na seção medidas de uma carga de solicitação para executar a operação de consulta.</span><span class="sxs-lookup"><span data-stu-id="bce58-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

