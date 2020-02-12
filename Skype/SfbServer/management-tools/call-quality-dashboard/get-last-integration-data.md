---
title: Obter Últimos Dados de Integração
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
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: 'Resumo: Saiba mais sobre a operação obter a última data de integração, que faz parte da API de dados para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: a4b455a543dd77f0edce223f43d64fe5c03e4bcb
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888790"
---
# <a name="get-last-integration-data"></a><span data-ttu-id="0eaaf-104">Obter Últimos Dados de Integração</span><span class="sxs-lookup"><span data-stu-id="0eaaf-104">Get Last Integration Data</span></span>
 
<span data-ttu-id="0eaaf-105">**Resumo:** Saiba mais sobre a operação obter a última data de integração, que faz parte da API de dados para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="0eaaf-105">**Summary:** Learn about the Get Last Integration Data operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="0eaaf-106">O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0eaaf-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="0eaaf-107">A operação obter a última integração de dados faz parte da API de dados para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="0eaaf-107">The Get Last Integration Data operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-last-integration-data"></a><span data-ttu-id="0eaaf-108">Obter Últimos Dados de Integração</span><span class="sxs-lookup"><span data-stu-id="0eaaf-108">Get Last Integration Data</span></span>

<span data-ttu-id="0eaaf-109">Obter a última operação de dados de integração retorna a lista de cinco recentes sucessos/falhas de arquivamento e processamento de cubo.</span><span class="sxs-lookup"><span data-stu-id="0eaaf-109">Get Last Integration Data operation returns the list of last 5 success/failure of archiving and cube processing.</span></span>
  
<span data-ttu-id="0eaaf-110">Esse recurso está desabilitado por padrão e precisa ser habilitado Configurando a API de dados.</span><span class="sxs-lookup"><span data-stu-id="0eaaf-110">This feature is disabled by default and it needs to be enabled by configuring the Data API.</span></span>
  

|<span data-ttu-id="0eaaf-111">**Forma**</span><span class="sxs-lookup"><span data-stu-id="0eaaf-111">**Method**</span></span>|<span data-ttu-id="0eaaf-112">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="0eaaf-112">**Request URI**</span></span>|<span data-ttu-id="0eaaf-113">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="0eaaf-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0eaaf-114">Obter</span><span class="sxs-lookup"><span data-stu-id="0eaaf-114">GET</span></span>  <br/> |<span data-ttu-id="0eaaf-115">https://\<do\>portal de/QoEDataService/IntegrationLog/status</span><span class="sxs-lookup"><span data-stu-id="0eaaf-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span></span>  <br/> |<span data-ttu-id="0eaaf-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="0eaaf-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="0eaaf-117">**Parâmetros de URI** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="0eaaf-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="0eaaf-118">**Solicitar cabeçalhos** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="0eaaf-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0eaaf-119">**Corpo da solicitação** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="0eaaf-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="0eaaf-120">**Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="0eaaf-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="0eaaf-121">**Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="0eaaf-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="0eaaf-122">**Cabeçalhos de resposta** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="0eaaf-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0eaaf-123">**Corpo da resposta** -abaixo está um exemplo de status do log.</span><span class="sxs-lookup"><span data-stu-id="0eaaf-123">**Response Body** - Below is a sample log status.</span></span>
  
```json
{
"LastSuccessIntegrations": ["01/18/2015 10:30:13",
"01/18/2015 10:28:29",
"01/17/2015 15:15:17",
"01/17/2015 15:00:17",
"01/17/2015 14:45:13"],
"LastSuccessCubeProcessings": ["01/17/2015 15:16:40",
"01/17/2015 15:01:41",
"01/17/2015 14:47:19",
"01/17/2015 14:31:40",
"01/17/2015 14:17:01"],
"LastFailedIntegrations":  ,
"LastFailedCubeProcessings": ["01/18/2015 10:30:58",
"01/18/2015 10:29:28",
"01/17/2015 10:02:20",
"01/15/2015 20:01:56",
"01/15/2015 19:45:50"],
"LastDataIntegrationStart": null,
"LastCubeProcessingStart": "01/18/2015 10:30:16"
}
```
