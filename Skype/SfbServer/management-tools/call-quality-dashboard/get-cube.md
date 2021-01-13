---
title: Obter o Cubo
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
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Resumo: saiba mais sobre a operação Obter Cubo, que faz parte da API de Dados do Painel de Qualidade de Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: a3527f21bc1751c23bba088ae06c3e6702cb8c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832621"
---
# <a name="get-cube"></a><span data-ttu-id="61c6f-104">Obter o Cubo</span><span class="sxs-lookup"><span data-stu-id="61c6f-104">Get Cube</span></span>
 
<span data-ttu-id="61c6f-105">**Resumo:** Saiba mais sobre a operação Obter Cubo, que faz parte da API de Dados do Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="61c6f-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="61c6f-106">O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="61c6f-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="61c6f-107">A operação Obter Cubo faz parte da API de Dados do Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="61c6f-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="61c6f-108">Obter o Cubo</span><span class="sxs-lookup"><span data-stu-id="61c6f-108">Get Cube</span></span>

<span data-ttu-id="61c6f-109">A operação Obter Cubo retorna a lista de dimensões e medidas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="61c6f-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="61c6f-110">**Method**</span><span class="sxs-lookup"><span data-stu-id="61c6f-110">**Method**</span></span>|<span data-ttu-id="61c6f-111">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="61c6f-111">**Request URI**</span></span>|<span data-ttu-id="61c6f-112">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="61c6f-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="61c6f-113">OBTER</span><span class="sxs-lookup"><span data-stu-id="61c6f-113">GET</span></span>  <br/> |<span data-ttu-id="61c6f-114">https:// \<portal\> /QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="61c6f-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="61c6f-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="61c6f-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="61c6f-116">**Parâmetros de URI** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="61c6f-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="61c6f-117">**Solicitação de headers** - nenhum outro.</span><span class="sxs-lookup"><span data-stu-id="61c6f-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="61c6f-118">**Corpo da Solicitação** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="61c6f-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="61c6f-119">**Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="61c6f-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="61c6f-120">**Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="61c6f-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="61c6f-121">**Response Headers** - Sem outros headers.</span><span class="sxs-lookup"><span data-stu-id="61c6f-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="61c6f-122">**Corpo de** Resposta - Abaixo está um exemplo de carga de resposta em JSON.</span><span class="sxs-lookup"><span data-stu-id="61c6f-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="61c6f-123">Este exemplo mostra apenas os dois primeiros elementos de cada grupo de elementos Cube.</span><span class="sxs-lookup"><span data-stu-id="61c6f-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
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

 <span data-ttu-id="61c6f-124">*KPIs*  - Reservado.</span><span class="sxs-lookup"><span data-stu-id="61c6f-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="61c6f-125">A seção KPIs de uma carga de solicitação permite que a operação Executar Consulta retorne valores para os KPIs definidos no cubo.</span><span class="sxs-lookup"><span data-stu-id="61c6f-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="61c6f-126">Ainda não há KPIs no Cubo QoE.</span><span class="sxs-lookup"><span data-stu-id="61c6f-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="61c6f-127">*Dimensões*  - A lista de dimensões que podem ser usadas nas seções Filtros e Dimensões de uma carga de solicitação para a operação Executar Consulta.</span><span class="sxs-lookup"><span data-stu-id="61c6f-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="61c6f-128">Para usar uma dimensão em uma expressão de filtro, você precisa especificar um membro de dimensão, que pode ser obtido usando a operação Obter Membros da Dimensão.</span><span class="sxs-lookup"><span data-stu-id="61c6f-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="61c6f-129">*Medidas*  - A lista de medidas que podem ser usadas na seção Medidas de uma carga de solicitação para a operação Executar Consulta.</span><span class="sxs-lookup"><span data-stu-id="61c6f-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

