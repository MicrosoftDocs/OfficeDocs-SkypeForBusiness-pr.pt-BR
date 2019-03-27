---
title: Obter o cubo
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Resumo: Saiba mais sobre a operação obter cubo, que é parte da API de dados para o painel de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: 5c0623b92c9169a9e54f92d21358fb377c84a8f8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897133"
---
# <a name="get-cube"></a><span data-ttu-id="80b0f-104">Obter o cubo</span><span class="sxs-lookup"><span data-stu-id="80b0f-104">Get Cube</span></span>
 
<span data-ttu-id="80b0f-105">**Resumo:** Saiba mais sobre a operação obter cubo, que é parte da API de dados para o painel de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="80b0f-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="80b0f-106">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="80b0f-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="80b0f-107">A operação obter cubo é parte da API de dados para o painel de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="80b0f-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="80b0f-108">Obter o cubo</span><span class="sxs-lookup"><span data-stu-id="80b0f-108">Get Cube</span></span>

<span data-ttu-id="80b0f-109">Operação de cubo Get retorna a lista de medidas e dimensões disponíveis.</span><span class="sxs-lookup"><span data-stu-id="80b0f-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="80b0f-110">**Método**</span><span class="sxs-lookup"><span data-stu-id="80b0f-110">**Method**</span></span>|<span data-ttu-id="80b0f-111">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="80b0f-111">**Request URI**</span></span>|<span data-ttu-id="80b0f-112">**Versão de HTTP**</span><span class="sxs-lookup"><span data-stu-id="80b0f-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="80b0f-113">Obter</span><span class="sxs-lookup"><span data-stu-id="80b0f-113">GET</span></span>  <br/> |<span data-ttu-id="80b0f-114">https://\<portal\>/QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="80b0f-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="80b0f-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="80b0f-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="80b0f-116">**Parâmetros URI** - None.</span><span class="sxs-lookup"><span data-stu-id="80b0f-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="80b0f-117">**Cabeçalhos de solicitação** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="80b0f-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="80b0f-118">O **corpo da solicitação** - None.</span><span class="sxs-lookup"><span data-stu-id="80b0f-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="80b0f-119">**Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="80b0f-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="80b0f-120">**Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).</span><span class="sxs-lookup"><span data-stu-id="80b0f-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="80b0f-121">**Cabeçalhos de resposta** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="80b0f-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="80b0f-122">**Corpo de resposta** - abaixo é uma carga de resposta de exemplo em JSON.</span><span class="sxs-lookup"><span data-stu-id="80b0f-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="80b0f-123">Esta amostra apenas está mostrando as duas primeiras elementos de cada grupos de elementos de cubo.</span><span class="sxs-lookup"><span data-stu-id="80b0f-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
```
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

 <span data-ttu-id="80b0f-124">*KPIs* - reservado.</span><span class="sxs-lookup"><span data-stu-id="80b0f-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="80b0f-125">A seção de KPIs a carga de solicitação permite que a operação de executar consulta retornar valores para os KPIs definidos no cubo.</span><span class="sxs-lookup"><span data-stu-id="80b0f-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="80b0f-126">Nenhum KPIs ainda existem no cubo do QoE.</span><span class="sxs-lookup"><span data-stu-id="80b0f-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="80b0f-127">*Dimensões* - lista de dimensões que podem ser usadas nas seções de filtros e dimensões de uma carga de solicitação para a operação de executar consulta.</span><span class="sxs-lookup"><span data-stu-id="80b0f-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="80b0f-128">Para usar uma dimensão em uma expressão de filtro, você precisará especificar um membro de dimensão, que pode ser obtido com a operação obter membros da dimensão.</span><span class="sxs-lookup"><span data-stu-id="80b0f-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="80b0f-129">*Medições* - lista de medidas que podem ser usadas na seção medidas de uma carga de solicitação para a operação de executar consulta.</span><span class="sxs-lookup"><span data-stu-id="80b0f-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

