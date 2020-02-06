---
title: Obter item
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
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Resumo: Saiba mais sobre a operação de obtenção de itens, que faz parte do serviço de item. O serviço de item faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 295276e6f3b0f577dae9a43c4c0f62e23b8582f4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816790"
---
# <a name="get-item"></a><span data-ttu-id="59801-105">Obter item</span><span class="sxs-lookup"><span data-stu-id="59801-105">Get Item</span></span>
 
<span data-ttu-id="59801-106">**Resumo:** Saiba mais sobre a operação obter item, que faz parte do serviço de item.</span><span class="sxs-lookup"><span data-stu-id="59801-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="59801-107">O serviço de item faz parte da API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="59801-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="59801-108">O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="59801-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="59801-109">A operação obter item faz parte do serviço de itens na API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="59801-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="59801-110">Obter item</span><span class="sxs-lookup"><span data-stu-id="59801-110">Get Item</span></span>

<span data-ttu-id="59801-111">Obter item retorna um item específico no repositório.</span><span class="sxs-lookup"><span data-stu-id="59801-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="59801-112">**Forma**</span><span class="sxs-lookup"><span data-stu-id="59801-112">**Method**</span></span>|<span data-ttu-id="59801-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="59801-113">**Request URI**</span></span>|<span data-ttu-id="59801-114">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="59801-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="59801-115">Obter</span><span class="sxs-lookup"><span data-stu-id="59801-115">GET</span></span>  <br/> |<span data-ttu-id="59801-116">https://\<do\>portal de/QoERepositoryService/Repository/item/{itemid}</span><span class="sxs-lookup"><span data-stu-id="59801-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="59801-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="59801-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="59801-118">**Parâmetros de URI** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="59801-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="59801-119">**Solicitar cabeçalhos** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="59801-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="59801-120">**Corpo da solicitação** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="59801-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="59801-121">**Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="59801-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="59801-122">**Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="59801-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="59801-123">Se uma ID de item especificada não for encontrada, será retornado o código de status 404 (não encontrado).</span><span class="sxs-lookup"><span data-stu-id="59801-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="59801-124">**Cabeçalhos de resposta** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="59801-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="59801-125">**Corpo da resposta** -abaixo está uma carga de resposta de exemplo em JSON.</span><span class="sxs-lookup"><span data-stu-id="59801-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="59801-126">*ItemId* -ID do item.</span><span class="sxs-lookup"><span data-stu-id="59801-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="59801-127">*userid* -ID do usuário que é proprietário deste item.</span><span class="sxs-lookup"><span data-stu-id="59801-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="59801-128">*conteúdo* -o conteúdo específico do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="59801-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="59801-129">*tipo* – o tipo do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="59801-129">*type*  - The type of the content.</span></span> <span data-ttu-id="59801-130">Este campo é definido pelos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="59801-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="59801-131">*Subitemids* – as IDs de subitens, se houver.</span><span class="sxs-lookup"><span data-stu-id="59801-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="59801-132">Trata-se de um curto circuito para obter a operação de subitens para salvar uma chamada.</span><span class="sxs-lookup"><span data-stu-id="59801-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="59801-133">Os aplicativos também podem obter as mesmas informações usando a operação obter subitens.</span><span class="sxs-lookup"><span data-stu-id="59801-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

