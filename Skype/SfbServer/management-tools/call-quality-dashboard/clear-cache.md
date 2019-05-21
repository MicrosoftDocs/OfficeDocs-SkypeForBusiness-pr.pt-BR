---
title: Limpar Cache
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Resumo: Saiba mais sobre a operação de limpeza de cache, que faz parte da API de dados para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 38648e1a910f93a30bd6da8807321acad0330e62
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274832"
---
# <a name="clear-cache"></a><span data-ttu-id="54d83-104">Limpar Cache</span><span class="sxs-lookup"><span data-stu-id="54d83-104">Clear Cache</span></span>
 
<span data-ttu-id="54d83-105">**Resumo:** Saiba mais sobre a operação de limpeza de cache, que faz parte da API de dados para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="54d83-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="54d83-106">O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="54d83-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="54d83-107">A operação de cache limpar faz parte da API de dados para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="54d83-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="54d83-108">Limpar Cache</span><span class="sxs-lookup"><span data-stu-id="54d83-108">Clear Cache</span></span>

<span data-ttu-id="54d83-109">Limpar operação de cache exclui o cache no servidor para consultas e dados.</span><span class="sxs-lookup"><span data-stu-id="54d83-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="54d83-110">Isso redefinirá o cache e obteremos dados atualizados do cubo de QoE posteriormente para novas solicitações.</span><span class="sxs-lookup"><span data-stu-id="54d83-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="54d83-111">**Forma**</span><span class="sxs-lookup"><span data-stu-id="54d83-111">**Method**</span></span>|<span data-ttu-id="54d83-112">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="54d83-112">**Request URI**</span></span>|<span data-ttu-id="54d83-113">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="54d83-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="54d83-114">Postar</span><span class="sxs-lookup"><span data-stu-id="54d83-114">POST</span></span>  <br/> |<span data-ttu-id="54d83-115">https://\<do\>portal de/QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="54d83-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="54d83-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="54d83-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="54d83-117">**Parâmetros de URI** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="54d83-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="54d83-118">**Solicitar cabeçalhos** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="54d83-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="54d83-119">**Corpo da solicitação** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="54d83-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="54d83-120">**Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="54d83-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="54d83-121">**Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="54d83-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="54d83-122">**Cabeçalhos de resposta** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="54d83-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="54d83-123">**Corpo da resposta** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="54d83-123">**Response Body** - None.</span></span>
  

