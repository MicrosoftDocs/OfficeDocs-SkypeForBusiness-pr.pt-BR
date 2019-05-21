---
title: Atualizar Item
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Resumo: Saiba mais sobre a operação atualizar item, que faz parte do serviço de item. O serviço de item faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: aa46be0babf5998fcf2fabea797cb7a769914f8e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274531"
---
# <a name="update-item"></a><span data-ttu-id="fd033-105">Atualizar Item</span><span class="sxs-lookup"><span data-stu-id="fd033-105">Update Item</span></span>
 
<span data-ttu-id="fd033-106">**Resumo:** Saiba mais sobre a operação atualizar item, que faz parte do serviço de item.</span><span class="sxs-lookup"><span data-stu-id="fd033-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="fd033-107">O serviço de item faz parte da API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="fd033-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="fd033-108">O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fd033-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="fd033-109">A operação atualizar item faz parte do serviço de itens na API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="fd033-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="fd033-110">Atualizar Item</span><span class="sxs-lookup"><span data-stu-id="fd033-110">Update Item</span></span>

<span data-ttu-id="fd033-111">Atualizar item atualiza um item específico no repositório.</span><span class="sxs-lookup"><span data-stu-id="fd033-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="fd033-112">**Forma**</span><span class="sxs-lookup"><span data-stu-id="fd033-112">**Method**</span></span>|<span data-ttu-id="fd033-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="fd033-113">**Request URI**</span></span>|<span data-ttu-id="fd033-114">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="fd033-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fd033-115">SUSPENDE</span><span class="sxs-lookup"><span data-stu-id="fd033-115">PUT</span></span>  <br/> |<span data-ttu-id="fd033-116">https://\<do\>portal de/QoERepositoryService/Repository/item/{itemid}</span><span class="sxs-lookup"><span data-stu-id="fd033-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="fd033-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="fd033-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="fd033-118">**Parâmetros de URI** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="fd033-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="fd033-119">**Cabeçalhos de solicitação** -Content-Type: Application/JSON.</span><span class="sxs-lookup"><span data-stu-id="fd033-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="fd033-120">**Corpo da solicitação** -JSON.</span><span class="sxs-lookup"><span data-stu-id="fd033-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="fd033-121">Exemplo de carga de solicitação:</span><span class="sxs-lookup"><span data-stu-id="fd033-121">Sample request payload:</span></span>
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="fd033-122">*conteúdo* do  Dados formatados como JSON a serem armazenados como o novo conteúdo de um subitem existente.</span><span class="sxs-lookup"><span data-stu-id="fd033-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="fd033-123">Tecnicamente, um repositório pode armazenar qualquer conteúdo de qualquer esquema, mas quando usado para o painel de qualidade da chamada, deve ser um relatório ou uma consulta.</span><span class="sxs-lookup"><span data-stu-id="fd033-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="fd033-124">*digite*  Sempre especifique "Application/JSON" para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="fd033-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="fd033-125">**Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="fd033-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="fd033-126">**Código de status** -uma operação bem-sucedida retorna o código de status 204 (sem conteúdo).</span><span class="sxs-lookup"><span data-stu-id="fd033-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="fd033-127">Se uma ID de item especificada não for encontrada, será retornado o código de status 404 (não encontrado).</span><span class="sxs-lookup"><span data-stu-id="fd033-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fd033-128">"Sem conteúdo" não é um status de erro.</span><span class="sxs-lookup"><span data-stu-id="fd033-128">"No Content" is not an error status.</span></span> <span data-ttu-id="fd033-129">Significa que uma resposta não retornou nada no corpo (em contraste, 200 OK retorna o conteúdo do corpo).</span><span class="sxs-lookup"><span data-stu-id="fd033-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="fd033-130">Isso indica que o item foi atualizado com êxito.</span><span class="sxs-lookup"><span data-stu-id="fd033-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="fd033-131">**Cabeçalhos de resposta** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="fd033-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="fd033-132">**Corpo da resposta** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="fd033-132">**Response Body** - None.</span></span>
  

