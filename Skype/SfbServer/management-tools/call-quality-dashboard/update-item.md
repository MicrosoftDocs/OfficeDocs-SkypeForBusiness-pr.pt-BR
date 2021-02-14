---
title: Atualizar Item
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
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Resumo: saiba mais sobre a operação Atualizar Item, que faz parte do Serviço de Item. O Serviço de Item faz parte da API de Repositório para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: 78da2fa414b4ba266f9e6aba4feac5ff73150062
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803081"
---
# <a name="update-item"></a><span data-ttu-id="bf18e-105">Atualizar Item</span><span class="sxs-lookup"><span data-stu-id="bf18e-105">Update Item</span></span>
 
<span data-ttu-id="bf18e-106">**Resumo:** Saiba mais sobre a operação Atualizar Item, que faz parte do Serviço de Item.</span><span class="sxs-lookup"><span data-stu-id="bf18e-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="bf18e-107">O Serviço de Item faz parte da API de Repositório para o Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="bf18e-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="bf18e-108">O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bf18e-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="bf18e-109">A operação Atualizar Item faz parte do Serviço de Item na API de Repositório para Painel de Qualidade de Chamada.</span><span class="sxs-lookup"><span data-stu-id="bf18e-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="bf18e-110">Atualizar Item</span><span class="sxs-lookup"><span data-stu-id="bf18e-110">Update Item</span></span>

<span data-ttu-id="bf18e-111">Atualizar Item atualiza um item específico no repositório.</span><span class="sxs-lookup"><span data-stu-id="bf18e-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="bf18e-112">**Method**</span><span class="sxs-lookup"><span data-stu-id="bf18e-112">**Method**</span></span>|<span data-ttu-id="bf18e-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="bf18e-113">**Request URI**</span></span>|<span data-ttu-id="bf18e-114">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="bf18e-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bf18e-115">PUT</span><span class="sxs-lookup"><span data-stu-id="bf18e-115">PUT</span></span>  <br/> |<span data-ttu-id="bf18e-116">https:// \<portal\> /QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="bf18e-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="bf18e-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="bf18e-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="bf18e-118">**Parâmetros de URI** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="bf18e-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="bf18e-119">**Request Headers** -Content-Type: application/json.</span><span class="sxs-lookup"><span data-stu-id="bf18e-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="bf18e-120">**Corpo da Solicitação** - JSON.</span><span class="sxs-lookup"><span data-stu-id="bf18e-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="bf18e-121">Carga de solicitação de exemplo:</span><span class="sxs-lookup"><span data-stu-id="bf18e-121">Sample request payload:</span></span>
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="bf18e-122">*content*  Dados formatados JSON a serem armazenados como o novo conteúdo de um sub-item existente.</span><span class="sxs-lookup"><span data-stu-id="bf18e-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="bf18e-123">Tecnicamente, um repositório pode armazenar qualquer conteúdo de qualquer esquema, mas quando usado para o Painel de Qualidade da Chamada, ele deve ser um relatório ou uma consulta.</span><span class="sxs-lookup"><span data-stu-id="bf18e-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="bf18e-124">*type*  Sempre especifique "application/json" para o Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="bf18e-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="bf18e-125">**Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="bf18e-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="bf18e-126">**Código de Status** - Uma operação bem-sucedida retorna o código de status 204 (Sem Conteúdo).</span><span class="sxs-lookup"><span data-stu-id="bf18e-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="bf18e-127">Se uma ID de item especificada não for encontrada, retornará o código de status 404 (Não Encontrado).</span><span class="sxs-lookup"><span data-stu-id="bf18e-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bf18e-128">"Nenhum Conteúdo" não é um status de erro.</span><span class="sxs-lookup"><span data-stu-id="bf18e-128">"No Content" is not an error status.</span></span> <span data-ttu-id="bf18e-129">Isso significa que uma resposta não retornou nada no corpo (por outro lado, 200 OK retorna conteúdo no corpo).</span><span class="sxs-lookup"><span data-stu-id="bf18e-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="bf18e-130">Indica que o Item foi atualizado com êxito.</span><span class="sxs-lookup"><span data-stu-id="bf18e-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="bf18e-131">**Response Headers** - None.</span><span class="sxs-lookup"><span data-stu-id="bf18e-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="bf18e-132">**Corpo de Resposta** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="bf18e-132">**Response Body** - None.</span></span>
  

