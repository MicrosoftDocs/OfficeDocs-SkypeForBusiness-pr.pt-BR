---
title: Obter subitens
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
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Resumo: Saiba mais sobre a operação obter subitens, que faz parte do serviço de item. O serviço de item faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 523a6050065680550685337dabfec72c87f30bf7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816760"
---
# <a name="get-sub-items"></a><span data-ttu-id="3f428-105">Obter subitens</span><span class="sxs-lookup"><span data-stu-id="3f428-105">Get Sub-Items</span></span>
 
<span data-ttu-id="3f428-106">**Resumo:** Saiba mais sobre a operação obter subitens, que faz parte do serviço de item.</span><span class="sxs-lookup"><span data-stu-id="3f428-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="3f428-107">O serviço de item faz parte da API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="3f428-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="3f428-108">O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3f428-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="3f428-109">A operação obter subitens é parte do serviço de item na API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="3f428-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="3f428-110">Obter subitens</span><span class="sxs-lookup"><span data-stu-id="3f428-110">Get Sub-Items</span></span>

<span data-ttu-id="3f428-111">Obter subitens retorna os subitens de um item específico.</span><span class="sxs-lookup"><span data-stu-id="3f428-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="3f428-112">**Forma**</span><span class="sxs-lookup"><span data-stu-id="3f428-112">**Method**</span></span>|<span data-ttu-id="3f428-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="3f428-113">**Request URI**</span></span>|<span data-ttu-id="3f428-114">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="3f428-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3f428-115">Obter</span><span class="sxs-lookup"><span data-stu-id="3f428-115">GET</span></span>  <br/> |<span data-ttu-id="3f428-116">https://\<do\>portal de/QoERepositoryService/Repository/item/{itemid}/subitem</span><span class="sxs-lookup"><span data-stu-id="3f428-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="3f428-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="3f428-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="3f428-118">**Parâmetros de URI** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="3f428-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="3f428-119">**Solicitar cabeçalhos** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="3f428-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="3f428-120">**Corpo da solicitação** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="3f428-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="3f428-121">**Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="3f428-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="3f428-122">**Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="3f428-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="3f428-123">Se um ID de usuário especificado não for encontrado, ele retornará o código de status 404 (não encontrado).</span><span class="sxs-lookup"><span data-stu-id="3f428-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="3f428-124">**Cabeçalhos de resposta** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="3f428-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="3f428-125">**Corpo da resposta** -abaixo está uma carga de resposta de exemplo em JSON.</span><span class="sxs-lookup"><span data-stu-id="3f428-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3f428-126">Uma matriz de objeto de item é retornada.</span><span class="sxs-lookup"><span data-stu-id="3f428-126">An array of Item object is returned.</span></span> 
  
```json
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

<span data-ttu-id="3f428-127">O objeto de item retornado pela operação de subitens contém somente os três campos a seguir.</span><span class="sxs-lookup"><span data-stu-id="3f428-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="3f428-128">*ItemId* -ID do item.</span><span class="sxs-lookup"><span data-stu-id="3f428-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="3f428-129">*userid* -ID do usuário que é proprietário deste item.</span><span class="sxs-lookup"><span data-stu-id="3f428-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="3f428-130">*tipo* – o tipo do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="3f428-130">*type*  - The type of the content.</span></span> <span data-ttu-id="3f428-131">Este campo é definido pelos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="3f428-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="3f428-132">`Content`os `subItems` campos não são incluídos na resposta para reduzir a quantidade de dados transmitidos pela rede.</span><span class="sxs-lookup"><span data-stu-id="3f428-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

