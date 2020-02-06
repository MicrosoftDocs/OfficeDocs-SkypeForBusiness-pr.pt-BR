---
title: Obter usuário
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
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Resumo: Saiba mais sobre a operação obter usuário, que faz parte do serviço de usuário. O serviço de usuário faz parte da API do repositório para o painel de qualidade da chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: e07a232b61e5ef0bb7462b3fff58d642a14496ec
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816730"
---
# <a name="get-user"></a><span data-ttu-id="9235b-105">Obter usuário</span><span class="sxs-lookup"><span data-stu-id="9235b-105">Get User</span></span>
 
<span data-ttu-id="9235b-106">**Resumo:** Saiba mais sobre a operação obter usuário, que faz parte do serviço de usuário.</span><span class="sxs-lookup"><span data-stu-id="9235b-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="9235b-107">O serviço de usuário faz parte da API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="9235b-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="9235b-108">O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9235b-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="9235b-109">A operação obter usuários faz parte do serviço de usuário na API do repositório para o painel de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="9235b-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="9235b-110">Obter usuário</span><span class="sxs-lookup"><span data-stu-id="9235b-110">Get User</span></span>

<span data-ttu-id="9235b-111">Obter usuário retorna um registro de usuário do repositório.</span><span class="sxs-lookup"><span data-stu-id="9235b-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="9235b-112">**Forma**</span><span class="sxs-lookup"><span data-stu-id="9235b-112">**Method**</span></span>|<span data-ttu-id="9235b-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="9235b-113">**Request URI**</span></span>|<span data-ttu-id="9235b-114">**Versão HTTP**</span><span class="sxs-lookup"><span data-stu-id="9235b-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9235b-115">Obter</span><span class="sxs-lookup"><span data-stu-id="9235b-115">GET</span></span>  <br/> |<span data-ttu-id="9235b-116">https://\<do\>portal de/QoERepositoryService/Repository/User/{userid}</span><span class="sxs-lookup"><span data-stu-id="9235b-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="9235b-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="9235b-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="9235b-118">**Parâmetros de URI** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="9235b-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="9235b-119">**Solicitar cabeçalhos** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="9235b-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9235b-120">**Corpo da solicitação** -nenhum.</span><span class="sxs-lookup"><span data-stu-id="9235b-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="9235b-121">**Resposta** -a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="9235b-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="9235b-122">**Código de status** -uma operação bem-sucedida retorna o código de status 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="9235b-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="9235b-123">Se um ID de usuário especificado não for encontrado, ele retornará o código de status 404 (não encontrado).</span><span class="sxs-lookup"><span data-stu-id="9235b-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="9235b-124">**Cabeçalhos de resposta** -sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="9235b-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9235b-125">**Corpo da resposta** -abaixo está uma carga de resposta de exemplo em JSON.</span><span class="sxs-lookup"><span data-stu-id="9235b-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="9235b-126">*userid* -ID do usuário.</span><span class="sxs-lookup"><span data-stu-id="9235b-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="9235b-127">*LoginName* -identificação de usuário externo para usuários normais.</span><span class="sxs-lookup"><span data-stu-id="9235b-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="9235b-128">Se a autenticação do Windows for usada para autenticar usuários, isso pode ser um FQDN do usuário.</span><span class="sxs-lookup"><span data-stu-id="9235b-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="9235b-129">defaultidid *-ID* do item padrão para este usuário.</span><span class="sxs-lookup"><span data-stu-id="9235b-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="9235b-130">O item padrão é o item mais alto que está associado ao usuário.</span><span class="sxs-lookup"><span data-stu-id="9235b-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="9235b-131">Todos os outros itens que este usuário tem podem ser acessados a partir do item padrão.</span><span class="sxs-lookup"><span data-stu-id="9235b-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9235b-132">Forneça o `defaultItemId` valor para obter a operação do item para recuperar os detalhes do item padrão.</span><span class="sxs-lookup"><span data-stu-id="9235b-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

