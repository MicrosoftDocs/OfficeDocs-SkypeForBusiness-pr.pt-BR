---
title: Obter itens sub-recurso
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Resumo: Saiba mais sobre a operação obter itens sub, que é parte do serviço do Item. O serviço de Item é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: 648f514ff03361673962052445d25076437057b9
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035649"
---
# <a name="get-sub-items"></a><span data-ttu-id="59cd7-105">Obter itens sub-recurso</span><span class="sxs-lookup"><span data-stu-id="59cd7-105">Get Sub-Items</span></span>
 
<span data-ttu-id="59cd7-106">**Resumo:** Saiba mais sobre a operação obter itens sub, que é parte do serviço do Item.</span><span class="sxs-lookup"><span data-stu-id="59cd7-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="59cd7-107">O serviço de Item é parte da API do repositório para painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="59cd7-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="59cd7-108">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="59cd7-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="59cd7-109">A operação obter itens sub-recurso é parte do serviço do Item na API repositório para o painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="59cd7-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="59cd7-110">Obter itens sub-recurso</span><span class="sxs-lookup"><span data-stu-id="59cd7-110">Get Sub-Items</span></span>

<span data-ttu-id="59cd7-111">Obter itens sub-recurso retorna subitens de um Item específico.</span><span class="sxs-lookup"><span data-stu-id="59cd7-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="59cd7-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="59cd7-112">**Method**</span></span>|<span data-ttu-id="59cd7-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="59cd7-113">**Request URI**</span></span>|<span data-ttu-id="59cd7-114">**Versão de HTTP**</span><span class="sxs-lookup"><span data-stu-id="59cd7-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="59cd7-115">Obter</span><span class="sxs-lookup"><span data-stu-id="59cd7-115">GET</span></span>  <br/> |<span data-ttu-id="59cd7-116">https://\<portal\>/QoERepositoryService/repositório/item / {itemId} / subitem</span><span class="sxs-lookup"><span data-stu-id="59cd7-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="59cd7-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="59cd7-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="59cd7-118">**Parâmetros URI** - None.</span><span class="sxs-lookup"><span data-stu-id="59cd7-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="59cd7-119">**Cabeçalhos de solicitação** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="59cd7-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="59cd7-120">O **corpo da solicitação** - None.</span><span class="sxs-lookup"><span data-stu-id="59cd7-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="59cd7-121">**Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="59cd7-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="59cd7-122">**Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).</span><span class="sxs-lookup"><span data-stu-id="59cd7-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="59cd7-123">Se um usuário especificado que ID não for encontrado, será retornado o código de status 404 (não encontrado).</span><span class="sxs-lookup"><span data-stu-id="59cd7-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="59cd7-124">**Cabeçalhos de resposta** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="59cd7-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="59cd7-125">**Corpo de resposta** - abaixo é uma carga de resposta de exemplo em JSON.</span><span class="sxs-lookup"><span data-stu-id="59cd7-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="59cd7-126">Uma matriz de objeto de Item será retornada.</span><span class="sxs-lookup"><span data-stu-id="59cd7-126">An array of Item object is returned.</span></span> 
  
```
[{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1710,
"userId": 0,
"type": "json"
}]
```

<span data-ttu-id="59cd7-127">O objeto de Item retornado pela operação de subitens contém apenas os seguintes três campos.</span><span class="sxs-lookup"><span data-stu-id="59cd7-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="59cd7-128">*itemId* - ID do item.</span><span class="sxs-lookup"><span data-stu-id="59cd7-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="59cd7-129">*userId* - ID do usuário que possui esse Item.</span><span class="sxs-lookup"><span data-stu-id="59cd7-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="59cd7-130">*tipo* - o tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="59cd7-130">*type*  - The type of the content.</span></span> <span data-ttu-id="59cd7-131">Este campo é definido pelos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="59cd7-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="59cd7-132">`Content`e `subItems` campos não estão incluídos na resposta para reduzir a quantidade de dados transmitidos na rede.</span><span class="sxs-lookup"><span data-stu-id="59cd7-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

