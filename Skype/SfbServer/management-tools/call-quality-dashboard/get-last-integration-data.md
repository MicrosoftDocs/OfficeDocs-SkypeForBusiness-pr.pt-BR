---
title: Obter dados de integração com o últimos
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: 'Resumo: Saiba mais sobre a operação obter dados de integração com o último, que é parte da API de dados para o painel de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: b2e759766987b6ee52795845ee55546920181807
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531784"
---
# <a name="get-last-integration-data"></a><span data-ttu-id="aaa5d-104">Obter dados de integração com o últimos</span><span class="sxs-lookup"><span data-stu-id="aaa5d-104">Get Last Integration Data</span></span>
 
<span data-ttu-id="aaa5d-105">**Resumo:** Saiba mais sobre a operação obter dados de integração com o último, que é parte da API de dados para o painel de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="aaa5d-105">**Summary:** Learn about the Get Last Integration Data operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="aaa5d-106">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="aaa5d-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="aaa5d-107">A operação de obter dados de integração com o último é parte da API de dados para o painel de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="aaa5d-107">The Get Last Integration Data operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-last-integration-data"></a><span data-ttu-id="aaa5d-108">Obter dados de integração com o últimos</span><span class="sxs-lookup"><span data-stu-id="aaa5d-108">Get Last Integration Data</span></span>

<span data-ttu-id="aaa5d-109">Operação de dados do último integração Get retorna a lista de sucesso últimas 5/falha de arquivamento e o processamento de cubo.</span><span class="sxs-lookup"><span data-stu-id="aaa5d-109">Get Last Integration Data operation returns the list of last 5 success/failure of archiving and cube processing.</span></span>
  
<span data-ttu-id="aaa5d-110">Esse recurso é desabilitado por padrão, e ele precisa estar habilitado, configurando a API de dados.</span><span class="sxs-lookup"><span data-stu-id="aaa5d-110">This feature is disabled by default and it needs to be enabled by configuring the Data API.</span></span>
  

|<span data-ttu-id="aaa5d-111">**Método**</span><span class="sxs-lookup"><span data-stu-id="aaa5d-111">**Method**</span></span>|<span data-ttu-id="aaa5d-112">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="aaa5d-112">**Request URI**</span></span>|<span data-ttu-id="aaa5d-113">**Versão de HTTP**</span><span class="sxs-lookup"><span data-stu-id="aaa5d-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aaa5d-114">Obter</span><span class="sxs-lookup"><span data-stu-id="aaa5d-114">GET</span></span>  <br/> |<span data-ttu-id="aaa5d-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span><span class="sxs-lookup"><span data-stu-id="aaa5d-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span></span>  <br/> |<span data-ttu-id="aaa5d-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="aaa5d-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="aaa5d-117">**Parâmetros URI** - None.</span><span class="sxs-lookup"><span data-stu-id="aaa5d-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="aaa5d-118">**Cabeçalhos de solicitação** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="aaa5d-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="aaa5d-119">O **corpo da solicitação** - None.</span><span class="sxs-lookup"><span data-stu-id="aaa5d-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="aaa5d-120">**Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="aaa5d-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="aaa5d-121">**Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).</span><span class="sxs-lookup"><span data-stu-id="aaa5d-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="aaa5d-122">**Cabeçalhos de resposta** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="aaa5d-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="aaa5d-123">**Corpo de resposta** - abaixo é um status de log da amostra.</span><span class="sxs-lookup"><span data-stu-id="aaa5d-123">**Response Body** - Below is a sample log status.</span></span>
  
```
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