---
title: Obter o Item Predecessor
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 'Resumo: Saiba mais sobre a operação obter ancestrais do Item, que é parte do serviço do Item. O serviço de Item é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: 7afeecb81d1933b0a308b174e49f6d8ff45a93dd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873109"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="0bb56-105">Obter o Item Predecessor</span><span class="sxs-lookup"><span data-stu-id="0bb56-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="0bb56-106">**Resumo:** Saiba mais sobre a operação obter ancestrais do Item, que é parte do serviço do Item.</span><span class="sxs-lookup"><span data-stu-id="0bb56-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="0bb56-107">O serviço de Item é parte da API do repositório para painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="0bb56-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="0bb56-108">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="0bb56-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="0bb56-109">A operação obter ancestrais do Item é parte do serviço do Item na API repositório para o painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="0bb56-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="0bb56-110">Obter o Item Predecessor</span><span class="sxs-lookup"><span data-stu-id="0bb56-110">Get Item Ancestors</span></span>

<span data-ttu-id="0bb56-111">Get Item ancestrais retorna uma ancestrais itens específicos do repositório.</span><span class="sxs-lookup"><span data-stu-id="0bb56-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="0bb56-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="0bb56-112">**Method**</span></span>|<span data-ttu-id="0bb56-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="0bb56-113">**Request URI**</span></span>|<span data-ttu-id="0bb56-114">**Versão de HTTP**</span><span class="sxs-lookup"><span data-stu-id="0bb56-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0bb56-115">Obter</span><span class="sxs-lookup"><span data-stu-id="0bb56-115">GET</span></span>  <br/> |<span data-ttu-id="0bb56-116">https://\<portal\>/QoERepositoryService/repositório/itemAncestors / {itemId}</span><span class="sxs-lookup"><span data-stu-id="0bb56-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="0bb56-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="0bb56-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="0bb56-118">**Parâmetros URI** - None.</span><span class="sxs-lookup"><span data-stu-id="0bb56-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="0bb56-119">**Cabeçalhos de solicitação** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="0bb56-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0bb56-120">O **corpo da solicitação** - None.</span><span class="sxs-lookup"><span data-stu-id="0bb56-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="0bb56-121">**Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="0bb56-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="0bb56-122">**Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).</span><span class="sxs-lookup"><span data-stu-id="0bb56-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="0bb56-123">Se um usuário especificado que ID não for encontrado, será retornado o código de status 404 (não encontrado).</span><span class="sxs-lookup"><span data-stu-id="0bb56-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="0bb56-124">**Cabeçalhos de resposta** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="0bb56-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0bb56-125">**Corpo de resposta** - abaixo é uma carga de resposta de exemplo em JSON.</span><span class="sxs-lookup"><span data-stu-id="0bb56-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
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

 <span data-ttu-id="0bb56-126">*Item1* - ID do item.</span><span class="sxs-lookup"><span data-stu-id="0bb56-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="0bb56-127">*Item2* - profundidade é a distância do Item.</span><span class="sxs-lookup"><span data-stu-id="0bb56-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="0bb56-128">0 é o pai imediato.</span><span class="sxs-lookup"><span data-stu-id="0bb56-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="0bb56-129">*Item3* - título do item.</span><span class="sxs-lookup"><span data-stu-id="0bb56-129">*Item3*  - Title of the item.</span></span>
  

