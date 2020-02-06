---
title: Obter configurações de usuário
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
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Resumo: Saiba mais sobre a operação obter configurações de usuário, que faz parte do serviço de configurações do usuário. O serviço configurações do usuário faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 5b5ad679387866ba6562e031b6d3a42cc68851a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816740"
---
# <a name="get-user-settings"></a><span data-ttu-id="945eb-105">Obter configurações de usuário</span><span class="sxs-lookup"><span data-stu-id="945eb-105">Get User Settings</span></span>
 
<span data-ttu-id="945eb-106">**Resumo:** Saiba mais sobre a operação obter configurações de usuário, que faz parte do serviço de configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="945eb-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="945eb-107">O serviço configurações do usuário faz parte da API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="945eb-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="945eb-108">O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="945eb-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="945eb-109">A operação obter configurações do usuário faz parte do serviço configurações do usuário na API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="945eb-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="945eb-110">Obter configurações de usuário</span><span class="sxs-lookup"><span data-stu-id="945eb-110">Get User Settings</span></span>

<span data-ttu-id="945eb-111">Obter configurações do usuário retorna uma lista de configurações para um usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="945eb-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="945eb-112">**Forma**</span><span class="sxs-lookup"><span data-stu-id="945eb-112">**Method**</span></span>|<span data-ttu-id="945eb-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="945eb-113">**Request URI**</span></span>|<span data-ttu-id="945eb-114">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="945eb-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="945eb-115">Obter</span><span class="sxs-lookup"><span data-stu-id="945eb-115">GET</span></span>  <br/> |<span data-ttu-id="945eb-116">https://\<do\>portal de/QoERepositoryService/Repository/User/{userid}/Setting</span><span class="sxs-lookup"><span data-stu-id="945eb-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="945eb-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="945eb-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="945eb-118">**Parâmetros de URI**</span><span class="sxs-lookup"><span data-stu-id="945eb-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="945eb-119">*efetivo* -opcional.</span><span class="sxs-lookup"><span data-stu-id="945eb-119">*effective*  - Optional.</span></span> <span data-ttu-id="945eb-120">Esse parâmetro só se aplica quando o padrão de ID de usuário especial é usado.</span><span class="sxs-lookup"><span data-stu-id="945eb-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="945eb-121">Em outros casos, ele será ignorado.</span><span class="sxs-lookup"><span data-stu-id="945eb-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="945eb-122">`True`Retorna as configurações de usuário `false` efetivas e retorna apenas as configurações do usuário (padrão).</span><span class="sxs-lookup"><span data-stu-id="945eb-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="945eb-123">**Solicitar cabeçalhos** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="945eb-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="945eb-124">**Corpo da solicitação** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="945eb-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="945eb-125">**Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="945eb-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="945eb-126">**Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="945eb-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="945eb-127">**Cabeçalhos de resposta** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="945eb-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="945eb-128">**Corpo da resposta** -abaixo está uma carga de resposta de exemplo em JSON.</span><span class="sxs-lookup"><span data-stu-id="945eb-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
[{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
},
{
"userId": 6,
"key": "ShowTimeStamps",
"value": "true"
}]
```
