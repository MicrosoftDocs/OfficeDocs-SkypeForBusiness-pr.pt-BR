---
title: Obter itens
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 'Resumo: Saiba mais sobre a operação obter itens, que é parte do serviço do Item. O serviço de Item é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: ad4be2c09de9d71499cd7592989334ccf4cf17c9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32235727"
---
# <a name="get-items"></a><span data-ttu-id="7a8b3-105">Obter itens</span><span class="sxs-lookup"><span data-stu-id="7a8b3-105">Get Items</span></span>
 
<span data-ttu-id="7a8b3-106">**Resumo:** Saiba mais sobre a operação obter itens, que é parte do serviço do Item.</span><span class="sxs-lookup"><span data-stu-id="7a8b3-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="7a8b3-107">O serviço de Item é parte da API do repositório para painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="7a8b3-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="7a8b3-108">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="7a8b3-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="7a8b3-109">A operação obter itens é parte do serviço do Item na API repositório para o painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="7a8b3-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="7a8b3-110">Obter itens</span><span class="sxs-lookup"><span data-stu-id="7a8b3-110">Get Items</span></span>

<span data-ttu-id="7a8b3-111">Obter itens retorna todos os itens no repositório.</span><span class="sxs-lookup"><span data-stu-id="7a8b3-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="7a8b3-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="7a8b3-112">**Method**</span></span>|<span data-ttu-id="7a8b3-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="7a8b3-113">**Request URI**</span></span>|<span data-ttu-id="7a8b3-114">**Versão de HTTP**</span><span class="sxs-lookup"><span data-stu-id="7a8b3-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7a8b3-115">Obter</span><span class="sxs-lookup"><span data-stu-id="7a8b3-115">GET</span></span>  <br/> |<span data-ttu-id="7a8b3-116">https://\<portal\>/QoERepositoryService/repository/item</span><span class="sxs-lookup"><span data-stu-id="7a8b3-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="7a8b3-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="7a8b3-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="7a8b3-118">**Parâmetros URI** - None.</span><span class="sxs-lookup"><span data-stu-id="7a8b3-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="7a8b3-119">**Cabeçalhos de solicitação** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="7a8b3-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7a8b3-120">O **corpo da solicitação** - None.</span><span class="sxs-lookup"><span data-stu-id="7a8b3-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="7a8b3-121">**Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="7a8b3-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="7a8b3-122">**Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).</span><span class="sxs-lookup"><span data-stu-id="7a8b3-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="7a8b3-123">**Cabeçalhos de resposta** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="7a8b3-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7a8b3-124">**Corpo de resposta** - abaixo é uma carga de resposta de exemplo em JSON.</span><span class="sxs-lookup"><span data-stu-id="7a8b3-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7a8b3-125">Uma matriz de objetos do Item será retornada.</span><span class="sxs-lookup"><span data-stu-id="7a8b3-125">An array of Item objects is returned.</span></span> <span data-ttu-id="7a8b3-126">Para obter detalhes sobre o objeto de Item, consulte obter Item.</span><span class="sxs-lookup"><span data-stu-id="7a8b3-126">For details about Item object, see Get Item.</span></span> 
  
```
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
