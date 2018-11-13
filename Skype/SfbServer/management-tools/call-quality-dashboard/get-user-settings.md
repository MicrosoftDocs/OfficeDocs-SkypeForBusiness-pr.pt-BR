---
title: Obter configurações de usuário
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Resumo: Saiba mais sobre a operação obter configurações de usuário, que é parte do serviço de configurações de usuário. O serviço de configurações de usuário é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.'
ms.openlocfilehash: 41bc45f63366337000ad8c263ff8e6dbcb36a3b3
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26293952"
---
# <a name="get-user-settings"></a><span data-ttu-id="c06a1-105">Obter configurações de usuário</span><span class="sxs-lookup"><span data-stu-id="c06a1-105">Get User Settings</span></span>
 
<span data-ttu-id="c06a1-106">**Resumo:** Saiba mais sobre a operação obter configurações de usuário, que é parte do serviço de configurações de usuário.</span><span class="sxs-lookup"><span data-stu-id="c06a1-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="c06a1-107">O serviço de configurações de usuário é parte da API do repositório para painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="c06a1-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="c06a1-108">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c06a1-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c06a1-109">A operação obter configurações de usuário é parte do serviço de configurações do usuário na API repositório para o painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="c06a1-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="c06a1-110">Obter configurações de usuário</span><span class="sxs-lookup"><span data-stu-id="c06a1-110">Get User Settings</span></span>

<span data-ttu-id="c06a1-111">Configurações de usuário Get retorna uma lista de configurações para um usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="c06a1-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="c06a1-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="c06a1-112">**Method**</span></span>|<span data-ttu-id="c06a1-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="c06a1-113">**Request URI**</span></span>|<span data-ttu-id="c06a1-114">**Versão de HTTP**</span><span class="sxs-lookup"><span data-stu-id="c06a1-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c06a1-115">Obter</span><span class="sxs-lookup"><span data-stu-id="c06a1-115">GET</span></span>  <br/> |<span data-ttu-id="c06a1-116">https://\<portal\>/QoERepositoryService/repositório/usuário / {userId} / configuração</span><span class="sxs-lookup"><span data-stu-id="c06a1-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="c06a1-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="c06a1-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="c06a1-118">**Parâmetros URI**</span><span class="sxs-lookup"><span data-stu-id="c06a1-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="c06a1-119">*efetivo* - opcional.</span><span class="sxs-lookup"><span data-stu-id="c06a1-119">*effective*  - Optional.</span></span> <span data-ttu-id="c06a1-120">Esse parâmetro se aplica apenas quando o padrão de ID de usuário especial é usado.</span><span class="sxs-lookup"><span data-stu-id="c06a1-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="c06a1-121">Em outros casos, ele será ignorado.</span><span class="sxs-lookup"><span data-stu-id="c06a1-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="c06a1-122">`True`Retorna as configurações de usuário efetivo e `false` retorna apenas as configurações de usuário (padrão).</span><span class="sxs-lookup"><span data-stu-id="c06a1-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="c06a1-123">**Cabeçalhos de solicitação** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="c06a1-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="c06a1-124">O **corpo da solicitação** - None.</span><span class="sxs-lookup"><span data-stu-id="c06a1-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="c06a1-125">**Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="c06a1-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="c06a1-126">**Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).</span><span class="sxs-lookup"><span data-stu-id="c06a1-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="c06a1-127">**Cabeçalhos de resposta** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="c06a1-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="c06a1-128">**Corpo de resposta** - abaixo é uma carga de resposta de exemplo em JSON.</span><span class="sxs-lookup"><span data-stu-id="c06a1-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
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