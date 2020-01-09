---
title: Obter itens
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 'Resumo: Saiba mais sobre a operação obter itens, que faz parte do serviço de item. O serviço de item faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: be93e16750c1a977a6bc3cfc9651e78a043ef563
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992658"
---
# <a name="get-items"></a><span data-ttu-id="a67bb-105">Obter itens</span><span class="sxs-lookup"><span data-stu-id="a67bb-105">Get Items</span></span>
 
<span data-ttu-id="a67bb-106">**Resumo:** Saiba mais sobre a operação obter itens, que faz parte do serviço de item.</span><span class="sxs-lookup"><span data-stu-id="a67bb-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="a67bb-107">O serviço de item faz parte da API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="a67bb-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="a67bb-108">O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a67bb-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="a67bb-109">A operação obter itens faz parte do serviço de itens na API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="a67bb-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="a67bb-110">Obter itens</span><span class="sxs-lookup"><span data-stu-id="a67bb-110">Get Items</span></span>

<span data-ttu-id="a67bb-111">Obter itens retorna todos os itens no repositório.</span><span class="sxs-lookup"><span data-stu-id="a67bb-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="a67bb-112">**Forma**</span><span class="sxs-lookup"><span data-stu-id="a67bb-112">**Method**</span></span>|<span data-ttu-id="a67bb-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="a67bb-113">**Request URI**</span></span>|<span data-ttu-id="a67bb-114">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="a67bb-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a67bb-115">Obter</span><span class="sxs-lookup"><span data-stu-id="a67bb-115">GET</span></span>  <br/> |<span data-ttu-id="a67bb-116">https://\<do\>portal de/QoERepositoryService/Repository/item</span><span class="sxs-lookup"><span data-stu-id="a67bb-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="a67bb-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="a67bb-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="a67bb-118">**Parâmetros de URI** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="a67bb-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="a67bb-119">**Solicitar cabeçalhos** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="a67bb-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a67bb-120">**Corpo da solicitação** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="a67bb-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="a67bb-121">**Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="a67bb-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="a67bb-122">**Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="a67bb-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="a67bb-123">**Cabeçalhos de resposta** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="a67bb-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a67bb-124">**Corpo da resposta** -abaixo está uma carga de resposta de exemplo em JSON.</span><span class="sxs-lookup"><span data-stu-id="a67bb-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a67bb-125">Uma matriz de objetos de item é retornada.</span><span class="sxs-lookup"><span data-stu-id="a67bb-125">An array of Item objects is returned.</span></span> <span data-ttu-id="a67bb-126">Para obter detalhes sobre o objeto de item, consulte obter item.</span><span class="sxs-lookup"><span data-stu-id="a67bb-126">For details about Item object, see Get Item.</span></span> 
  
```json
[{
"itemId": 1652,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1654,
"userId": 0,
"type": "application/json"
}]
```
