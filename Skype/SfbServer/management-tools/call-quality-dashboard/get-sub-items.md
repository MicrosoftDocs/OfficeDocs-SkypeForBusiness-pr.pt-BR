---
title: Obter os Subitens
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
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Resumo: saiba mais sobre a operação Sub-Items obter, que faz parte do Serviço de Item. O Serviço de Item faz parte da API de Repositório para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: defb0b898c5101513cbb4f6da4382a8bb43bce6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832501"
---
# <a name="get-sub-items"></a><span data-ttu-id="7ab24-105">Obter os Subitens</span><span class="sxs-lookup"><span data-stu-id="7ab24-105">Get Sub-Items</span></span>
 
<span data-ttu-id="7ab24-106">**Resumo:** Saiba mais sobre a operação Sub-Items obter, que faz parte do Serviço de Item.</span><span class="sxs-lookup"><span data-stu-id="7ab24-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="7ab24-107">O Serviço de Item faz parte da API de Repositório para o Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="7ab24-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="7ab24-108">O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7ab24-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="7ab24-109">A operação Obter Sub-Items é parte do Serviço de Item na API de Repositório para Painel de Qualidade de Chamada.</span><span class="sxs-lookup"><span data-stu-id="7ab24-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="7ab24-110">Obter os Subitens</span><span class="sxs-lookup"><span data-stu-id="7ab24-110">Get Sub-Items</span></span>

<span data-ttu-id="7ab24-111">Get Sub-Items retorna sub-itens de um Item específico.</span><span class="sxs-lookup"><span data-stu-id="7ab24-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="7ab24-112">**Method**</span><span class="sxs-lookup"><span data-stu-id="7ab24-112">**Method**</span></span>|<span data-ttu-id="7ab24-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="7ab24-113">**Request URI**</span></span>|<span data-ttu-id="7ab24-114">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="7ab24-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7ab24-115">OBTER</span><span class="sxs-lookup"><span data-stu-id="7ab24-115">GET</span></span>  <br/> |<span data-ttu-id="7ab24-116">https:// \<portal\> /QoERepositoryService/repository/item/{itemId}/subtentem</span><span class="sxs-lookup"><span data-stu-id="7ab24-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="7ab24-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="7ab24-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="7ab24-118">**Parâmetros de URI** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="7ab24-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="7ab24-119">**Solicitação de headers** - nenhum outro.</span><span class="sxs-lookup"><span data-stu-id="7ab24-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7ab24-120">**Corpo da Solicitação** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="7ab24-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="7ab24-121">**Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="7ab24-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="7ab24-122">**Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="7ab24-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="7ab24-123">Se uma ID de usuário especificada não for encontrada, ela retornará o código de status 404 (Não Encontrado).</span><span class="sxs-lookup"><span data-stu-id="7ab24-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="7ab24-124">**Response Headers** - Sem outros headers.</span><span class="sxs-lookup"><span data-stu-id="7ab24-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7ab24-125">**Corpo de** Resposta - Abaixo está um exemplo de carga de resposta em JSON.</span><span class="sxs-lookup"><span data-stu-id="7ab24-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7ab24-126">Uma matriz do objeto Item é retornada.</span><span class="sxs-lookup"><span data-stu-id="7ab24-126">An array of Item object is returned.</span></span> 
  
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

<span data-ttu-id="7ab24-127">O objeto Item retornado pela Sub-Items contém apenas os três campos a seguir.</span><span class="sxs-lookup"><span data-stu-id="7ab24-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="7ab24-128">*itemId*  - ID do item.</span><span class="sxs-lookup"><span data-stu-id="7ab24-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="7ab24-129">*userId*  - ID do usuário que possui este Item.</span><span class="sxs-lookup"><span data-stu-id="7ab24-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="7ab24-130">*tipo*  - O tipo do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="7ab24-130">*type*  - The type of the content.</span></span> <span data-ttu-id="7ab24-131">Esse campo é definido pelos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="7ab24-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="7ab24-132">`Content` e `subItems` os campos não são incluídos na resposta para reduzir a quantidade de dados transmitidos pela rede.</span><span class="sxs-lookup"><span data-stu-id="7ab24-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

