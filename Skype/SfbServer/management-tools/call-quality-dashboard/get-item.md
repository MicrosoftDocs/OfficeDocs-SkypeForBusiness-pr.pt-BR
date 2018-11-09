---
title: Obtenha Item
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Resumo: Saiba mais sobre a operação obter Item, que é parte do serviço do Item. O serviço de Item é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: 12b52bdd51e8ba59f1aa90e2a366b3e11fb54805
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035572"
---
# <a name="get-item"></a><span data-ttu-id="c3875-105">Obtenha Item</span><span class="sxs-lookup"><span data-stu-id="c3875-105">Get Item</span></span>
 
<span data-ttu-id="c3875-106">**Resumo:** Saiba mais sobre a operação obter Item, que é parte do serviço do Item.</span><span class="sxs-lookup"><span data-stu-id="c3875-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="c3875-107">O serviço de Item é parte da API do repositório para painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="c3875-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="c3875-108">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="c3875-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="c3875-109">A operação obter Item é parte do serviço do Item na API repositório para o painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="c3875-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="c3875-110">Obtenha Item</span><span class="sxs-lookup"><span data-stu-id="c3875-110">Get Item</span></span>

<span data-ttu-id="c3875-111">Obtenha o Item Retorna um item específico no repositório.</span><span class="sxs-lookup"><span data-stu-id="c3875-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="c3875-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="c3875-112">**Method**</span></span>|<span data-ttu-id="c3875-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="c3875-113">**Request URI**</span></span>|<span data-ttu-id="c3875-114">**Versão de HTTP**</span><span class="sxs-lookup"><span data-stu-id="c3875-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c3875-115">Obter</span><span class="sxs-lookup"><span data-stu-id="c3875-115">GET</span></span>  <br/> |<span data-ttu-id="c3875-116">https://\<portal\>/QoERepositoryService/repositório/item / {itemId}</span><span class="sxs-lookup"><span data-stu-id="c3875-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="c3875-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="c3875-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="c3875-118">**Parâmetros URI** - None.</span><span class="sxs-lookup"><span data-stu-id="c3875-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="c3875-119">**Cabeçalhos de solicitação** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="c3875-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c3875-120">O **corpo da solicitação** - None.</span><span class="sxs-lookup"><span data-stu-id="c3875-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="c3875-121">**Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="c3875-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="c3875-122">**Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).</span><span class="sxs-lookup"><span data-stu-id="c3875-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="c3875-123">Se uma ID de item especificado não for encontrada, será retornado o código de status 404 (não encontrado).</span><span class="sxs-lookup"><span data-stu-id="c3875-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="c3875-124">**Cabeçalhos de resposta** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="c3875-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c3875-125">**Corpo de resposta** - abaixo é uma carga de resposta de exemplo em JSON.</span><span class="sxs-lookup"><span data-stu-id="c3875-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="c3875-126">*itemId* - ID do item.</span><span class="sxs-lookup"><span data-stu-id="c3875-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="c3875-127">*userId* - ID do usuário que possui esse item.</span><span class="sxs-lookup"><span data-stu-id="c3875-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="c3875-128">*conteúdo* – o conteúdo de aplicativo específico.</span><span class="sxs-lookup"><span data-stu-id="c3875-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="c3875-129">*tipo* - o tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="c3875-129">*type*  - The type of the content.</span></span> <span data-ttu-id="c3875-130">Este campo é definido pelos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="c3875-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="c3875-131">*subItemIds* - as identificações de subitens, se houver alguma.</span><span class="sxs-lookup"><span data-stu-id="c3875-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="c3875-132">Este é um short-circuit da operação Get sub-recurso Items para salvar uma chamada.</span><span class="sxs-lookup"><span data-stu-id="c3875-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="c3875-133">Aplicativos podem se desejar obter as mesmas informações usando a operação obter itens subsites.</span><span class="sxs-lookup"><span data-stu-id="c3875-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

