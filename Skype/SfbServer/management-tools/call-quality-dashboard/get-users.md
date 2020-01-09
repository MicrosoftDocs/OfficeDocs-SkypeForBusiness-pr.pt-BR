---
title: Obter usuários
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Resumo: Saiba mais sobre a operação obter usuários, que faz parte do serviço de usuário. O serviço de usuário faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 6cf2248035c780c2efce6b1f4539a39cd2a5829a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992608"
---
# <a name="get-users"></a><span data-ttu-id="3567a-105">Obter usuários</span><span class="sxs-lookup"><span data-stu-id="3567a-105">Get Users</span></span>
 
<span data-ttu-id="3567a-106">**Resumo:** Saiba mais sobre a operação obter usuários, que faz parte do serviço de usuário.</span><span class="sxs-lookup"><span data-stu-id="3567a-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="3567a-107">O serviço de usuário faz parte da API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="3567a-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="3567a-108">O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3567a-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="3567a-109">A operação obter usuários faz parte do serviço de usuário na API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="3567a-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="3567a-110">Obter usuários</span><span class="sxs-lookup"><span data-stu-id="3567a-110">Get Users</span></span>

<span data-ttu-id="3567a-111">Obter usuários retorna uma lista de usuários no repositório.</span><span class="sxs-lookup"><span data-stu-id="3567a-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="3567a-112">**Forma**</span><span class="sxs-lookup"><span data-stu-id="3567a-112">**Method**</span></span>|<span data-ttu-id="3567a-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="3567a-113">**Request URI**</span></span>|<span data-ttu-id="3567a-114">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="3567a-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3567a-115">Obter</span><span class="sxs-lookup"><span data-stu-id="3567a-115">GET</span></span>  <br/> |<span data-ttu-id="3567a-116">https://\<do\>portal de/QoERepositoryService/Repository/User</span><span class="sxs-lookup"><span data-stu-id="3567a-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="3567a-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="3567a-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="3567a-118">**Parâmetros de URI** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="3567a-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="3567a-119">**Solicitar cabeçalhos** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="3567a-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="3567a-120">**Corpo da solicitação** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="3567a-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="3567a-121">**Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="3567a-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="3567a-122">**Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="3567a-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="3567a-123">**Cabeçalhos de resposta** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="3567a-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="3567a-124">**Corpo da resposta** -abaixo está uma carga de resposta de exemplo em JSON.</span><span class="sxs-lookup"><span data-stu-id="3567a-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3567a-125">Uma matriz de objetos de usuário é retornada.</span><span class="sxs-lookup"><span data-stu-id="3567a-125">An array of User objects is returned.</span></span> <span data-ttu-id="3567a-126">Para obter detalhes sobre o objeto de usuário, consulte obter usuário.</span><span class="sxs-lookup"><span data-stu-id="3567a-126">For details about the User object, see Get User.</span></span> 
  
```json
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


