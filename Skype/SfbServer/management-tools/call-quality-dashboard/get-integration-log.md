---
title: Obter o Log de integração
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Resumo: Saiba mais sobre a operação obter o Log de integração, que é parte da API de dados para o painel de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: 6408d0a773ee00854f82c4430e4402e79db23fa6
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531085"
---
# <a name="get-integration-log"></a><span data-ttu-id="9d155-104">Obter o Log de integração</span><span class="sxs-lookup"><span data-stu-id="9d155-104">Get Integration Log</span></span>
 
<span data-ttu-id="9d155-105">**Resumo:** Saiba mais sobre a operação obter o Log de integração, que é parte da API de dados para o painel de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="9d155-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="9d155-106">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="9d155-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="9d155-107">A operação obter integração Log é parte da API de dados para o painel de qualidade de chamada</span><span class="sxs-lookup"><span data-stu-id="9d155-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="9d155-108">Obter o Log de integração</span><span class="sxs-lookup"><span data-stu-id="9d155-108">Get Integration Log</span></span>

<span data-ttu-id="9d155-109">Obtenha a operação retorna uma lista de entradas de log descrevendo as atividades no cubo de QoE de processamento de Log de integração.</span><span class="sxs-lookup"><span data-stu-id="9d155-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="9d155-110">Essa operação está desabilitada por padrão, por motivos de segurança.</span><span class="sxs-lookup"><span data-stu-id="9d155-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="9d155-111">Quando desabilitada, ela retornará uma sequência vazia.</span><span class="sxs-lookup"><span data-stu-id="9d155-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="9d155-112">Para habilitar essa operação, os administradores precisam configurar o Web. config para o aplicativo de web de host do API de dados.</span><span class="sxs-lookup"><span data-stu-id="9d155-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="9d155-113">Método</span><span class="sxs-lookup"><span data-stu-id="9d155-113">Method</span></span>|<span data-ttu-id="9d155-114">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="9d155-114">**Request URI**</span></span>|<span data-ttu-id="9d155-115">**Versão de HTTP**</span><span class="sxs-lookup"><span data-stu-id="9d155-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9d155-116">Obter</span><span class="sxs-lookup"><span data-stu-id="9d155-116">GET</span></span>  <br/> |<span data-ttu-id="9d155-117">https://\<portal\>/QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="9d155-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="9d155-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="9d155-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="9d155-119">**Parâmetros URI** - None.</span><span class="sxs-lookup"><span data-stu-id="9d155-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="9d155-120">**Cabeçalhos de solicitação** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="9d155-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9d155-121">O **corpo da solicitação** - None.</span><span class="sxs-lookup"><span data-stu-id="9d155-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="9d155-122">**Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="9d155-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="9d155-123">**Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).</span><span class="sxs-lookup"><span data-stu-id="9d155-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="9d155-124">**Cabeçalhos de resposta** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="9d155-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9d155-125">**Corpo de resposta** - a seguir é uma estrutura de amostra de entradas de log.</span><span class="sxs-lookup"><span data-stu-id="9d155-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


