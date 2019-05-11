---
title: Obter configurações de usuário
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Resumo: Saiba mais sobre a operação obter configurações de usuário, que é parte do serviço de configurações de usuário. O serviço de configurações de usuário é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: cef6eef88f4fa7a7410f4967ad698972f98d7c5f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930585"
---
# <a name="get-user-settings"></a><span data-ttu-id="a11cf-105">Obter configurações de usuário</span><span class="sxs-lookup"><span data-stu-id="a11cf-105">Get User Settings</span></span>
 
<span data-ttu-id="a11cf-106">**Resumo:** Saiba mais sobre a operação obter configurações de usuário, que é parte do serviço de configurações de usuário.</span><span class="sxs-lookup"><span data-stu-id="a11cf-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="a11cf-107">O serviço de configurações de usuário é parte da API do repositório para painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="a11cf-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="a11cf-108">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="a11cf-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="a11cf-109">A operação obter configurações de usuário é parte do serviço de configurações do usuário na API repositório para o painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="a11cf-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="a11cf-110">Obter configurações de usuário</span><span class="sxs-lookup"><span data-stu-id="a11cf-110">Get User Settings</span></span>

<span data-ttu-id="a11cf-111">Configurações de usuário Get retorna uma lista de configurações para um usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="a11cf-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="a11cf-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="a11cf-112">**Method**</span></span>|<span data-ttu-id="a11cf-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="a11cf-113">**Request URI**</span></span>|<span data-ttu-id="a11cf-114">**Versão de HTTP**</span><span class="sxs-lookup"><span data-stu-id="a11cf-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a11cf-115">Obter</span><span class="sxs-lookup"><span data-stu-id="a11cf-115">GET</span></span>  <br/> |<span data-ttu-id="a11cf-116">https://\<portal\>/QoERepositoryService/repositório/usuário / {userId} / configuração</span><span class="sxs-lookup"><span data-stu-id="a11cf-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="a11cf-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="a11cf-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="a11cf-118">**Parâmetros URI**</span><span class="sxs-lookup"><span data-stu-id="a11cf-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="a11cf-119">*efetivo* - opcional.</span><span class="sxs-lookup"><span data-stu-id="a11cf-119">*effective*  - Optional.</span></span> <span data-ttu-id="a11cf-120">Esse parâmetro se aplica apenas quando o padrão de ID de usuário especial é usado.</span><span class="sxs-lookup"><span data-stu-id="a11cf-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="a11cf-121">Em outros casos, ele será ignorado.</span><span class="sxs-lookup"><span data-stu-id="a11cf-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="a11cf-122">`True`Retorna as configurações de usuário efetivo e `false` retorna apenas as configurações de usuário (padrão).</span><span class="sxs-lookup"><span data-stu-id="a11cf-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="a11cf-123">**Cabeçalhos de solicitação** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="a11cf-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="a11cf-124">O **corpo da solicitação** - None.</span><span class="sxs-lookup"><span data-stu-id="a11cf-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="a11cf-125">**Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="a11cf-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="a11cf-126">**Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).</span><span class="sxs-lookup"><span data-stu-id="a11cf-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="a11cf-127">**Cabeçalhos de resposta** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="a11cf-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="a11cf-128">**Corpo de resposta** - abaixo é uma carga de resposta de exemplo em JSON.</span><span class="sxs-lookup"><span data-stu-id="a11cf-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
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
