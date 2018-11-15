---
title: Obter do usuário
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Resumo: Saiba mais sobre a operação de usuário obter, que faz parte do serviço de usuário. O serviço de usuário é parte da API do repositório para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.'
ms.openlocfilehash: 3508336eda934cf317f857d7ad7e903cb7298e00
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26533270"
---
# <a name="get-user"></a><span data-ttu-id="88836-105">Obter do usuário</span><span class="sxs-lookup"><span data-stu-id="88836-105">Get User</span></span>
 
<span data-ttu-id="88836-106">**Resumo:** Saiba mais sobre a operação de usuário obter, que faz parte do serviço de usuário.</span><span class="sxs-lookup"><span data-stu-id="88836-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="88836-107">O serviço de usuário é parte da API do repositório para painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="88836-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="88836-108">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="88836-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="88836-109">A operação obter usuários é parte do serviço do usuário na API repositório para o painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="88836-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="88836-110">Obter do usuário</span><span class="sxs-lookup"><span data-stu-id="88836-110">Get User</span></span>

<span data-ttu-id="88836-111">Obtenha o usuário retornos de um registro de usuário do repositório.</span><span class="sxs-lookup"><span data-stu-id="88836-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="88836-112">**Método**</span><span class="sxs-lookup"><span data-stu-id="88836-112">**Method**</span></span>|<span data-ttu-id="88836-113">**URI de solicitação**</span><span class="sxs-lookup"><span data-stu-id="88836-113">**Request URI**</span></span>|<span data-ttu-id="88836-114">**Versão de HTTP**</span><span class="sxs-lookup"><span data-stu-id="88836-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="88836-115">Obter</span><span class="sxs-lookup"><span data-stu-id="88836-115">GET</span></span>  <br/> |<span data-ttu-id="88836-116">https://\<portal\>/QoERepositoryService/repositório/usuário / {userId}</span><span class="sxs-lookup"><span data-stu-id="88836-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="88836-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="88836-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="88836-118">**Parâmetros URI** - None.</span><span class="sxs-lookup"><span data-stu-id="88836-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="88836-119">**Cabeçalhos de solicitação** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="88836-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="88836-120">O **corpo da solicitação** - None.</span><span class="sxs-lookup"><span data-stu-id="88836-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="88836-121">**Resposta** - a resposta inclui um código de status HTTP e um conjunto de cabeçalhos de resposta.</span><span class="sxs-lookup"><span data-stu-id="88836-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="88836-122">**Código de status** - uma operação bem-sucedida retorna o código de status 200 (Okey).</span><span class="sxs-lookup"><span data-stu-id="88836-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="88836-123">Se um usuário especificado que ID não for encontrado, será retornado o código de status 404 (não encontrado).</span><span class="sxs-lookup"><span data-stu-id="88836-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="88836-124">**Cabeçalhos de resposta** - sem cabeçalhos adicionais.</span><span class="sxs-lookup"><span data-stu-id="88836-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="88836-125">**Corpo de resposta** - abaixo é uma carga de resposta de exemplo em JSON.</span><span class="sxs-lookup"><span data-stu-id="88836-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="88836-126">*userId* - ID do usuário.</span><span class="sxs-lookup"><span data-stu-id="88836-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="88836-127">*loginName* - identificação de usuário externo para usuários regulares.</span><span class="sxs-lookup"><span data-stu-id="88836-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="88836-128">Se a autenticação do Windows é usada para autenticação de usuários, isso pode ser um FQDN do usuário.</span><span class="sxs-lookup"><span data-stu-id="88836-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="88836-129">*defaultItemId* - ID do Item padrão para este usuário.</span><span class="sxs-lookup"><span data-stu-id="88836-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="88836-130">O Item padrão é o Item de nível superior que está associado ao usuário.</span><span class="sxs-lookup"><span data-stu-id="88836-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="88836-131">Todos os outros itens que pertencentes este usuário podem ser navegados para o Item padrão.</span><span class="sxs-lookup"><span data-stu-id="88836-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="88836-132">Fornecer o `defaultItemId` valor a operação obter Item para recuperar os detalhes do Item padrão.</span><span class="sxs-lookup"><span data-stu-id="88836-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

