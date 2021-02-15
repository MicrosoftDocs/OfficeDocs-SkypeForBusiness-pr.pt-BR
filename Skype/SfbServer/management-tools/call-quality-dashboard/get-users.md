---
title: Obter os Usuários
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
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Resumo: saiba mais sobre a operação Obter Usuários, que faz parte do Serviço de Usuário. O Serviço de Usuário faz parte da API de Repositório para Painel de Qualidade de Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: a830663fc97d8fda727d1ebb008d97407796cc7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832421"
---
# <a name="get-users"></a><span data-ttu-id="afcf9-105">Obter os Usuários</span><span class="sxs-lookup"><span data-stu-id="afcf9-105">Get Users</span></span>
 
<span data-ttu-id="afcf9-106">**Resumo:** Saiba mais sobre a operação Obter Usuários, que faz parte do Serviço de Usuário.</span><span class="sxs-lookup"><span data-stu-id="afcf9-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="afcf9-107">O Serviço de Usuário faz parte da API de Repositório para Painel de Qualidade de Chamada.</span><span class="sxs-lookup"><span data-stu-id="afcf9-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="afcf9-108">O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="afcf9-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="afcf9-109">A operação Obter Usuários faz parte do Serviço de Usuário na API de Repositório para Painel de Qualidade de Chamada.</span><span class="sxs-lookup"><span data-stu-id="afcf9-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="afcf9-110">Obter os Usuários</span><span class="sxs-lookup"><span data-stu-id="afcf9-110">Get Users</span></span>

<span data-ttu-id="afcf9-111">Obter usuários retorna uma lista de usuários no repositório.</span><span class="sxs-lookup"><span data-stu-id="afcf9-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="afcf9-112">**Method**</span><span class="sxs-lookup"><span data-stu-id="afcf9-112">**Method**</span></span>|<span data-ttu-id="afcf9-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="afcf9-113">**Request URI**</span></span>|<span data-ttu-id="afcf9-114">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="afcf9-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="afcf9-115">OBTER</span><span class="sxs-lookup"><span data-stu-id="afcf9-115">GET</span></span>  <br/> |<span data-ttu-id="afcf9-116">https:// \<portal\> /QoERepositoryService/repository/user</span><span class="sxs-lookup"><span data-stu-id="afcf9-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="afcf9-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="afcf9-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="afcf9-118">**Parâmetros de URI** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="afcf9-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="afcf9-119">**Solicitação de headers** - nenhum outro.</span><span class="sxs-lookup"><span data-stu-id="afcf9-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="afcf9-120">**Corpo da Solicitação** - Nenhum.</span><span class="sxs-lookup"><span data-stu-id="afcf9-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="afcf9-121">**Resposta** - A resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="afcf9-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="afcf9-122">**Código de Status** - Uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="afcf9-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="afcf9-123">**Response Headers** - Sem outros headers.</span><span class="sxs-lookup"><span data-stu-id="afcf9-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="afcf9-124">**Corpo de** Resposta - Abaixo está um exemplo de carga de resposta em JSON.</span><span class="sxs-lookup"><span data-stu-id="afcf9-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="afcf9-125">Uma matriz de objetos User é retornada.</span><span class="sxs-lookup"><span data-stu-id="afcf9-125">An array of User objects is returned.</span></span> <span data-ttu-id="afcf9-126">Para obter detalhes sobre o objeto User, consulte Get User.</span><span class="sxs-lookup"><span data-stu-id="afcf9-126">For details about the User object, see Get User.</span></span> 
  
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


