---
title: Obter itens
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
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 'Resumo: Saiba mais sobre a operação obter itens, que faz parte do serviço de item. O serviço de item faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 6345201fe3843e3fe8cf6671f01d2db30fb4e22e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816780"
---
# <a name="get-items"></a><span data-ttu-id="79a44-105">Obter itens</span><span class="sxs-lookup"><span data-stu-id="79a44-105">Get Items</span></span>
 
<span data-ttu-id="79a44-106">**Resumo:** Saiba mais sobre a operação obter itens, que faz parte do serviço de item.</span><span class="sxs-lookup"><span data-stu-id="79a44-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="79a44-107">O serviço de item faz parte da API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="79a44-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="79a44-108">O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="79a44-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="79a44-109">A operação obter itens faz parte do serviço de itens na API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="79a44-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="79a44-110">Obter itens</span><span class="sxs-lookup"><span data-stu-id="79a44-110">Get Items</span></span>

<span data-ttu-id="79a44-111">Obter itens retorna todos os itens no repositório.</span><span class="sxs-lookup"><span data-stu-id="79a44-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="79a44-112">**Forma**</span><span class="sxs-lookup"><span data-stu-id="79a44-112">**Method**</span></span>|<span data-ttu-id="79a44-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="79a44-113">**Request URI**</span></span>|<span data-ttu-id="79a44-114">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="79a44-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="79a44-115">Obter</span><span class="sxs-lookup"><span data-stu-id="79a44-115">GET</span></span>  <br/> |<span data-ttu-id="79a44-116">https://\<do\>portal de/QoERepositoryService/Repository/item</span><span class="sxs-lookup"><span data-stu-id="79a44-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="79a44-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="79a44-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="79a44-118">**Parâmetros de URI** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="79a44-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="79a44-119">**Solicitar cabeçalhos** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="79a44-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="79a44-120">**Corpo da solicitação** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="79a44-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="79a44-121">**Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="79a44-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="79a44-122">**Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="79a44-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="79a44-123">**Cabeçalhos de resposta** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="79a44-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="79a44-124">**Corpo da resposta** -abaixo está uma carga de resposta de exemplo em JSON.</span><span class="sxs-lookup"><span data-stu-id="79a44-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="79a44-125">Uma matriz de objetos de item é retornada.</span><span class="sxs-lookup"><span data-stu-id="79a44-125">An array of Item objects is returned.</span></span> <span data-ttu-id="79a44-126">Para obter detalhes sobre o objeto de item, consulte obter item.</span><span class="sxs-lookup"><span data-stu-id="79a44-126">For details about Item object, see Get Item.</span></span> 
  
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
