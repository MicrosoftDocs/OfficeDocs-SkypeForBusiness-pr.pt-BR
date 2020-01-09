---
title: Obter configuração de usuário
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Resumo: Saiba mais sobre a operação obter a configuração do usuário, que faz parte do serviço de configurações do usuário. O serviço configurações do usuário faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 168e61aaebb47cb087e77cbd18e3e6edfd987227
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992638"
---
# <a name="get-user-setting"></a><span data-ttu-id="d420c-105">Obter configuração de usuário</span><span class="sxs-lookup"><span data-stu-id="d420c-105">Get User Setting</span></span>
 
<span data-ttu-id="d420c-106">**Resumo:** Saiba mais sobre a operação obter a configuração do usuário, que faz parte do serviço de configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="d420c-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="d420c-107">O serviço configurações do usuário faz parte da API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="d420c-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="d420c-108">O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d420c-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="d420c-109">A operação obter a configuração do usuário faz parte do serviço configurações do usuário na API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="d420c-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="d420c-110">Obter configuração de usuário</span><span class="sxs-lookup"><span data-stu-id="d420c-110">Get User Setting</span></span>

<span data-ttu-id="d420c-111">Obter configuração de usuário retorna uma única configuração de usuário.</span><span class="sxs-lookup"><span data-stu-id="d420c-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="d420c-112">**Forma**</span><span class="sxs-lookup"><span data-stu-id="d420c-112">**Method**</span></span>|<span data-ttu-id="d420c-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="d420c-113">**Request URI**</span></span>|<span data-ttu-id="d420c-114">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="d420c-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d420c-115">Obter</span><span class="sxs-lookup"><span data-stu-id="d420c-115">GET</span></span>  <br/> |<span data-ttu-id="d420c-116">https://\<do\>portal de/QoERepositoryService/Repository/User/{userid}/Setting/{Key}</span><span class="sxs-lookup"><span data-stu-id="d420c-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="d420c-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="d420c-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="d420c-118">**Parâmetros de URI** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="d420c-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="d420c-119">**Solicitar cabeçalhos** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="d420c-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="d420c-120">**Corpo da solicitação** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="d420c-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="d420c-121">**Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="d420c-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="d420c-122">**Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="d420c-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="d420c-123">**Cabeçalhos de resposta** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="d420c-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="d420c-124">**Corpo da resposta** -abaixo está uma carga de resposta de exemplo em JSON.</span><span class="sxs-lookup"><span data-stu-id="d420c-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="d420c-125">*userid* -ID do usuário.</span><span class="sxs-lookup"><span data-stu-id="d420c-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="d420c-126">*chave-chave* da configuração.</span><span class="sxs-lookup"><span data-stu-id="d420c-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="d420c-127">*Value* -valor da configuração.</span><span class="sxs-lookup"><span data-stu-id="d420c-127">*value*  - Value of the setting.</span></span>
  

