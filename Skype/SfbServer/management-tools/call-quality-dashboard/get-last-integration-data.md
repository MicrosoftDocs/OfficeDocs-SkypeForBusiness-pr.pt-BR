---
title: Obter os Últimos Dados de Integração
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
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: 'Resumo: saiba mais sobre a operação Obter Últimos Dados de Integração, que faz parte da API de Dados para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: c40041e41e04d2bdc62a9eb9fa1eb699697a5b3d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832511"
---
# <a name="get-last-integration-data"></a><span data-ttu-id="f117e-104">Obter os Últimos Dados de Integração</span><span class="sxs-lookup"><span data-stu-id="f117e-104">Get Last Integration Data</span></span>
 
<span data-ttu-id="f117e-105">**Resumo:** Saiba mais sobre a operação Obter Últimos Dados de Integração, que faz parte da API de Dados para Painel de Qualidade de Chamada.</span><span class="sxs-lookup"><span data-stu-id="f117e-105">**Summary:** Learn about the Get Last Integration Data operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="f117e-106">O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f117e-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="f117e-107">A operação Obter Últimos Dados de Integração faz parte da API de Dados do Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="f117e-107">The Get Last Integration Data operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-last-integration-data"></a><span data-ttu-id="f117e-108">Obter os Últimos Dados de Integração</span><span class="sxs-lookup"><span data-stu-id="f117e-108">Get Last Integration Data</span></span>

<span data-ttu-id="f117e-109">A operação Obter Dados da Última Integração retorna a lista dos últimos 5 êxitos/falhas de arquivamento e processamento de cubos.</span><span class="sxs-lookup"><span data-stu-id="f117e-109">Get Last Integration Data operation returns the list of last 5 success/failure of archiving and cube processing.</span></span>
  
<span data-ttu-id="f117e-110">Esse recurso está desabilitado por padrão e precisa ser habilitado configurando a API de Dados.</span><span class="sxs-lookup"><span data-stu-id="f117e-110">This feature is disabled by default and it needs to be enabled by configuring the Data API.</span></span>
  

|<span data-ttu-id="f117e-111">**Method**</span><span class="sxs-lookup"><span data-stu-id="f117e-111">**Method**</span></span>|<span data-ttu-id="f117e-112">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="f117e-112">**Request URI**</span></span>|<span data-ttu-id="f117e-113">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="f117e-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f117e-114">OBTER</span><span class="sxs-lookup"><span data-stu-id="f117e-114">GET</span></span>  <br/> |<span data-ttu-id="f117e-115">https:// \<portal\> /QoEDataService/IntegrationLog/Status</span><span class="sxs-lookup"><span data-stu-id="f117e-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span></span>  <br/> |<span data-ttu-id="f117e-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="f117e-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="f117e-117">**Parâmetros de URI** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f117e-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="f117e-118">**Solicitação de headers** - nenhum outro.</span><span class="sxs-lookup"><span data-stu-id="f117e-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="f117e-119">**Corpo da Solicitação** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="f117e-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="f117e-120">**Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="f117e-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="f117e-121">**Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="f117e-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="f117e-122">**Response Headers** - Sem outros headers.</span><span class="sxs-lookup"><span data-stu-id="f117e-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="f117e-123">**Corpo de Resposta** - Abaixo está um exemplo de status do log.</span><span class="sxs-lookup"><span data-stu-id="f117e-123">**Response Body** - Below is a sample log status.</span></span>
  
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
