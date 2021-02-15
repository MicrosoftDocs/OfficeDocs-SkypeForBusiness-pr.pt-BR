---
title: Obter o Log de integração
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
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Resumo: saiba mais sobre a operação Obter Log de Integração, que faz parte da API de Dados do Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: 69827fa9f3fd3f56843a41867b029a071799ba66
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832591"
---
# <a name="get-integration-log"></a><span data-ttu-id="7849a-104">Obter o Log de integração</span><span class="sxs-lookup"><span data-stu-id="7849a-104">Get Integration Log</span></span>
 
<span data-ttu-id="7849a-105">**Resumo:** Saiba mais sobre a operação Obter Log de Integração, que faz parte da API de Dados do Painel de Qualidade de Chamada.</span><span class="sxs-lookup"><span data-stu-id="7849a-105">**Summary:** Learn about the Get Integration Log operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="7849a-106">O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7849a-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="7849a-107">A operação Obter Log de Integração faz parte da API de Dados do Painel de Qualidade da Chamada</span><span class="sxs-lookup"><span data-stu-id="7849a-107">The Get Integration Log operation is part of the Data API for Call Quality Dashboard</span></span>
  
## <a name="get-integration-log"></a><span data-ttu-id="7849a-108">Obter o Log de integração</span><span class="sxs-lookup"><span data-stu-id="7849a-108">Get Integration Log</span></span>

<span data-ttu-id="7849a-109">A operação Obter Log de Integração retorna uma lista de entradas de log que descrevem as atividades no processamento do cubo de QoE.</span><span class="sxs-lookup"><span data-stu-id="7849a-109">Get Integration Log operation returns a list of log entries describing the activities in QoE Cube processing.</span></span>
  
<span data-ttu-id="7849a-110">Essa operação está desabilitada por padrão por motivos de segurança.</span><span class="sxs-lookup"><span data-stu-id="7849a-110">This operation is disabled by default for security reasons.</span></span> <span data-ttu-id="7849a-111">Quando desabilitado, retorna uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="7849a-111">When disabled, it returns an empty string.</span></span> <span data-ttu-id="7849a-112">Para habilitar essa operação, os administradores precisam configurar o web.config para o aplicativo Web host da API de Dados.</span><span class="sxs-lookup"><span data-stu-id="7849a-112">To enable this operation, administrators need to configure the web.config for Data API's host web application.</span></span>
  

|<span data-ttu-id="7849a-113">Método</span><span class="sxs-lookup"><span data-stu-id="7849a-113">Method</span></span>|<span data-ttu-id="7849a-114">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="7849a-114">**Request URI**</span></span>|<span data-ttu-id="7849a-115">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="7849a-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7849a-116">OBTER</span><span class="sxs-lookup"><span data-stu-id="7849a-116">GET</span></span>  <br/> |<span data-ttu-id="7849a-117">https:// \<portal\> /QoEDataService/IntegrationLog</span><span class="sxs-lookup"><span data-stu-id="7849a-117">https://\<portal\>/QoEDataService/IntegrationLog</span></span>  <br/> |<span data-ttu-id="7849a-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="7849a-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="7849a-119">**Parâmetros de URI** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="7849a-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="7849a-120">**Solicitação de headers** - nenhum outro.</span><span class="sxs-lookup"><span data-stu-id="7849a-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7849a-121">**Corpo da Solicitação** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="7849a-121">**Request Body** - None.</span></span>
  
 <span data-ttu-id="7849a-122">**Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="7849a-122">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="7849a-123">**Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="7849a-123">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="7849a-124">**Response Headers** - Sem outros headers.</span><span class="sxs-lookup"><span data-stu-id="7849a-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7849a-125">**Corpo de** Resposta - Abaixo está uma estrutura de exemplo de entradas de log.</span><span class="sxs-lookup"><span data-stu-id="7849a-125">**Response Body** - Below is a sample structure of log entries.</span></span>
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


