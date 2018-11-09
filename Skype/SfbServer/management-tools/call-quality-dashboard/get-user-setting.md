---
title: Obter a configuração do usuário
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Resumo: Saiba mais sobre a operação de obter a configuração do usuário, que faz parte do serviço de configurações de usuário. O serviço de configurações de usuário é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: 286939271bdc99790f125beabb68735dd4c5f758
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035642"
---
# <a name="get-user-setting"></a><span data-ttu-id="46bf6-105">Obter a configuração do usuário</span><span class="sxs-lookup"><span data-stu-id="46bf6-105">Get User Setting</span></span>
 
<span data-ttu-id="46bf6-106">**Resumo:** Saiba mais sobre a operação de obter a configuração do usuário, que faz parte do serviço de configurações de usuário.</span><span class="sxs-lookup"><span data-stu-id="46bf6-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="46bf6-107">O serviço de configurações de usuário é parte da API do repositório para painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="46bf6-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="46bf6-108">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="46bf6-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="46bf6-109">A operação de obter a configuração do usuário é parte do serviço de configurações do usuário na API repositório para o painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="46bf6-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="46bf6-110">Obter a configuração do usuário</span><span class="sxs-lookup"><span data-stu-id="46bf6-110">Get User Setting</span></span>

<span data-ttu-id="46bf6-111">Obtenha a configuração do usuário retorna a configuração de um único usuário.</span><span class="sxs-lookup"><span data-stu-id="46bf6-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="46bf6-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="46bf6-112">**Method**</span></span>|<span data-ttu-id="46bf6-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="46bf6-113">**Request URI**</span></span>|<span data-ttu-id="46bf6-114">**Versão de HTTP**</span><span class="sxs-lookup"><span data-stu-id="46bf6-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="46bf6-115">Obter</span><span class="sxs-lookup"><span data-stu-id="46bf6-115">GET</span></span>  <br/> |<span data-ttu-id="46bf6-116">https://\<portal\>/QoERepositoryService/repositório/usuário / {userId} /setting/ {chave}</span><span class="sxs-lookup"><span data-stu-id="46bf6-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="46bf6-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="46bf6-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="46bf6-118">**Parâmetros URI** - None.</span><span class="sxs-lookup"><span data-stu-id="46bf6-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="46bf6-119">**Cabeçalhos de solicitação** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="46bf6-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="46bf6-120">O **corpo da solicitação** - None.</span><span class="sxs-lookup"><span data-stu-id="46bf6-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="46bf6-121">**Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="46bf6-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="46bf6-122">**Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).</span><span class="sxs-lookup"><span data-stu-id="46bf6-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="46bf6-123">**Cabeçalhos de resposta** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="46bf6-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="46bf6-124">**Corpo de resposta** - abaixo é uma carga de resposta de exemplo em JSON.</span><span class="sxs-lookup"><span data-stu-id="46bf6-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="46bf6-125">*userId* - ID do usuário.</span><span class="sxs-lookup"><span data-stu-id="46bf6-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="46bf6-126">*chave* - chave da configuração.</span><span class="sxs-lookup"><span data-stu-id="46bf6-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="46bf6-127">*valor* - valor da configuração.</span><span class="sxs-lookup"><span data-stu-id="46bf6-127">*value*  - Value of the setting.</span></span>
  

