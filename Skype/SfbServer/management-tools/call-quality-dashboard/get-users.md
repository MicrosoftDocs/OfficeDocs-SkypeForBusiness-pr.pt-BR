---
title: Colocar os usuários
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Resumo: Saiba mais sobre a operação obter usuários, que é parte do serviço do usuário. O serviço de usuário é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.'
ms.openlocfilehash: 4d4de424776514479ed2204eeb0a5315a7323662
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569695"
---
# <a name="get-users"></a><span data-ttu-id="26c8c-105">Colocar os usuários</span><span class="sxs-lookup"><span data-stu-id="26c8c-105">Get Users</span></span>
 
<span data-ttu-id="26c8c-106">**Resumo:** Saiba mais sobre a operação obter usuários, que é parte do serviço do usuário.</span><span class="sxs-lookup"><span data-stu-id="26c8c-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="26c8c-107">O serviço de usuário é parte da API do repositório para painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="26c8c-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="26c8c-108">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="26c8c-108">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="26c8c-109">A operação obter usuários é parte do serviço do usuário na API repositório para o painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="26c8c-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="26c8c-110">Colocar os usuários</span><span class="sxs-lookup"><span data-stu-id="26c8c-110">Get Users</span></span>

<span data-ttu-id="26c8c-111">Obtenha uma lista de usuários de retorna os usuários no repositório.</span><span class="sxs-lookup"><span data-stu-id="26c8c-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="26c8c-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="26c8c-112">**Method**</span></span>|<span data-ttu-id="26c8c-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="26c8c-113">**Request URI**</span></span>|<span data-ttu-id="26c8c-114">**Versão de HTTP**</span><span class="sxs-lookup"><span data-stu-id="26c8c-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="26c8c-115">Obter</span><span class="sxs-lookup"><span data-stu-id="26c8c-115">GET</span></span>  <br/> |<span data-ttu-id="26c8c-116">https://\<portal\>/QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="26c8c-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="26c8c-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="26c8c-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="26c8c-118">**Parâmetros URI** - None.</span><span class="sxs-lookup"><span data-stu-id="26c8c-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="26c8c-119">**Cabeçalhos de solicitação** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="26c8c-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="26c8c-120">O **corpo da solicitação** - None.</span><span class="sxs-lookup"><span data-stu-id="26c8c-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="26c8c-121">**Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="26c8c-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="26c8c-122">**Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).</span><span class="sxs-lookup"><span data-stu-id="26c8c-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="26c8c-123">**Cabeçalhos de resposta** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="26c8c-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="26c8c-124">**Corpo de resposta** - abaixo é uma carga de resposta de exemplo em JSON.</span><span class="sxs-lookup"><span data-stu-id="26c8c-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="26c8c-125">Uma matriz de objetos de usuário é retornada.</span><span class="sxs-lookup"><span data-stu-id="26c8c-125">An array of User objects is returned.</span></span> <span data-ttu-id="26c8c-126">Para obter detalhes sobre o objeto de usuário, consulte obter um usuário.</span><span class="sxs-lookup"><span data-stu-id="26c8c-126">For details about the User object, see Get User.</span></span> 
  
```
[{
"userId": 0,
"loginName": "system",
"defaultItemId": 1652
},
{
"userId": 1,
"loginName": "SAMPLEDOMAIN\\testuser1",
"defaultItemId": 1652
},
{
"userId": 2,
"loginName": "SAMPLEDOMAIN\\testuser2",
"defaultItemId": 1774
}]
```


