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
ms.openlocfilehash: 1b21e078578b9e198c743f77f77e4beca94ddeaf
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294829"
---
# <a name="get-integration-log"></a><span data-ttu-id="5221c-104">Obter o Log de integração</span><span class="sxs-lookup"><span data-stu-id="5221c-104">Get Integration Log</span></span>
 
<span data-ttu-id="5221c-105">**Resumo:** Saiba mais sobre a operação obter o Log de integração, que é parte da API de dados para o painel de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="5221c-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="5221c-106">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5221c-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5221c-107">A operação obter integração Log é parte da API de dados para o painel de qualidade de chamada</span><span class="sxs-lookup"><span data-stu-id="5221c-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="5221c-108">Obter o Log de integração</span><span class="sxs-lookup"><span data-stu-id="5221c-108">Get Integration Log</span></span>

<span data-ttu-id="5221c-109">Obtenha a operação retorna uma lista de entradas de log descrevendo as atividades no cubo de QoE de processamento de Log de integração.</span><span class="sxs-lookup"><span data-stu-id="5221c-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="5221c-110">Essa operação está desabilitada por padrão, por motivos de segurança.</span><span class="sxs-lookup"><span data-stu-id="5221c-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="5221c-111">Quando desabilitada, ela retornará uma sequência vazia.</span><span class="sxs-lookup"><span data-stu-id="5221c-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="5221c-112">Para habilitar essa operação, os administradores precisam configurar o Web. config para o aplicativo de web de host do API de dados.</span><span class="sxs-lookup"><span data-stu-id="5221c-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="5221c-113">Método</span><span class="sxs-lookup"><span data-stu-id="5221c-113">Method</span></span>|<span data-ttu-id="5221c-114">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="5221c-114">**Request URI**</span></span>|<span data-ttu-id="5221c-115">**Versão de HTTP**</span><span class="sxs-lookup"><span data-stu-id="5221c-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5221c-116">Obter</span><span class="sxs-lookup"><span data-stu-id="5221c-116">GET</span></span>  <br/> |<span data-ttu-id="5221c-117">https://\<portal\>/QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="5221c-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="5221c-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="5221c-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="5221c-119">**Parâmetros URI** - None.</span><span class="sxs-lookup"><span data-stu-id="5221c-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="5221c-120">**Cabeçalhos de solicitação** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="5221c-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="5221c-121">O **corpo da solicitação** - None.</span><span class="sxs-lookup"><span data-stu-id="5221c-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="5221c-122">**Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="5221c-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="5221c-123">**Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).</span><span class="sxs-lookup"><span data-stu-id="5221c-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="5221c-124">**Cabeçalhos de resposta** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="5221c-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="5221c-125">**Corpo de resposta** - a seguir é uma estrutura de amostra de entradas de log.</span><span class="sxs-lookup"><span data-stu-id="5221c-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


