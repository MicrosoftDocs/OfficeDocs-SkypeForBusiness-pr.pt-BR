---
title: Obter o Log de integração
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
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Resumo: Saiba mais sobre a operação obter log de integração, que faz parte da API de dados para o painel de qualidade de chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 9caa909e80a0bab5257af16fe77e9d154947a56e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816810"
---
# <a name="get-integration-log"></a><span data-ttu-id="c2fa5-104">Obter o Log de integração</span><span class="sxs-lookup"><span data-stu-id="c2fa5-104">Get Integration Log</span></span>
 
<span data-ttu-id="c2fa5-105">**Resumo:** Saiba mais sobre a operação obter log de integração, que faz parte da API de dados para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="c2fa5-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="c2fa5-106">O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c2fa5-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="c2fa5-107">A operação obter log de integração faz parte da API de dados para o painel de qualidade da chamada</span><span class="sxs-lookup"><span data-stu-id="c2fa5-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="c2fa5-108">Obter o Log de integração</span><span class="sxs-lookup"><span data-stu-id="c2fa5-108">Get Integration Log</span></span>

<span data-ttu-id="c2fa5-109">A operação obter log de integração retorna uma lista de entradas de log que descrevem as atividades em processamento de cubo QoE.</span><span class="sxs-lookup"><span data-stu-id="c2fa5-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="c2fa5-110">Esta operação é desativada por padrão por motivos de segurança.</span><span class="sxs-lookup"><span data-stu-id="c2fa5-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="c2fa5-111">Quando desabilitado, ele retorna uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="c2fa5-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="c2fa5-112">Para habilitar essa operação, os administradores precisam configurar o Web. config do aplicativo Web host da API de dados.</span><span class="sxs-lookup"><span data-stu-id="c2fa5-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="c2fa5-113">Forma</span><span class="sxs-lookup"><span data-stu-id="c2fa5-113">Method</span></span>|<span data-ttu-id="c2fa5-114">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="c2fa5-114">**Request URI**</span></span>|<span data-ttu-id="c2fa5-115">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="c2fa5-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c2fa5-116">Obter</span><span class="sxs-lookup"><span data-stu-id="c2fa5-116">GET</span></span>  <br/> |<span data-ttu-id="c2fa5-117">https://\<do\>portal de/QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="c2fa5-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="c2fa5-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="c2fa5-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="c2fa5-119">**Parâmetros de URI** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="c2fa5-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="c2fa5-120">**Solicitar cabeçalhos** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="c2fa5-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c2fa5-121">**Corpo da solicitação** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="c2fa5-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="c2fa5-122">**Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="c2fa5-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="c2fa5-123">**Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="c2fa5-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="c2fa5-124">**Cabeçalhos de resposta** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="c2fa5-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c2fa5-125">**Corpo da resposta** -abaixo está uma estrutura de exemplo das entradas do log.</span><span class="sxs-lookup"><span data-stu-id="c2fa5-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


