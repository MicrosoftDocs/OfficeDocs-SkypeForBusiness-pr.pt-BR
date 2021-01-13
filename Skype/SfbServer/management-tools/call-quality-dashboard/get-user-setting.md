---
title: Obter as Configuração de Usuário
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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Resumo: saiba mais sobre a operação Obter Configuração do Usuário, que faz parte do Serviço de Configurações do Usuário. O Serviço de Configurações do Usuário faz parte da API de Repositório para o Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: 82632f5de7ae215d6f34d9f0b39e500fb713a1be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832481"
---
# <a name="get-user-setting"></a><span data-ttu-id="c7f03-105">Obter as Configuração de Usuário</span><span class="sxs-lookup"><span data-stu-id="c7f03-105">Get User Setting</span></span>
 
<span data-ttu-id="c7f03-106">**Resumo:** Saiba mais sobre a operação Obter Configuração do Usuário, que faz parte do Serviço de Configurações do Usuário.</span><span class="sxs-lookup"><span data-stu-id="c7f03-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="c7f03-107">O Serviço de Configurações do Usuário faz parte da API de Repositório para o Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="c7f03-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="c7f03-108">O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c7f03-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="c7f03-109">A operação Obter Configuração do Usuário faz parte do Serviço de Configurações do Usuário na API de Repositório para Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="c7f03-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="c7f03-110">Obter as Configuração de Usuário</span><span class="sxs-lookup"><span data-stu-id="c7f03-110">Get User Setting</span></span>

<span data-ttu-id="c7f03-111">Obter Configuração do Usuário retorna uma configuração de usuário único.</span><span class="sxs-lookup"><span data-stu-id="c7f03-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="c7f03-112">**Method**</span><span class="sxs-lookup"><span data-stu-id="c7f03-112">**Method**</span></span>|<span data-ttu-id="c7f03-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="c7f03-113">**Request URI**</span></span>|<span data-ttu-id="c7f03-114">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="c7f03-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c7f03-115">OBTER</span><span class="sxs-lookup"><span data-stu-id="c7f03-115">GET</span></span>  <br/> |<span data-ttu-id="c7f03-116">https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting/{key}</span><span class="sxs-lookup"><span data-stu-id="c7f03-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="c7f03-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="c7f03-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="c7f03-118">**Parâmetros de URI** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="c7f03-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="c7f03-119">**Solicitação de headers** - nenhum outro.</span><span class="sxs-lookup"><span data-stu-id="c7f03-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c7f03-120">**Corpo da Solicitação** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="c7f03-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="c7f03-121">**Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="c7f03-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="c7f03-122">**Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="c7f03-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="c7f03-123">**Response Headers** - Sem outros headers.</span><span class="sxs-lookup"><span data-stu-id="c7f03-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c7f03-124">**Corpo de** Resposta - Abaixo está um exemplo de carga de resposta em JSON.</span><span class="sxs-lookup"><span data-stu-id="c7f03-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="c7f03-125">*userId*  - ID do usuário.</span><span class="sxs-lookup"><span data-stu-id="c7f03-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="c7f03-126">*chave*  - Chave da configuração.</span><span class="sxs-lookup"><span data-stu-id="c7f03-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="c7f03-127">*valor*  - Valor da configuração.</span><span class="sxs-lookup"><span data-stu-id="c7f03-127">*value*  - Value of the setting.</span></span>
  

