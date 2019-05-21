---
title: Obter o Item Predecessor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 'Resumo: Saiba mais sobre a operação obter item ancestrais, que faz parte do serviço de item. O serviço de item faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 77fb5f46ada278bcb172a51620317182fe5d61b0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274727"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="29e6b-105">Obter o Item Predecessor</span><span class="sxs-lookup"><span data-stu-id="29e6b-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="29e6b-106">**Resumo:** Saiba mais sobre a operação obter item ancestrais, que faz parte do serviço de item.</span><span class="sxs-lookup"><span data-stu-id="29e6b-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="29e6b-107">O serviço de item faz parte da API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="29e6b-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="29e6b-108">O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="29e6b-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="29e6b-109">A operação obter item ancestrais faz parte do serviço de item na API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="29e6b-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="29e6b-110">Obter o Item Predecessor</span><span class="sxs-lookup"><span data-stu-id="29e6b-110">Get Item Ancestors</span></span>

<span data-ttu-id="29e6b-111">Obter item ancestrais retorna um ancestral de itens específicos do repositório.</span><span class="sxs-lookup"><span data-stu-id="29e6b-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="29e6b-112">**Forma**</span><span class="sxs-lookup"><span data-stu-id="29e6b-112">**Method**</span></span>|<span data-ttu-id="29e6b-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="29e6b-113">**Request URI**</span></span>|<span data-ttu-id="29e6b-114">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="29e6b-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="29e6b-115">Obter</span><span class="sxs-lookup"><span data-stu-id="29e6b-115">GET</span></span>  <br/> |<span data-ttu-id="29e6b-116">https://\<do\>portal de/QoERepositoryService/Repository/itemAncestors/{ItemId}</span><span class="sxs-lookup"><span data-stu-id="29e6b-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="29e6b-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="29e6b-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="29e6b-118">**Parâmetros de URI** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="29e6b-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="29e6b-119">**Solicitar cabeçalhos** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="29e6b-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="29e6b-120">**Corpo da solicitação** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="29e6b-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="29e6b-121">**Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="29e6b-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="29e6b-122">**Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="29e6b-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="29e6b-123">Se um ID de usuário especificado não for encontrado, ele retornará o código de status 404 (não encontrado).</span><span class="sxs-lookup"><span data-stu-id="29e6b-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="29e6b-124">**Cabeçalhos de resposta** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="29e6b-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="29e6b-125">**Corpo da resposta** -abaixo está uma carga de resposta de exemplo em JSON.</span><span class="sxs-lookup"><span data-stu-id="29e6b-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
[{
"item1": 1653,
"item2": 0,
"item3": "Audio Streams Monthly Trend"
},
{
"item1": 1652,
"item2": 1,
"item3": "All Audio Streams"
}]
```

 <span data-ttu-id="29e6b-126">*Item1* -ID do item.</span><span class="sxs-lookup"><span data-stu-id="29e6b-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="29e6b-127">*Item2* -Depth é a distância do item.</span><span class="sxs-lookup"><span data-stu-id="29e6b-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="29e6b-128">0 é o pai imediato.</span><span class="sxs-lookup"><span data-stu-id="29e6b-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="29e6b-129">*Item3* -título do item.</span><span class="sxs-lookup"><span data-stu-id="29e6b-129">*Item3*  - Title of the item.</span></span>
  

