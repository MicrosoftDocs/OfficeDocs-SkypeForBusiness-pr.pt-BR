---
title: Limpar Cache
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Resumo: Saiba mais sobre a operação Clear Cache, que é parte da API de dados para o painel de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: 918709d87545289e46c6bef49aafb0f1d37b2950
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930802"
---
# <a name="clear-cache"></a><span data-ttu-id="0c985-104">Limpar Cache</span><span class="sxs-lookup"><span data-stu-id="0c985-104">Clear Cache</span></span>
 
<span data-ttu-id="0c985-105">**Resumo:** Saiba mais sobre a operação Clear Cache, que é parte da API de dados para o painel de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="0c985-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="0c985-106">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="0c985-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="0c985-107">A operação de Clear Cache é parte da API de dados para o painel de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="0c985-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="0c985-108">Limpar Cache</span><span class="sxs-lookup"><span data-stu-id="0c985-108">Clear Cache</span></span>

<span data-ttu-id="0c985-109">Operação de Clear Cache exclui o cache no servidor para consultas e dados.</span><span class="sxs-lookup"><span data-stu-id="0c985-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="0c985-110">Isso redefinirá o cache e abordaremos dados atualizados do cubo de QoE posteriormente para novas solicitações.</span><span class="sxs-lookup"><span data-stu-id="0c985-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="0c985-111">**Método**</span><span class="sxs-lookup"><span data-stu-id="0c985-111">**Method**</span></span>|<span data-ttu-id="0c985-112">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="0c985-112">**Request URI**</span></span>|<span data-ttu-id="0c985-113">**Versão de HTTP**</span><span class="sxs-lookup"><span data-stu-id="0c985-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0c985-114">Postar</span><span class="sxs-lookup"><span data-stu-id="0c985-114">POST</span></span>  <br/> |<span data-ttu-id="0c985-115">https://\<portal\>/QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="0c985-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="0c985-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="0c985-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="0c985-117">**Parâmetros URI** - None.</span><span class="sxs-lookup"><span data-stu-id="0c985-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="0c985-118">**Cabeçalhos de solicitação** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="0c985-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0c985-119">O **corpo da solicitação** - None.</span><span class="sxs-lookup"><span data-stu-id="0c985-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="0c985-120">**Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="0c985-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="0c985-121">**Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).</span><span class="sxs-lookup"><span data-stu-id="0c985-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="0c985-122">**Cabeçalhos de resposta** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="0c985-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0c985-123">**Corpo de resposta** - None.</span><span class="sxs-lookup"><span data-stu-id="0c985-123">**Response Body** - None.</span></span>
  

