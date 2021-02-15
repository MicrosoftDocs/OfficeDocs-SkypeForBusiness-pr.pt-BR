---
title: Obter os Itens
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
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 'Resumo: saiba mais sobre a operação Obter Itens, que faz parte do Serviço de Item. O Serviço de Item faz parte da API de Repositório para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: 7da3ba77e782abe44896a7c1eb51a458d9a7e0b8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832531"
---
# <a name="get-items"></a><span data-ttu-id="0b36e-105">Obter os Itens</span><span class="sxs-lookup"><span data-stu-id="0b36e-105">Get Items</span></span>
 
<span data-ttu-id="0b36e-106">**Resumo:** Saiba mais sobre a operação Obter Itens, que faz parte do Serviço de Item.</span><span class="sxs-lookup"><span data-stu-id="0b36e-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="0b36e-107">O Serviço de Item faz parte da API de Repositório para o Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="0b36e-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="0b36e-108">O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0b36e-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="0b36e-109">A operação Obter Itens faz parte do Serviço de Item na API de Repositório para Painel de Qualidade de Chamada.</span><span class="sxs-lookup"><span data-stu-id="0b36e-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="0b36e-110">Obter os Itens</span><span class="sxs-lookup"><span data-stu-id="0b36e-110">Get Items</span></span>

<span data-ttu-id="0b36e-111">Get Items retorna todos os itens no repositório.</span><span class="sxs-lookup"><span data-stu-id="0b36e-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="0b36e-112">**Method**</span><span class="sxs-lookup"><span data-stu-id="0b36e-112">**Method**</span></span>|<span data-ttu-id="0b36e-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="0b36e-113">**Request URI**</span></span>|<span data-ttu-id="0b36e-114">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="0b36e-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0b36e-115">OBTER</span><span class="sxs-lookup"><span data-stu-id="0b36e-115">GET</span></span>  <br/> |<span data-ttu-id="0b36e-116">https:// \<portal\> /QoERepositoryService/repository/item</span><span class="sxs-lookup"><span data-stu-id="0b36e-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="0b36e-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="0b36e-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="0b36e-118">**Parâmetros de URI** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="0b36e-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="0b36e-119">**Solicitação de headers** - nenhum outro.</span><span class="sxs-lookup"><span data-stu-id="0b36e-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0b36e-120">**Corpo da Solicitação** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="0b36e-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="0b36e-121">**Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="0b36e-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="0b36e-122">**Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="0b36e-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="0b36e-123">**Response Headers** - Sem outros headers.</span><span class="sxs-lookup"><span data-stu-id="0b36e-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="0b36e-124">**Corpo de** Resposta - Abaixo está um exemplo de carga de resposta em JSON.</span><span class="sxs-lookup"><span data-stu-id="0b36e-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0b36e-125">Uma matriz de objetos Item é retornada.</span><span class="sxs-lookup"><span data-stu-id="0b36e-125">An array of Item objects is returned.</span></span> <span data-ttu-id="0b36e-126">Para obter detalhes sobre o objeto Item, consulte Get Item.</span><span class="sxs-lookup"><span data-stu-id="0b36e-126">For details about Item object, see Get Item.</span></span> 
  
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
