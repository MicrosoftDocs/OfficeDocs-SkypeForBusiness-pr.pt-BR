---
title: Obter o Item Predecessor
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
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 'Resumo: Saiba mais sobre a operação Get Item Ancestors, que faz parte do Serviço de Item. O Serviço de Item faz parte da API de Repositório para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: 59fcd10f620b32151346e8732e67ae6151a258ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832571"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="39469-105">Obter o Item Predecessor</span><span class="sxs-lookup"><span data-stu-id="39469-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="39469-106">**Resumo:** Saiba mais sobre a operação Get Item Ancestors, que faz parte do Serviço de Item.</span><span class="sxs-lookup"><span data-stu-id="39469-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="39469-107">O Serviço de Item faz parte da API de Repositório para o Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="39469-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="39469-108">O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="39469-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="39469-109">A operação Get Item Ancestors faz parte do Serviço de Item na API de Repositório para Painel de Qualidade de Chamada.</span><span class="sxs-lookup"><span data-stu-id="39469-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="39469-110">Obter o Item Predecessor</span><span class="sxs-lookup"><span data-stu-id="39469-110">Get Item Ancestors</span></span>

<span data-ttu-id="39469-111">Obter Item Ancestors retorna itens específicos ancestrais do repositório.</span><span class="sxs-lookup"><span data-stu-id="39469-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="39469-112">**Method**</span><span class="sxs-lookup"><span data-stu-id="39469-112">**Method**</span></span>|<span data-ttu-id="39469-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="39469-113">**Request URI**</span></span>|<span data-ttu-id="39469-114">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="39469-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="39469-115">OBTER</span><span class="sxs-lookup"><span data-stu-id="39469-115">GET</span></span>  <br/> |<span data-ttu-id="39469-116">https:// \<portal\> /QoERepositoryService/repository/itemAncestors/{itemId}</span><span class="sxs-lookup"><span data-stu-id="39469-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="39469-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="39469-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="39469-118">**Parâmetros de URI** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="39469-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="39469-119">**Solicitação de headers** - nenhum outro.</span><span class="sxs-lookup"><span data-stu-id="39469-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="39469-120">**Corpo da Solicitação** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="39469-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="39469-121">**Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="39469-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="39469-122">**Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="39469-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="39469-123">Se uma ID de usuário especificada não for encontrada, ela retornará o código de status 404 (Não Encontrado).</span><span class="sxs-lookup"><span data-stu-id="39469-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="39469-124">**Response Headers** - Sem outros headers.</span><span class="sxs-lookup"><span data-stu-id="39469-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="39469-125">**Corpo de** Resposta - Abaixo está um exemplo de carga de resposta em JSON.</span><span class="sxs-lookup"><span data-stu-id="39469-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
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

 <span data-ttu-id="39469-126">*Item1*  - ID do item.</span><span class="sxs-lookup"><span data-stu-id="39469-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="39469-127">*Item2*  - Profundidade é a distância do Item.</span><span class="sxs-lookup"><span data-stu-id="39469-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="39469-128">0 é o pai imediato.</span><span class="sxs-lookup"><span data-stu-id="39469-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="39469-129">*Item3*  - Título do item.</span><span class="sxs-lookup"><span data-stu-id="39469-129">*Item3*  - Title of the item.</span></span>
  

