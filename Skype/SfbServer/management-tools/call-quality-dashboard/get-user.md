---
title: Obter usuário
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Resumo: Saiba mais sobre a operação obter usuário, que faz parte do serviço de usuário. O serviço de usuário faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 09dcbbaeaae98ed7b01f3d710cfda23aa5fa986f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992618"
---
# <a name="get-user"></a><span data-ttu-id="d49e0-105">Obter usuário</span><span class="sxs-lookup"><span data-stu-id="d49e0-105">Get User</span></span>
 
<span data-ttu-id="d49e0-106">**Resumo:** Saiba mais sobre a operação obter usuário, que faz parte do serviço de usuário.</span><span class="sxs-lookup"><span data-stu-id="d49e0-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="d49e0-107">O serviço de usuário faz parte da API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="d49e0-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="d49e0-108">O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d49e0-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="d49e0-109">A operação obter usuários faz parte do serviço de usuário na API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="d49e0-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="d49e0-110">Obter usuário</span><span class="sxs-lookup"><span data-stu-id="d49e0-110">Get User</span></span>

<span data-ttu-id="d49e0-111">Obter usuário retorna um registro de usuário do repositório.</span><span class="sxs-lookup"><span data-stu-id="d49e0-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="d49e0-112">**Forma**</span><span class="sxs-lookup"><span data-stu-id="d49e0-112">**Method**</span></span>|<span data-ttu-id="d49e0-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="d49e0-113">**Request URI**</span></span>|<span data-ttu-id="d49e0-114">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="d49e0-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d49e0-115">Obter</span><span class="sxs-lookup"><span data-stu-id="d49e0-115">GET</span></span>  <br/> |<span data-ttu-id="d49e0-116">https://\<do\>portal de/QoERepositoryService/Repository/User/{userid}</span><span class="sxs-lookup"><span data-stu-id="d49e0-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="d49e0-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="d49e0-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="d49e0-118">**Parâmetros de URI** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="d49e0-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="d49e0-119">**Solicitar cabeçalhos** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="d49e0-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="d49e0-120">**Corpo da solicitação** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="d49e0-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="d49e0-121">**Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="d49e0-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="d49e0-122">**Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="d49e0-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="d49e0-123">Se um ID de usuário especificado não for encontrado, ele retornará o código de status 404 (não encontrado).</span><span class="sxs-lookup"><span data-stu-id="d49e0-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="d49e0-124">**Cabeçalhos de resposta** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="d49e0-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="d49e0-125">**Corpo da resposta** -abaixo está uma carga de resposta de exemplo em JSON.</span><span class="sxs-lookup"><span data-stu-id="d49e0-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="d49e0-126">*userid* -ID do usuário.</span><span class="sxs-lookup"><span data-stu-id="d49e0-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="d49e0-127">*LoginName* -identificação de usuário externo para usuários normais.</span><span class="sxs-lookup"><span data-stu-id="d49e0-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="d49e0-128">Se a autenticação do Windows for usada para autenticar usuários, isso pode ser um FQDN do usuário.</span><span class="sxs-lookup"><span data-stu-id="d49e0-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="d49e0-129">defaultidid *-ID* do item padrão para este usuário.</span><span class="sxs-lookup"><span data-stu-id="d49e0-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="d49e0-130">O item padrão é o item mais alto que está associado ao usuário.</span><span class="sxs-lookup"><span data-stu-id="d49e0-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="d49e0-131">Todos os outros itens que este usuário tem podem ser acessados a partir do item padrão.</span><span class="sxs-lookup"><span data-stu-id="d49e0-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d49e0-132">Forneça o `defaultItemId` valor para obter a operação do item para recuperar os detalhes do item padrão.</span><span class="sxs-lookup"><span data-stu-id="d49e0-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

