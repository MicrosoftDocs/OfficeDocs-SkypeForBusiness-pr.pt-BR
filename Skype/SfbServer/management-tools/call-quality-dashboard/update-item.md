---
title: Atualizar Item
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/8/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Resumo: Saiba sobre a operação de atualização de Item, que é parte do serviço do Item. O serviço de Item é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.'
ms.openlocfilehash: 0616f41a3ae680412bdc435716d805af77e72f3a
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295263"
---
# <a name="update-item"></a><span data-ttu-id="2c579-105">Atualizar Item</span><span class="sxs-lookup"><span data-stu-id="2c579-105">Update Item</span></span>
 
<span data-ttu-id="2c579-106">**Resumo:** Saiba mais sobre a operação de atualização de Item, que é parte do serviço do Item.</span><span class="sxs-lookup"><span data-stu-id="2c579-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="2c579-107">O serviço de Item é parte da API do repositório para painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="2c579-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="2c579-108">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2c579-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="2c579-109">A operação de atualização de Item é parte do serviço do Item na API repositório para o painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="2c579-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="2c579-110">Atualizar Item</span><span class="sxs-lookup"><span data-stu-id="2c579-110">Update Item</span></span>

<span data-ttu-id="2c579-111">Atualizar Item atualiza um item específico no repositório.</span><span class="sxs-lookup"><span data-stu-id="2c579-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="2c579-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="2c579-112">**Method**</span></span>|<span data-ttu-id="2c579-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="2c579-113">**Request URI**</span></span>|<span data-ttu-id="2c579-114">**Versão de HTTP**</span><span class="sxs-lookup"><span data-stu-id="2c579-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2c579-115">PUT</span><span class="sxs-lookup"><span data-stu-id="2c579-115">PUT</span></span>  <br/> |<span data-ttu-id="2c579-116">https://\<portal\>/QoERepositoryService/repositório/item / {itemId}</span><span class="sxs-lookup"><span data-stu-id="2c579-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="2c579-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="2c579-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="2c579-118">**Parâmetros URI** - None.</span><span class="sxs-lookup"><span data-stu-id="2c579-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="2c579-119">**Cabeçalhos de solicitação** -conteúdo-tipo: application/json.</span><span class="sxs-lookup"><span data-stu-id="2c579-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="2c579-120">**Corpo da solicitação** - JSON.</span><span class="sxs-lookup"><span data-stu-id="2c579-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="2c579-121">Carga de solicitação de exemplo:</span><span class="sxs-lookup"><span data-stu-id="2c579-121">Sample request payload:</span></span>
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="2c579-122">*conteúdo*  JSON formatado dados a serem armazenados como o novo conteúdo de um Item de subsites existente.</span><span class="sxs-lookup"><span data-stu-id="2c579-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="2c579-123">Tecnicamente, um repositório pode armazenar o conteúdo de qualquer esquema, mas quando usado para painel de controle de qualidade de chamada, ele deve ser um relatório ou uma consulta.</span><span class="sxs-lookup"><span data-stu-id="2c579-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="2c579-124">*tipo*  Sempre especifique "application json" para painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="2c579-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="2c579-125">**Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="2c579-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="2c579-126">**Código de status** - uma operação bem-sucedida retorna o código de status 204 (sem conteúdo).</span><span class="sxs-lookup"><span data-stu-id="2c579-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="2c579-127">Se uma ID de item especificado não for encontrada, será retornado o código de status 404 (não encontrado).</span><span class="sxs-lookup"><span data-stu-id="2c579-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2c579-128">"Nenhum conteúdo" não é um status de erro.</span><span class="sxs-lookup"><span data-stu-id="2c579-128">"No Content" is not an error status.</span></span> <span data-ttu-id="2c579-129">Isso significa que uma resposta não retornou nada no corpo (em contraste, conteúdo de 200 retorna Okey no corpo).</span><span class="sxs-lookup"><span data-stu-id="2c579-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="2c579-130">Indica que o Item foi atualizado com êxito.</span><span class="sxs-lookup"><span data-stu-id="2c579-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="2c579-131">**Cabeçalhos de resposta** - None.</span><span class="sxs-lookup"><span data-stu-id="2c579-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="2c579-132">**Corpo de resposta** - None.</span><span class="sxs-lookup"><span data-stu-id="2c579-132">**Response Body** - None.</span></span>
  

