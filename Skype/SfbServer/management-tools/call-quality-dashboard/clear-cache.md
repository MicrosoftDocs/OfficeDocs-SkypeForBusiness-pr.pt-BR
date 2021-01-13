---
title: Limpar Cache
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
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Resumo: saiba mais sobre a operação Limpar Cache, que faz parte da API de Dados do Painel de Qualidade de Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: c9b966bb1e35a5a6255cd75ea6c685daaf220a09
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806411"
---
# <a name="clear-cache"></a><span data-ttu-id="ae90f-104">Limpar Cache</span><span class="sxs-lookup"><span data-stu-id="ae90f-104">Clear Cache</span></span>
 
<span data-ttu-id="ae90f-105">**Resumo:** Saiba mais sobre a operação Limpar Cache, que faz parte da API de Dados do Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="ae90f-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="ae90f-106">O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ae90f-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="ae90f-107">A operação Limpar Cache faz parte da API de Dados do Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="ae90f-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="ae90f-108">Limpar Cache</span><span class="sxs-lookup"><span data-stu-id="ae90f-108">Clear Cache</span></span>

<span data-ttu-id="ae90f-109">A operação Limpar Cache exclui o cache no servidor para consultas e dados.</span><span class="sxs-lookup"><span data-stu-id="ae90f-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="ae90f-110">Isso redefini o cache e obteremos dados atualizados do Cubo QoE posteriormente para novas solicitações.</span><span class="sxs-lookup"><span data-stu-id="ae90f-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="ae90f-111">**Method**</span><span class="sxs-lookup"><span data-stu-id="ae90f-111">**Method**</span></span>|<span data-ttu-id="ae90f-112">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="ae90f-112">**Request URI**</span></span>|<span data-ttu-id="ae90f-113">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="ae90f-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ae90f-114">POSTAR</span><span class="sxs-lookup"><span data-stu-id="ae90f-114">POST</span></span>  <br/> |<span data-ttu-id="ae90f-115">https:// \<portal\> /QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="ae90f-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="ae90f-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="ae90f-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="ae90f-117">**Parâmetros de URI** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="ae90f-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="ae90f-118">**Solicitação de headers** - nenhum outro.</span><span class="sxs-lookup"><span data-stu-id="ae90f-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="ae90f-119">**Corpo da Solicitação** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="ae90f-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="ae90f-120">**Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="ae90f-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="ae90f-121">**Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="ae90f-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="ae90f-122">**Response Headers** - Sem outros headers.</span><span class="sxs-lookup"><span data-stu-id="ae90f-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="ae90f-123">**Corpo de Resposta** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="ae90f-123">**Response Body** - None.</span></span>
  

