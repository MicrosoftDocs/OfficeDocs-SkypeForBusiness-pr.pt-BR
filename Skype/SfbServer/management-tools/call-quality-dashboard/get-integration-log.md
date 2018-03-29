---
title: Obter o Log de integração
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Resumo: Saiba mais sobre a operação obter o Log de integração, que é parte da API de dados para o painel de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.'
ms.openlocfilehash: 8ccd4fc299cbf5310a5974d55b181aa1f42255ce
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="get-integration-log"></a><span data-ttu-id="83b3e-104">Obter o Log de integração</span><span class="sxs-lookup"><span data-stu-id="83b3e-104">Get Integration Log</span></span>
 
<span data-ttu-id="83b3e-105">**Resumo:** Saiba mais sobre a operação obter o Log de integração, que é parte da API de dados para o painel de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="83b3e-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="83b3e-106">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="83b3e-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="83b3e-107">A operação obter integração Log é parte da API de dados para o painel de qualidade de chamada</span><span class="sxs-lookup"><span data-stu-id="83b3e-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="83b3e-108">Obter o Log de integração</span><span class="sxs-lookup"><span data-stu-id="83b3e-108">Get Integration Log</span></span>

<span data-ttu-id="83b3e-109">Obtenha a operação retorna uma lista de entradas de log descrevendo as atividades no cubo de QoE de processamento de Log de integração.</span><span class="sxs-lookup"><span data-stu-id="83b3e-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="83b3e-110">Essa operação está desabilitada por padrão, por motivos de segurança.</span><span class="sxs-lookup"><span data-stu-id="83b3e-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="83b3e-111">Quando desabilitada, ela retornará uma sequência vazia.</span><span class="sxs-lookup"><span data-stu-id="83b3e-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="83b3e-112">Para habilitar essa operação, os administradores precisam configurar o Web. config para o aplicativo de web de host do API de dados.</span><span class="sxs-lookup"><span data-stu-id="83b3e-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="83b3e-113">Método</span><span class="sxs-lookup"><span data-stu-id="83b3e-113">Method</span></span>|<span data-ttu-id="83b3e-114">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="83b3e-114">**Request URI**</span></span>|<span data-ttu-id="83b3e-115">**Versão de HTTP**</span><span class="sxs-lookup"><span data-stu-id="83b3e-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="83b3e-116">Obter</span><span class="sxs-lookup"><span data-stu-id="83b3e-116">GET</span></span>  <br/> |<span data-ttu-id="83b3e-117">https://\<portal\>/QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="83b3e-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="83b3e-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="83b3e-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="83b3e-119">**Parâmetros URI** - None.</span><span class="sxs-lookup"><span data-stu-id="83b3e-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="83b3e-120">**Cabeçalhos de solicitação** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="83b3e-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="83b3e-121">O **corpo da solicitação** - None.</span><span class="sxs-lookup"><span data-stu-id="83b3e-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="83b3e-122">**Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="83b3e-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="83b3e-123">**Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).</span><span class="sxs-lookup"><span data-stu-id="83b3e-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="83b3e-124">**Cabeçalhos de resposta** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="83b3e-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="83b3e-125">**Corpo de resposta** - a seguir é uma estrutura de amostra de entradas de log.</span><span class="sxs-lookup"><span data-stu-id="83b3e-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]

```


